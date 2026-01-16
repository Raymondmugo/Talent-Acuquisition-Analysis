## Merlin Kenya User Inactivity Analysis Dashboard
This repository contains a Python data analysis script designed to process user activity logs (specifically for Merlin Kenya users). 
The tool generates insights regarding user inactivity, reactivation timelines, and role-based trends.
It outputs a visual dashboard (PNG) and detailed statistical summaries (CSV) to assist in operational decision-making.
  # Features
Reactivation Analysis: Calculates the time taken for an INACTIVE user to return to an ACTIVE state.
Role-Based Metrics: Aggregates total inactive and active counts per job role.
Sector & Branch Analysis: Identifies which sectors and specific stations (branches) have the highest volume of inactive accounts.
Visualization: Automatically generates a 4-panel dashboard highlighting top trends.
##  Prerequisites
To run this script, you will need Python installed along with the following libraries:pandasmatplotlibseaborn
You can install the dependencies using pip:Bashpip install pandas matplotlib seaborn
## Input Data Requirements
The script expects a CSV file (e.g., Merlin II Kenya Users - results-xxxx.csv) containing the following 
columns:Column NameDescriptionlastModifiedDateISO8601 formatted datetime string of the last record update.
creationDateISO8601 formatted datetime string of account creation.
userStateCurrent status of the user (e.g., 'ACTIVE', 'INACTIVE').role_display_nameThe job title or role associated with the 
user.sector_idIdentifier for the operational sector.nameName of the station or branch.emailUser email address (used for the detailed event CSV).
## Usage
Place your data file in the project directory.Update the file path: 
Open the script and modify the file_path variable to point to your CSV location.Python# Example inside the script
file_path = "path/to/your/data_file.csv"
  # Run the script:Bashpython analysis_script.py
## Methodology & Assumptions
Time to Activate: The script assumes the dataset is sorted or ordered chronologically. I
t calculates "Time to Activate" by measuring the time difference between a row marked INACTIVE and the immediately following row,
assuming the next row represents the reactivation event.Role Attribution: Reactivation times are attributed to the role the user held during the INACTIVE state.
  ## Outputs
  The script generates the following files in the working directory:1. Visual Dashboard (comprehensive_inactive_analysis.png)
  A composite image containing four charts:Top 10 Roles with the most Inactive Status.Average Days to Reactivate by Role.Inactive Accounts by Sector.
  Top 10 Inactive Stations (Branches).2. Data Summariesrole_inactivity_summary.csv: A summary table showing total active/inactive counts and 
  average reactivation time per role.reactivation_events.csv: A detailed log of specific reactivation events, including the email, role, date, 
  and calculated days taken to reactivate.
 ## Author Njeri Mugo 0136🤓
