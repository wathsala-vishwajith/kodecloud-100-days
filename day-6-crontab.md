## Cron Job Setup and Testing Guide

Step 1: install cronie

`sudo dnf install cronie -y`

Step 2: Enable and Start the crond service
```
sudo systemctl enable crond
sudo systemctl start crond
sudo systemctl status crond
```

The output should show Active: active (running).

` */5 * * * * command` needs to be added to the root user's crontab, meaning it will execute every five minutes.

Step 1: Edit the root user's crontab. We will use the crontab -e command with sudo to edit the root user's cron jobs.

`sudo crontab -e`

Step 2: Insert the Cron Job LineThis will open the root user's crontab file in a text editor (usually vi or nano). Append the following line to the end of the file:

`*/5 * * * * echo hello > /tmp/cron_text`

Explanation of the cron entry:*/5: 
Executes every 5 minutes (i.e., at 0, 5, 10, 15, ..., 55 past the hour).

\*: Executes every hour.

\*: Executes every day of the month.*: Executes every month.

\*: Executes every day of the week.

echo hello > /tmp/cron_text: The command to run.

Save and close the file. 

Step 3: Verify the Crontab EntryYou can check the root user's crontab list to ensure the entry was added correctly:

`sudo crontab -l`
