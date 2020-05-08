---
layout: post
title: Download data from GES-DISC
categories: ACMG
---

Download your data using wget:

# wget for Windows

1) Make sure you have setup your Earthdata account.

2) Install wget if necessary. A version of wget 1.18 complied with gnuTLS 3.3.3 or OpenSSL 1.0.2 or LibreSSL 2.0.2 or later is recommended.

3) Create a cookie file. This file will let you download GES DISC resources without having to re-login.
- Open a run-command window by pressing WinKey + R

- Next, enter "cmd" in the text field and click "OK"

- Navigate to the directory you wish to create the cookies file in. In this guide, we place it under the C drive, but any directory will do. You can navigate to the C drive by entering `C:`

- Finally, enter `NUL > .urs_cookies`
  - Note: you may need to re-create .urs_cookies in case you have already executed `wget` without valid authentication.
  - Note: you can get 'Access denied' error. Enter 'dir' to verify that '.urs_cookies' file is listed in your directory.

4) Download your data using wget:

`
wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies --user=<your username> --ask-password --content-disposition <url>
`

- `--auth-no-challenge` may not be needed depending on your version of `wget`

- `<your username>` is the username belonging to your Earthdata account

- `<url>` is the link that points to a file you wish to download or to an OPeNDAP resource.

- Your Earthdata password might be requested on the first download

- If you wish to download an entire directory, such as this example URL, use the following command:
```
wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies -np -r --content-disposition <url>
```

To download multiple data files at once, create a plain-text `<url.txt>` file with each line containing a GES DISC data file URL. Then, enter the following command:
```
wget --load-cookies C:\.urs_cookies --save-cookies C:\.urs_cookies --auth-no-challenge=on --keep-session-cookies --user=<your username> --ask-password --content-disposition -i <url.txt>
```

# wget for Mac/Linux

1) Make sure you have setup your Earthdata account.

2) Install wget if necessary. A version of wget 1.18 complied with gnuTLS 3.3.3 or OpenSSL 1.0.2 or LibreSSL 2.0.2 or later is recommended.

3) Create a .netrc file in your home directory.
- `cd ~` or `cd $HOME`

- `touch .netrc`

- `echo "machine urs.earthdata.nasa.gov login <uid> password <password>" >> .netrc` (where <uid> is your user name and <password> is your Earthdata Login password without the brackets)
  
- `chmod 0600 .netrc` (so only you can access it)

4) Create a cookie file. This file will be used to persist sessions across calls to `wget` or `curl`.
- `cd ~` or `cd $HOME`

- `touch .urs_cookies`
  - Note: you may need to re-create .urs_cookies in case you have already executed wget without valid authentication.

5) Download your data using wget:
```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies --content-disposition <url>
```

- `--auth-no-challenge` may not be needed depending on your version of `wget`

- `<url>` is the link that points to a file you wish to download or to an OPeNDAP resource.

- Your Earthdata password might be requested on the first download

- If you wish to download an entire directory, such as this example URL, use the following command:
```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies -np -r --content-disposition <url>
```

To download multiple data files at once, create a plain-text `<url.txt>` file with each line containing a GES DISC data file URL. Then, enter the following command:

```
wget --load-cookies ~/.urs_cookies --save-cookies ~/.urs_cookies --auth-no-challenge=on --keep-session-cookies --content-disposition -i <url.txt>
```
