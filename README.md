DionaeaFR
=========

Front Web to Dionaea low-interaction honeypot.
Home DionaeaFR: http://rubenespadas.github.io/DionaeaFR/
Home Dionaea:   http://dionaea.carnivore.it/

[*] Technologies:

  - Python 2.7.13
  - Django 1.11.18
  - Jquery 1.7.2
  - Bootstrap Framework 2.1.1
  - jVectorMap 1.0
  - Kendo-UI v2011.3.1129
  - SQLite3

[*] Installation:

	- With your distro's package manager install the packages:
		nodejs, gcc & python2-pip
		(with Debian derivatives install 'python-pip' instead)

	- Download GeoIP and GeoLiteCity and gunzip to ./DionaeaFR/static:
		curl https://src.fedoraproject.org/lookaside/pkgs/GeoIP/GeoLiteCity.dat.gz/2ec4a73cd879adddf916df479f3581c7/GeoLiteCity.dat.gz | gunzip > ./DionaeaFR/static/GeoLiteCity.dat
		curl https://src.fedoraproject.org/lookaside/pkgs/GeoIP/GeoIP.dat.gz/508e3c10da15f2722774cf4014863976/GeoIP.dat.gz | gunzip > ./DionaeaFR/static/GeoIP.dat

	- Running a honeypot as root is not advised. Create an unprivileged user and change ownership & group of this git directory to that user:
		useradd <user>
		chown <user>:<user> -R <path>/DionaeaFR
		su <user>

	- With pip2 (as the unprivileged user):
		pip2 install --user -r requirements.txt

[*] Run server:

	Copy DionaeaFR/settings.py.dist to DionaeaFR/settings.py and configure it (mainly ALLOWED_HOSTS and DATABASE->NAME).
	python2 manage.py collectstatic
	python2 manage.py runserver 0.0.0.0:8000
	Access to http://YOUR_IP:8000 in browser.

[*] Changelog:

  27/01/2019
	- Forked & addressed multiple deprecated functions used by DionaeaFR (Special thanks to 'Dependency Hell™').  

  30/11/2012
	- Add transport, type and protocol filters in connections table.
	- Add Attacks graph last 7 days.
  
  29/11/2012
	- Add less support
	- Add HTML minify
	- Add menu icons
	- Other visuals changes
	
  18/12/2012
	- Add home panel

  20/12/2012
	- Add country name in tooltips
	- Add Top 10 Ports Graph
	- Add ANTIVIRUS_VIRUSTOTAL variable in settings.py
	- Deactive minify by default
	- Restructure directories
	- Fixed Graphs
  
  15/05/2013
	- Refactoring Code
	- New filters system

  16/05/2013
	- Fixed mysql_command.
	- Add refresh interval in graphs.

[*] Suggestions? 
    (harryharryharry: Please for the love of all that is holy - no suggestions, as I'm wholly incapable of implementing them.)

Designed by @rubenespadas
