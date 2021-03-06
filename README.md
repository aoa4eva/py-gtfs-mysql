#  GTFS MySQL IMPORT SCRIPT

#### Author: Tom Lee (thomas.j.lee@gmail.com)
#### Modified for Montgomery County by: Afua Ankomah (hi@aoa4eva.me) 
##### Latest modifications using Montgomery County GTFS files from: 
##### http://www.montgomerycountymd.gov/DOT-Transit/GTFS/GTFSfiles.html
---
- This is a simple set of scripts that will import a GTFS dataset into a lightweight MySQL database.  The work is based on Washington, DC's WMATA GTFS dataset, but is being modified specifically for Montgomery County's GTFS dataset. 

- In addition to the GTFS fields, a number of columns have been created to assist in the conversion of GTFS's string-based date/time representations to more useful Unix timestamp-style second counts.
---
DEAD-SIMPLE USAGE:

1. Create a database, e.g. CREATE DATABASE MOCOGTFS

2. Run table creation scripts against the database:

	cat sql/*.sql | mysql -p -u USERNAME -h HOST -D mocogtfs
	
3. Edit settings.py with your mysql details.

4. Put your GTFS files into the gtfs/ folder

5. Run the import script:

	python load_gtfs.py
	
6. Run the time index creation script:

	python build_indices.py
	
7. Build something neat

This is a simple site developed to showcase the data retrieved from the Montgomery County MD website.
