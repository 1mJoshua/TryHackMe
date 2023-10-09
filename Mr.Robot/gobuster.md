# Gobuster
```bash
===============================================================
Gobuster v3.6
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.162.72/
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/dirb/wordlists/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.6
[+] Timeout:                 10s
===============================================================
Starting gobuster in directory enumeration mode
===============================================================
/.hta                 (Status: 403) [Size: 213]
/.htaccess            (Status: 403) [Size: 218]
/.htpasswd            (Status: 403) [Size: 218]
/0                    (Status: 301) [Size: 0] [--> http://10.10.162.72/0/]
/admin                (Status: 301) [Size: 234] [--> http://10.10.162.72/admin/]
/atom                 (Status: 301) [Size: 0] [--> http://10.10.162.72/feed/atom/]
/audio                (Status: 301) [Size: 234] [--> http://10.10.162.72/audio/]
/blog                 (Status: 301) [Size: 233] [--> http://10.10.162.72/blog/]
/css                  (Status: 301) [Size: 232] [--> http://10.10.162.72/css/]
/dashboard            (Status: 302) [Size: 0] [--> http://10.10.162.72/wp-admin/]
/favicon.ico          (Status: 200) [Size: 0]
/feed                 (Status: 301) [Size: 0] [--> http://10.10.162.72/feed/]
/image                (Status: 301) [Size: 0] [--> http://10.10.162.72/image/]
/Image                (Status: 301) [Size: 0] [--> http://10.10.162.72/Image/]
/images               (Status: 301) [Size: 235] [--> http://10.10.162.72/images/]
/index.html           (Status: 200) [Size: 1188]
/index.php            (Status: 301) [Size: 0] [--> http://10.10.162.72/]
/js                   (Status: 301) [Size: 231] [--> http://10.10.162.72/js/]
/intro                (Status: 200) [Size: 516314]
/license              (Status: 200) [Size: 309]
/login                (Status: 302) [Size: 0] [--> http://10.10.162.72/wp-login.php]
/page1                (Status: 301) [Size: 0] [--> http://10.10.162.72/]
/phpmyadmin           (Status: 403) [Size: 94]
/rdf                  (Status: 301) [Size: 0] [--> http://10.10.162.72/feed/rdf/]
/readme               (Status: 200) [Size: 64]
/robots               (Status: 200) [Size: 41]
/robots.txt           (Status: 200) [Size: 41]
/rss                  (Status: 301) [Size: 0] [--> http://10.10.162.72/feed/]
/rss2                 (Status: 301) [Size: 0] [--> http://10.10.162.72/feed/]
/sitemap              (Status: 200) [Size: 0]
/sitemap.xml          (Status: 200) [Size: 0]
/video                (Status: 301) [Size: 234] [--> http://10.10.162.72/video/]
/wp-admin             (Status: 301) [Size: 237] [--> http://10.10.162.72/wp-admin/]
/wp-config            (Status: 200) [Size: 0]
/wp-content           (Status: 301) [Size: 239] [--> http://10.10.162.72/wp-content/]
/wp-cron              (Status: 200) [Size: 0]
/wp-includes          (Status: 301) [Size: 240] [--> http://10.10.162.72/wp-includes/]
/wp-links-opml        (Status: 200) [Size: 227]
/wp-load              (Status: 200) [Size: 0]
/wp-login             (Status: 200) [Size: 2606]
/wp-mail              (Status: 500) [Size: 3064]
/wp-settings          (Status: 500) [Size: 0]
/wp-signup            (Status: 302) [Size: 0] [--> http://10.10.162.72/wp-login.php?action=register]
/xmlrpc               (Status: 405) [Size: 42]
/xmlrpc.php           (Status: 405) [Size: 42]
Progress: 4614 / 4615 (99.98%)
===============================================================
Finished
===============================================================
```