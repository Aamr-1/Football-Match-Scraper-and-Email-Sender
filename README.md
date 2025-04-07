# Football Match Scraper and Email Sender

## Overview
This script scrapes the list of football matches from the Goal.com website for a specific date and sends the details of those matches (including teams, scores, and championship information) as an Excel file via email. The script runs automatically every day at 9:00 PM and sends the results to a predefined email address.

## Features:
- Scrapes football match data from Goal.com.
- Creates an Excel file with match details: championship title, teams, and scores.
- Sends the generated Excel file as an email attachment.
- Runs automatically at 9:00 PM every day.

## Requirements
1. Python 3.x
2. Install the necessary libraries by running the following command:
   
   ```bash
   pip install requests beautifulsoup4 pandas openpyxl python-dotenv schedule
   ```
## Setup
### 1. Create an .env file
You need to create a .env file in the same directory as your script. This file will store your email address and app password securely. Example:
```env
email_address=your_email@gmail.com
APP_pass=your_app_password
```
Make sure to replace your_email@gmail.com with your actual email address, and your_app_password with the app password you generate from your email provider (e.g., Gmail).
## Configure your email settings:
  -Email Address: The email address from which the script will send the email.
  -app Password: To use Gmail or other email providers, you may need to create an app-specific password. Follow your provider's documentation to create one.
For Gmail, you can generate an app password here: https://myaccount.google.com/apppasswords.

## Understanding the Code:

**Scraping**: The script fetches the list of football matches for the current date by scraping Goal.com. It looks for the following information:

- **Championship title**
- **Teams** (Team A and Team B)
- **Scores** (if available)

**Excel File Generation**: The match data is saved into an Excel file, which is then sent as an email attachment.

**Email Sending**: The email is sent using Gmail's SMTP server (`smtp.gmail.com`). You need to have the app password configured for the email to work.
##  Running the Script:
-Ensure your .env file is configured correctly with your email address and app password.
-Run the script using the following command:
```bash

python your_script_name.py

```

This will start the script, and it will run in the background indefinitely. The script checks every minute for any scheduled tasks (e.g., sending the daily email at 9:00 PM).

## Scheduling:
-The script uses the schedule library to run the job() function daily at 9:00 PM, sending the email with the football match details.

## Troubleshooting:
### **1-Missing Data:**
-If the script can't find data (teams or scores), it prints an error message indicating the missing information.

-Make sure the website's structure has not changed; if it has, the script might need adjustments.

 ### **2-Email Not Sending:**

  -Ensure your email and app password are set up correctly in the .env file.

  -Check for any email sending limits imposed by your email provider.

### 3-Dependencies Missing:
If you encounter issues related to missing dependencies, ensure all required libraries are installed using:
```bash
pip install -r requirements.txt.
```

### **4-App Password Issues (Gmail):**

If you're using Gmail, ensure you have enabled "Less secure apps" (or generated an app-specific password if 2FA is enabled).


