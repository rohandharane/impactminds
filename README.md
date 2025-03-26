# Lightning Talks Schedule Display

This application displays a schedule for lightning talks, pulling data from either Google Sheets or Airtable.

## Setup Instructions

### Google Sheets Setup

1. Create a Google Sheet with the following columns:
   - TIME
   - SPEAKER
   - ROOM
   - STATUS (values should be: OPEN, CLOSING, or CLOSED)

2. Publish your Google Sheet to the web:
   - Go to File > Share > Publish to web
   - Choose the sheet you want to publish
   - Click "Publish"
   - Copy the Sheet ID from the URL (the long string between /d/ and /edit in the URL)

3. Update the configuration in `index.html`:
   - Set `DATA_SOURCE` to `'GOOGLE_SHEETS'`
   - Set `SHEET_ID` to your Google Sheet ID
   - Set `SHEET_NAME` to the name of your sheet (usually "Sheet1")

### Airtable Setup

1. Create an Airtable base with a table containing the following fields:
   - TIME
   - SPEAKER
   - ROOM
   - STATUS (values should be: OPEN, CLOSING, or CLOSED)

2. Get your Airtable API key:
   - Go to your Airtable account
   - Go to Account > API
   - Generate an API key if you don't have one

3. Get your Airtable Base ID:
   - Go to https://airtable.com/api
   - Select your base
   - The Base ID is in the URL and documentation

4. Update the configuration in `index.html`:
   - Set `DATA_SOURCE` to `'AIRTABLE'`
   - Set `API_KEY` to your Airtable API key
   - Set `BASE_ID` to your Airtable Base ID
   - Set `TABLE_NAME` to the name of your table

## Running the Application

Simply open the `index.html` file in a web browser, or host it on a web server.

## Configuration Options

You can modify the following settings in the `CONFIG` object in `index.html`:

- `DATA_SOURCE`: Choose between 'GOOGLE_SHEETS' or 'AIRTABLE'
- `REFRESH_INTERVAL`: How often to refresh the data (in milliseconds)

## Troubleshooting

- If using Google Sheets, make sure your sheet is published to the web and accessible to anyone with the link
- If using Airtable, ensure your API key has the correct permissions
- Check the browser console for any error messages