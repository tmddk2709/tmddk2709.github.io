Download your data using wget:
wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies --user=<your username> --ask-password --content-disposition <url>

--auth-no-challenge may not be needed depending on your version of wget
<your username> is the username belonging to your Earthdata account
<url> is the link that points to a file you wish to download or to an OPeNDAP resource.
Your Earthdata password might be requested on the first download
If you wish to download an entire directory, such as this example URL, use the following command:
wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies -np -r --content-disposition <url>

To download multiple data files at once, create a plain-text <url.txt> file with each line containing a GES DISC data file URL. Then, enter the following command:

wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies --user=<your username> --ask-password --content-disposition -i <url.txt>

Back to top

wget for Mac/Linux
Make sure you have setup your Earthdata account.
Install wget if necessary. A version of wget 1.18 complied with gnuTLS 3.3.3 or OpenSSL 1.0.2 or LibreSSL 2.0.2 or later is recommended.
Create a .netrc file in your home directory.
cd ~ or cd $HOME
touch .netrc
echo "machine urs.earthdata.nasa.gov login <uid> password <password>" >> .netrc (where <uid> is your user name and <password> is your Earthdata Login password without the brackets)
chmod 0600 .netrc (so only you can access it)
Create a cookie file. This file will be used to persist sessions across calls to wget or curl.
cd ~ or cd $HOME
touch .urs_cookies.
Note: you may need to re-create .urs_cookies in case you have already executed wget without valid authentication.
Download your data using wget:
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies --content-disposition <url>

--auth-no-challenge may not be needed depending on your version of wget
<url> is the link that points to a file you wish to download or to an OPeNDAP resource.
Your Earthdata password might be requested on the first download
If you wish to download an entire directory, such as this example URL, use the following command:
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies -np -r --content-disposition <url>

To download multiple data files at once, create a plain-text <url.txt> file with each line containing a GES DISC data file URL. Then, enter the following command:

wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies --content-disposition -i <url.txt>
