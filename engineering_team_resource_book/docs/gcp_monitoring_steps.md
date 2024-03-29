# Setting Up GCP Monitoring 

## 1. Setting Up a Notifications Channel
- In order to be able to set alert conditions, you must first set up a notifications channel for those alerts. Do this by going [here](https://console.cloud.google.com/monitoring?_ga=2.154211320.1135228163.1672770768-27455422.1666893129) to monitoring, selecting a project, then clicking Alerting and then EDIT NOTIFICATION CHANNELS. 
- Under Slack, click Add New and allow access to your workspace. Make a channel in the Slack workspace for alerts. If it is a private channel, add the monitoring Slack app to it with `/invite @Google Cloud Monitoring`.
- Go back to the GCP console and finish setting up the channel by filling in the required description and adding the new Slack channel name. Once this is done, send the test notification to ensure that Slack and GCP have linked correctly and the notifications are appearing in the correct channel. Add an email under the Email section below Slack in the GCP as a backup.

## 2. Creating an Alerting Policy
- Now that we have a notification channel, we can create the alerting policy that uses it. There are two types of alerting policies, metrics and logs based alerting. Mertics based alerting monitors a metric like CPU usage, and sends an alert when it falls outside of whatever range you deem acceptable in the policy.  Logs based alerting sends an alert when a specific type of log/a log containing a specific message appears.
- We will only cover setting up logs based alerting here, but if you want to set up a metrics-based alerting policy, the instructions to do so are [here](https://cloud.google.com/monitoring/alerts/using-alerting-ui).
- To set up a logs based alerting policy, go to the [Logs Explorer](https://console.cloud.google.com/logs?_ga=2.191922154.1135228163.1672770768-27455422.1666893129). Here, you can test querying the logs, which is how you build the conditions for your alert. The documentation for building a query is [here](https://cloud.google.com/logging/docs/view/logging-query-language).
- Once you have a query that gets the log type that you want to be alerted about, you can turn that into an alerting policy by clicking Create alert in the bar above the histogram. Give your policy a descriptive name and documentation (this documentation is what appears as the header to the slack notifications recieve). 
- Next, paste your query into the text box where you define which log entries to alert on.
- Set your notification frequency/autoclose duration as desired, and then for who should be notified select your new Slack channel and your email as a backup.

## 3. Testing the Alerts
- To test your policy, create a JSON request body from the example [here](https://cloud.google.com/logging/docs/alerting/log-based-alerts#lba-test) that fulfils your alert policy conditions. For example, if I had a policy that alerted when an error log appeared in my project, I would replace the project ID as shown, and change the "severity" field to "ERROR".  Upload this test log with the Try this method function in the log entries explorer [here](https://cloud.google.com/logging/docs/reference/v2/rest/v2/entries/write).
- This log, if uploaded with the correct conditions, should trigger the Slack being sent. It will also open an 'incident' and email you, so even if your Slack integration is not set up correctly, you should be able to see if it worked.
:::{admonition} Note
The minimum time between alerts is 5 minutes, and it's automatically set to 1 day between alerts, so if you forget to change this or attempt to test a sending a notification less than 5 minutes after one was sent sucessfully, you will not recieve another Slack. This isn't a bug on your end, it's just one aspect of the GCP notifications. You can change the alert window by clicking the edit button next to Policy details and changing the Time Between Notifications.
:::