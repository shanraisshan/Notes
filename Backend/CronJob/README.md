# Cron Job

> A time-based task scheduler in Unix/Linux that automatically runs commands or scripts at specified intervals

## ELI5

Term|Analogy
:-:|:-:
Cron Job|An alarm clock that does a chore for you when it rings
Crontab|The list of alarms you've set
Cron Daemon|The clock on the wall that's always ticking and checking
Schedule Expression|The time you set on the alarm (e.g., every morning at 7)
`* * * * *`|Five dials on the alarm: minute, hour, day, month, weekday

## Crontab Syntax

```
┌───────────── minute (0-59)
│ ┌───────────── hour (0-23)
│ │ ┌───────────── day of month (1-31)
│ │ │ ┌───────────── month (1-12)
│ │ │ │ ┌───────────── day of week (0-6, Sun=0)
│ │ │ │ │
* * * * *  command_to_run
```

## Common Examples

Expression|Meaning
:-:|:-:
`0 9 * * *`|Every day at 9:00 AM
`*/5 * * * *`|Every 5 minutes
`0 0 * * 0`|Every Sunday at midnight
`30 8 1 * *`|8:30 AM on the 1st of every month
`0 0 1 1 *`|Once a year on Jan 1st at midnight

## Common Commands

Command|Description
:-:|:-:
`crontab -e`|Edit your crontab
`crontab -l`|List your scheduled jobs
`crontab -r`|Remove all your cron jobs

## Special Strings

String|Equivalent
:-:|:-:
`@reboot`|Run once at startup
`@daily`|`0 0 * * *`
`@weekly`|`0 0 * * 0`
`@monthly`|`0 0 1 * *`
`@yearly`|`0 0 1 1 *`

## Use Cases

- Log rotation and cleanup
- Database backups
- Sending scheduled emails or reports
- Syncing data between services
- Health checks and monitoring
