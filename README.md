# docker-splunkforwarder
Simple splunk forwarder utilizing runtime templates (reefer) and docker

1)  Required Env variables
  SPLUNK_SERVER
  SPLUNK_SERVER_PORT
  SPLUNK_LOGFILE_PATTERN
  SPLUNK_INDEX


docker run -d -e SPLUNK_SERVER=splunk.localhost -e SPLUNK_SERVER_PORT=9500 -e 'SPLUNK_LOGFILE_PATTERN=/var/log/*.log' -e SPLUNK_INDEX=prod_idx readytalk/splunkforwarder
