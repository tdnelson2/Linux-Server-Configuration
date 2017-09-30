# Linux Server Configuration

## Connect
* Username: `grader`.
* SSH port: `2200`.
* IP address: `54.69.143.140`.
* SSH key is included in 'Notes to Reviewer'.

## Item Catalog Application
* App is live at [http://54.69.143.140/](http://54.69.143.140/).
  * Note: login using Google is not working since the Google API requires the url to end with `.com`, `.org` etc. Use Facebook login instead.
* App files are at `/var/www/html`
```
/var/www/html/
├── modules
├── static
│   ├── fonts
│   ├── images
│   ├── js
│   └── styles
└── templates
```
## Database
* Guest users have read-only privileges using `sudo psql -h localhost -d mydb -U catalog -p 5432`
* Password: `pw`

### Software Added
* Apache2 (apache2 libapache2-mod-wsgi).
* PostgreSQL (postgresql).
* Tree (tree) [to create that nifty folder stucture above]
* Python2 Package Manager (python-pip).
  * Flask (flask packaging oauth2client redis passlib flask-httpauth).
  * SQLAlchemy (sqlalchemy flask-sqlalchemy psycopg2 bleach requests).

### Configuration Changes
* Custom SSH keys for `student` and `grader`.
* Non-standard SSH port (`2200`).
* UFW firewall configured to deny incoming on all ports except `2200/tcp`, `80/tcp`, `123/udp`.
* Local timezone configured to UTC.