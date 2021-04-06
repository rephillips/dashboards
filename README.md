# dashboards
Install these views onto the Monitoring Console inside the monitoring console app.


view: support_hec.xml

requires: lookup file HEC_reply_codes, (create HEC_reply_codes.csv from github raw view, save as HEC_reply_codes.csv to your desktop)

1.) add lookup file to MC instance:
on Monitoring Console > Settings > Lookups > Lookup table files > + Add new
Destination app: splunk_monitoring_console
Browse: locate the HEC_reply_codes.csv
Destination filename: HEC_reply_codes
Save

2.) create lookup definition:
on Monitoring Console > Settings > Lookups > Lookup Definitions > + Add new
Destination app: splunk_monitoring_console
Name: HEC_reply_codes
Type: File-based
Lookup File: HEC_reply_codes
Save

set sharing permissions for lookup file and lookup definition from "private" to "app" 

Test its working: 
|inputlookup HEC_reply_codes
