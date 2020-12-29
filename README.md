![GitHub last commit](https://img.shields.io/github/last-commit/ValentinNikolaev/multirbl-monitor)
![visitors](https://visitor-badge.laobi.icu/badge?page_id=ValentinNikolaev.multirbl-monitor)


# multirbl-monitor

Monitors multiple DNSRBLs and can send you an e-mail if your SMTP host is blacklisted.

```sh
usage: MultiRbl.php [-b -n -e -h=smtp.yourdomain.com] [--show-blacklists-only=y --no-color=y --email-if-bl=y --host=smtp.yourdomain.com]
```

### Installation & Usage


```sh
git clone https://github.com/deftx/multirbl-monitor
cd multirbl-monitor
composer install
```

Then, edit MultiRbl.php and change the e-mail settings to match your configuration.

### Install in a crontab
```
@hourly /usr/bin/php /path/to/multirbl/MultiRbl.php --host=smtp.yourhost.com -e > /dev/null 2>&1
```

### Sample output
```
----------------------------
Blacklist
----------------------------
URIBL black
http://www.uribl.com/
	Type: Blacklist
	Listed: YES

----------------------------
Combinedlist
----------------------------
Hostkarma
http://wiki.junkemailfilter.com/index.php/Spam_DNS_Lists
	Type: Combinedlist
	Listed: YES
	Status: neutral
	Description: Familiar domain (older than 10 days)

----------------------------
Infolist
----------------------------
Abuse.net
http://www.abuse.net/
	Type: Infolist
	Listed: YES

Total Blacklisted: 1
Total lists: 53
Number of blacklists domain is not listed on: 42
```
