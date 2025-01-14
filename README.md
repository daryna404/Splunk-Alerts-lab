# Splunk-Alerts-lab

**Lab Review:** Monitoring and Alerting for Security and Performance Events in Splunk

**Objectives**

Develop search queries to identify critical security and performance events.

Create scheduled and real-time alerts to monitor and respond to system activities.

Implement throttling mechanisms to reduce alert fatigue.

Extract actionable insights from triggered alerts for improved incident response.

**Skills Learned**

Crafting precise search queries in Splunk for targeted monitoring.

Configuring scheduled and real-time alerts for different use cases.

Applying field-based throttling to optimize alerting systems.

Analyzing triggered alerts to identify root causes and affected components.

# **Task 1: Creating an Alert for SSH Login Failures**

**Overview:**

This task focused on detecting and alerting administrators about multiple failed SSH login attempts, which can indicate potential brute-force attacks or misconfiguration issues.

**Key Steps:**

Search Query Development:

Utilized the auth sourcetype.

Filtered events containing the string "failed" to identify unsuccessful SSH login attempts.

<img width="676" alt="image" src="https://github.com/user-attachments/assets/96dd9863-7c49-4980-b1e4-525216968bae" />


Scheduled Alert Creation:

Configured a scheduled alert titled ssh-failed with the following parameters:

<img width="620" alt="image" src="https://github.com/user-attachments/assets/df431325-25a6-48a5-ac30-5ef72f9ce585" />

**Outcome:**

The alert successfully identified bursts of failed SSH login attempts, providing actionable insights to respond proactively to potential security threats.

# Task 2: Creating a Real-Time Alert for HTTP 500 Internal Server Errors

**Overview:**

The second task aimed to catch internal server errors in real-time, enabling immediate troubleshooting of web application issues.

Key Steps:

Search Query Development:

Utilized the access_combined sourcetype.

Filtered events with the status code 500 to identify internal server errors.

![image](https://github.com/user-attachments/assets/ce70ff37-f12f-4f1a-a776-bd34c85ea2a5)


**Real-Time Alert Creation:**

Configured an alert titled http-500 with the following parameters:

<img width="574" alt="image" src="https://github.com/user-attachments/assets/a6dafe7d-a2f5-432c-bc14-cd79e1617125" />


Throttling:

Applied field-based throttling using the uri_path field.

<img width="434" alt="image" src="https://github.com/user-attachments/assets/9f3d5941-83db-4b81-9edb-a2427843e99f" />


Suppressed duplicate alerts for 10 minutes based on the same endpoint.

<img width="531" alt="image" src="https://github.com/user-attachments/assets/99fa35ad-e741-4b4b-9dc9-d1598b2ef579" />


Triggered Alerts:

Reviewed triggered alerts to extract actionable data:

![image](https://github.com/user-attachments/assets/38c78d1a-d32f-4afe-adb3-9ea92b0d2d56)

IP Address: Identified users causing 500 errors.

URI Path: Pinpointed the API endpoint responsible for the error.

<img width="796" alt="image" src="https://github.com/user-attachments/assets/73dcd534-bb57-4ce9-9067-a4871e9e91e9" />


**Outcome:**

The real-time alert enabled swift identification of problematic endpoints and user activity, reducing downtime and improving user experience.
