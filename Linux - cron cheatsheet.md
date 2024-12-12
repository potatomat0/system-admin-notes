---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: December
day: 11
creation date: 2024-12-11 09:28
modification date: Wednesday 11th December 2024 09:28:00
---

#linux #selflearn 
## Article link:

_____
## Content

### Format

```
Min  Hour Day  Mon  Weekday
```

```
*    *    *    *    *  command to be executed
┬    ┬    ┬    ┬    ┬
│    │    │    │    └─  Weekday  (0=Sun .. 6=Sat)
│    │    │    └──────  Month    (1..12)
│    │    └───────────  Day      (1..31)
│    └────────────────  Hour     (0..23)
└─────────────────────  Minute   (0..59)
```

### Operators

|   |   |
|---|---|
|`*`|all values|
|`,`|separate individual values|
|`-`|a range of values|
|`/`|divide a value into steps|

### Special strings

|   |   |
|---|---|
|`@reboot`|every rebot|
|`@hourly`|once every hour - same as `0 * * * *`|
|`@daily`|once every day - same as `0 0 * * *`|
|`@midnight`|once every midnight - same as `@daily`|
|`@weekly`|once every week - same as `0 0 * * 0`|
|`@monthly`|once every month - same as `0 0 1 * *`|
|`@yearly`|once every year - same as `0 0 1 1 *`|

### Examples

|   |   |
|---|---|
|`0 * * * *`|every hour|
|`*/15 * * * *`|every 15 mins|
|`0 */2 * * *`|every 2 hours|
|`0 18 * * 0-6`|every week Mon-Sat at 6pm|
|`10 2 * * 6,7`|every Sat and Sun on 2:10am|
|`0 0 * * 0`|every Sunday midnight|

### Crontab

```bash
# Adding tasks easily
echo "@reboot echo hi" | crontab

# Open in editor - optional for another user
crontab -e [-u user]

# List tasks - optional for another user
crontab -l [-u user]

# Delete crontab file - optional for another user
crontab -r [-u user]
```

## Getting started 

[Crontab Explained in Linux \[With Examples\]](https://linuxhandbook.com/crontab/)

## How to Add/Update Crontab

Crontab files are typically stored in the /etc/cron.d/ directory on Linux systems. The crontab command can be used to edit the crontab file.

```
crontab -e 
```

By default, it will edit the crontab entries of the currently logged-in user. To edit other user crontab use the command below:

```
crontab -u username -e 
```

Change the **EDITOR** environment variable to change your default editor.

## How to List Crontab

To view the crontab entries of current users use the following command.

```
crontab -l 
```

Use -u followed by the username to view the crontab entries of the specified user.

```
crontab -u username -l 
```

## 20 Useful Examples for Scheduling Crontab

Here is the list of examples for scheduling cron jobs in a Linux system using crontab.

##### - Schedule a cron to execute at 2 am daily.

This will be useful for scheduling database backups on a daily basis.

0 2 * * * bash /script/backup.sh

- Asterisk (*) is used for matching all the records.

##### - Schedule a cron to execute twice a day.

The below example command will execute at 5 AM and 5 PM daily. You can specify multiple time stamps by comma-separated.

0 5,17 * * * /scripts/script.sh

##### - Schedule a cron to execute every minute.

Generally, we don’t require any script to execute every minute but in some cases, you may need to configure it.

* * * * *  /scripts/script.sh

##### - Schedule a cron to execute every Sunday at 5 PM.

This type of cron is useful for doing weekly tasks, like log rotation, etc.

0 17 * * sun  /scripts/script.sh

##### - Schedule a cron to execute every 10 minutes.

If you want to run your script at 10 minutes intervals, you can configure it like the below. These types of crons are useful for monitoring.

*/10 * * * * /scripts/monitor.sh

***/10:** means to run every 10 minutes. Same as if you want to execute on every 5 minutes use */5.

##### - Schedule a cron to execute on selected months.

Sometimes we are required to schedule a task to be executed for selected months only. Below example script will run in January, May, and August months.

* * * jan,may,aug *  /script/script.sh

##### - Schedule a cron to execute on selected days.

If you required scheduling a task to be executed for selected days only. The below example will run on each Sunday and Friday at 5 PM.

0 17 * * sun,fri  /script/script.sh

##### - Schedule a cron to execute on the first Sunday of every month.

To schedule a script to execute a script on the first Sunday only is not possible by time parameter, But we can use the condition in command fields to do it.

0 2 * * sun  [ $(date +%d) -le 07 ] && /script/script.sh

##### - Schedule a cron to execute every four hours.

If you want to run a script on 4 hours intervals. It can be configured like below.

0 */4 * * * /scripts/script.sh

##### - Schedule a cron to execute twice every Sunday and Monday.

To schedule a task to execute twice on Sunday and Monday only. Use the following settings to do it.

0 4,17 * * sun,mon /scripts/script.sh

##### - Schedule a cron to execute every 30 Seconds.

To schedule a task to execute every 30 seconds is not possible by time parameters, But it can be done by scheduling the same cron twice as below.

* * * * * /scripts/script.sh
* * * * *  sleep 30; /scripts/script.sh

##### - Schedule multiple tasks in a single cron.

To configure multiple tasks with a single cron Can be done by separating tasks by the semicolon ( ; ).

* * * * * /scripts/script.sh; /scripts/scrit2.sh

##### - Schedule tasks to execute yearly ( @yearly ).

**@yearly** timestamp is similar to “**0 0 1 1 ***“. It will execute a task on the first minute of every year, It may useful to send new year greetings 🙂

@yearly /scripts/script.sh

##### - Schedule tasks to execute monthly ( @monthly ).

**@monthly** timestamp is similar to “**0 0 1 * ***“. It will execute a task in the first minute of the month. It may useful to do monthly tasks like paying the bills and invoicing to customers.

@monthly /scripts/script.sh

##### - Schedule tasks to execute Weekly ( @weekly ).

A **@weekly** timestamp is similar to “**`0 0 * * sun`**“. It will execute a task in the first minute of the week. It may useful to do weekly tasks like the cleanup of the system etc.

@weekly /bin/script.sh

##### - Schedule tasks to execute daily ( @daily ).

**@daily** timestamp is similar to “**0 0 * * ***“. It will execute a task in the first minute of every day, It may useful to do daily tasks.

@daily /scripts/script.sh

##### - Schedule tasks to execute hourly ( @hourly ).

**@hourly** timestamp is similar to “**0 * * * ***“. It will execute a task in the first minute of every hour, It may useful to do hourly tasks.

@hourly /scripts/script.sh

##### - Schedule tasks to execute on system reboot ( @reboot ).

**@reboot** is useful for those tasks which you want to run on your system startup. It will be the same as system startup scripts. It is useful for starting tasks in the background automatically.

@reboot /scripts/script.sh

##### - Redirect Cron Results to a specified email account.

By default, cron sends details to the current user where cron is scheduled. If you want to redirect it to your other account, can be done by setup the MAIL variable like below

```
crontab -l 
```

##### - Take a backup of all cron to a plain text file.

I recommend keeping a backup of all jobs entry in a file. This will help you to recover cron in case of accidental deletion.

**Check current scheduled cron:**

```
crontab -l 
```

**Backup cron to text file:**

crontab -l > cron-backup.txt
cat cron-backup.txt
MAIL=rahul
0 2 * * * /script/backup.sh

**Removing current scheduled cron:**

crontab -r
crontab -l
no crontab for root

**Restore crons from text file:**

crontab cron-backup.txt
crontab -l
MAIL=rahul
0 2 * * * /script/backup.sh