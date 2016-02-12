**How To Upgrade Splunk**

- Start Download from http://10.1.2.134:8000 - You will need a Splunk account to do this
- Click on the x64 *.deb link 
- On next page, cancel the download and on right is WGET command - copy the link
- Log onto Linux box - `ssh 10.1.2.134`
- Change to su - `sudo su`
- Goto the tmp folder - `cd /tmp`
- Download the upgrade - paste the WGET command copied from the Splunk page
- After download complete, stop Splunk - type `cd /opt/splunk/bin` then type `./splunk stop`
- Run the installer - type `cd /tmp` then `dpkg -i splunk-XXXXXX.deb`
- Start Splunk - type `cd /opt/splunk/bin` then type `./splunk start`
- Scroll to the end of the License Agreement and type `y`
- Splunk will prompt:
```
Splunk has detected an older version of Splunk installed on this machine. To
finish upgrading to the new version, Splunk's installer will automatically
update and alter your current configuration files. Deprecated configuration
files will be renamed with a .deprecated extension.

You can choose to preview the changes that will be made to your configuration
files before proceeding with the migration and upgrade:

If you want to migrate and upgrade without previewing the changes that will be
made to your existing configuration files, choose 'y'.
If you want to see what changes will be made before you proceed with the
upgrade, choose 'n'.


Perform migration and upgrade without previewing configuration changes? [y/n]
```
- Type `y`
- Splunk will start installing and you should see something like this when it is done:
```
Checking prerequisites...
	Checking http port [8000]: open
	Checking mgmt port [8089]: open
	Checking appserver port [127.0.0.1:8065]: open
	Checking kvstore port [8191]: open
	Checking configuration...  Done.
	Checking critical directories...	Done
	Checking indexes...
		Validated: _audit _internal _introspection _thefishbucket history main perfmon summary windows wineventlog
	Done
	Checking filesystem compatibility...  Done
	Checking conf files for problems...
	Done
	Checking default conf files for edits...
	Validating installed files against hashes from '/opt/splunk/splunk-6.3.3-f44afce176d0-linux-2.6-x86_64-manifest'
	All installed files intact.
	Done
All preliminary checks passed.

Starting splunk server daemon (splunkd)...
Done


Waiting for web server at http://127.0.0.1:8000 to be available.... Done


If you get stuck, we're here to help.
Look for answers here: http://docs.splunk.com

The Splunk web interface is at http://smithossec.smithsport.com:8000
````
- Verify that the upgrade was succussful by going to [http://10.1.2.134:8000/]
