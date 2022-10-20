# Apache/PHP Security Files
.ini and .conf files to add some additional security to the PHP and Apache configurations. Recommendations taken from both [OWASP](https://cheatsheetseries.owasp.org/) and [Security Headers](https://securityheaders.com/).
## Usage
Depending on your server setup, you can copy/paste the contents of the security.ini file into your php.ini file and copy/paste the contents of the security.conf file into your httpd.conf file.

Alternatively if you have **Additional Configuration Files** set up then you can just add the files to the correct directories.
## File Notes
### security.conf
**Header set X-Frame-Options** - By using **set** and not **always set**, you are able to overwrite this with the .htaccess file incase certain areas of your system need to be loaded into iframes.

**Header always set Permissions-Policy** - Your settings may vary here depending on whether you need to use geolocation, etc.
### security.ini
**disable_functions** - Your settings may vary here depending on your usage; there may be functions you need to use (in which case remove them) or there may be others that you can block.

**session.cookie_samesite** - If your system is writing to a session directly from an external link (if you are resuming a previous lead, etc), you may need to disable this.

**xPoweredByHeader** - If you are using a control panel such as Plesk then this may not work as it will be overwritten by Plesks own config files. You will have to disable it there as well.
