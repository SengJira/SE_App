# conference-companion
Companion app for EMC Australian SE Conference 2016

# SUMMARY
Flask web app with Redis backend and ECS S3 object store

# FUNCTIONALITY
* Displays the conference program
* Scrolls down the program to the last session before current time
* Allows attendees to review the different sessions in the conference
* It will preselect a specific sesson to review if session name is passed as a parameter
   * Use: build a QR barcode pointing to a session and add it to the last page in the deck of that session
* Allows users to upload their favourite photos of the conference (restricted to jpg)
* Allows users to browse uploaded photos
* Allows event admins to dump all the reviews on CSV format for analysis

# REQUIREMENTS
* Cloud Foundry (the syntax to grab Redis credentials will work with CF environment variables)
* Flask directories
   * static (contains style.css, logo.png and backgr.jpg)
   * templates
   * uploads (photos get uploaded and thumbnailed here , before sending to ECS)
* Environment variables (set them up in Cloud Foundry)
   * ECS_host (if you don't have one, you can test "object.ecstestdrive.com")
   * ECS_access_key
   * ECS_secret
   * bucket (the name of the ECS bucket)
* Redis instance in Cloud Foundry
* sessions.txt file contains details about each session in the conference
   * Fields are separated by ";" so that you can use commas in the event description

Enjoy

