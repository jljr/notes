**How To Upgrade Splunk**

- Start Download
- On next page on right is WGET command - copy the link
- Log onto Linux box
- Goto the tmp folder - `cd /tmp`
- Download the upgrade - type `wget {paste the WGET URL}`
- Stop Splunk - type `./opt/splunk/bin/splunk stop`
- Run the installer - type `dpkg -i splunk-4.2.4-110225-linux-2.6-amd64.deb`
