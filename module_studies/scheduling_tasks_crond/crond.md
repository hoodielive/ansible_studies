# Schedule tasks with the cron and at modules:

The cron module - manage cron.d and crontab entries.

```yaml
---
- name: show options for the cron module
  cron:
    name: "Job_Name"
    special_time: reboot|daily|weekly|etc.
    minute: 0-59|*|*/2
    hour: 0-23|*|*/2
    day: 1-31|*|*/2
    month: 1-12|*|*/2
    weekday: 0-6 for Sunday to Saturday|*
    user: user_name
    cron_file: file_name
    state: present
    job: command
```
