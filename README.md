# Generate Leads with Google Maps (n8n Workflow)

![Workflow Screenshot](Screenshot%202025-08-06%20014737.png)

## Overview
This n8n workflow automates the process of extracting business leads from Google Maps and saving them to Google Sheets. It is designed for users who want to collect business information (such as phone numbers, addresses, ratings, and more) for specific subcategories and zip codes.

## Features
- **Manual and Scheduled Triggers:** Start the workflow manually or on a schedule.
- **Google Sheets Integration:** Reads zip codes and subcategories from your Google Sheets, and writes results back.
- **Google Maps API Integration:** Searches Google Maps for businesses matching your criteria.
- **Duplicate Removal:** Ensures only unique leads are added.
- **Exponential Backoff & Retry Logic:** Handles API rate limits and errors gracefully.
- **Status Updates:** Marks zip codes as scraped and updates workflow status in Google Sheets.
- **Error Handling:** Stops workflow and provides error messages if Google Sheets API limits are reached.

## How It Works
1. **Settings:** Configure your Google Sheets document URL, zip code sheet name, and subcategory sheet name.
2. **Triggers:** Start the workflow manually or on a schedule.
3. **Data Preparation:** Fetch zip codes and subcategories from Google Sheets, filter out ignored or already scraped entries.
4. **Looping:** For each zip code and subcategory, query the Google Maps API for matching businesses.
5. **Processing Results:** Split results, remove duplicates, and append new leads to the results sheet in Google Sheets.
6. **Status Update:** Mark processed zip codes as scraped.
7. **Error Handling:** If API limits are hit, the workflow stops and logs an error.

## Requirements
- n8n installed and running
- Google Cloud account with Maps API enabled
- Google Sheets document with zip codes and subcategories
- Google OAuth2 credentials set up in n8n

## Setup Instructions
1. **Clone this repository.**
2. **Import the workflow JSON file** (`Generate Leads with Google Maps.json`) into n8n.
3. **Update the Google Sheets URLs and sheet names** in the workflow settings node.
4. **Set up Google OAuth2 credentials** in n8n for Sheets and Maps API access.
5. **Start the workflow manually or enable the schedule trigger.**

## Customization
- Adjust the zip code and subcategory sheets to target different regions or business types.
- Modify the Google Maps API query parameters for more specific searches.
- Add or remove columns in the Google Sheets integration nodes as needed.

## Workflow Screenshot
![Workflow Screenshot](Screenshot%202025-08-06%20014737.png)

## Author
* 🌐 Connect with me on LinkedIn: [Syed Abdullah Shah](http://www.linkedin.com/in/syed-abdullah-shah-4018a5176)
* 📩 Email: [sa.abdullahshah.2001@gmail.com](mailto:sa.abdullahshah.2001@gmail.com)

---

*This workflow is provided as-is. Please ensure you comply with Google Maps and Google Sheets API usage policies.*
