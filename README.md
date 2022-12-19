# Router ping and notification in private messages via telegram bot

### Installation

1. Download the necessary files or clone this project anywhere.
```sh
$git clone https://github.com/dog1912/ping-and-notifications-to-telegram.git
```
2. Add your domain name or ip address for the router to the ping.sh and pinger.sh script files.

3. Edit the value of TOKEN and CHAT_ID to send a notification to telegram
```sh
TOKEN=Token bot from telegram
CHAT_ID=ID Admin
```
4. Add the task to the crontab with flock to prevent re-runs. Instead of /scripts/ you need to specify your path

```sh
*/1 * * * * flock -n /var/tmp/host1.lock -c "/scripts/ping.sh host1"  >/dev/null 2>&1
*/1 * * * * flock -n /var/tmp/host2.lock -c "/scripts/ping.sh host2"  >/dev/null 2>&1
```

### Feedback

Feel free to send bug reports and feature requests. If you are using this solution in production, please tell me to know it's being useful.
