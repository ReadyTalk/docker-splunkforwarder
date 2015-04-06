# docker-splunkforwarder
Simple splunk forwarder utilizing runtime templates (reefer) to configure the Splunk agent. It's currently somewhat limited in that it will only log one file glob pattern and send it to a single index. We could extend the idea to support multiple file globs sending to multiple indexes.

## Required Env variables
* SPLUNK_SERVER - Server FQDN/IP to send logs.
* SPLUNK_SERVER_PORT - Port on the above server.
* SPLUNK_LOGFILE_PATTERN - Glob pattern (or regex but this is not tested) for files to monitor.
* SPLUNK_INDEX - Splunk index to send log entries to.

## Example run:
docker run -d -e SPLUNK_SERVER=splunk.localhost -e SPLUNK_SERVER_PORT=9500 -e 'SPLUNK_LOGFILE_PATTERN=/var/log/*.log' -e SPLUNK_INDEX=prod_idx readytalk/splunkforwarder
