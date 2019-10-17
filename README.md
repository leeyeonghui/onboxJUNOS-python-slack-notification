# onboxJUNOS-python-slack-notification

script directory:  /var/db/scripts/op

#Junos commands to be configured 
set system scripts language python
set system scripts op allow-url-for-python
set system scripts op file commit_slack.py
set system services netconf ssh

set event-options policy Junos-Slack events UI_COMMIT_COMPLETED
set event-options policy Junos-Slack then execute-commands commands "op commit_slack"
