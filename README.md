# splunk-soc-practice

## Splunk SOC Analyst Lab

### Goal

This lab was created to practice Splunk SPL using simulated Linux and web server logs. The focus was on detecting authentication failures, analyzing web traffic, enriching logs with geolocation, and building SOC-style visualizations.

---

## SPL Commands Used

### Authentication & Brute Force Detection
source="secure.log" "Failed password" | stats count by user
source="linux_secure" ("root" OR "admin") "Failed password"

### Web Log Analysis
host="nginx" | stats count by clientip
source="access.log" | timechart count
source="access.log" | iplocation clientip | timechart count by Country

### Threat Hunting / Top Attackers
source="linux_secure" | top src
source="secure.log" signature="Failed password" | top src

---

## Visualizations

Screenshots for each SPL query are included in the repository, along with charts showing:

* Failed login activity over time
* Top attacker IP addresses
* Geographic distribution of events
* Web traffic trends

---

## Skills Practiced & Achievements

* SPL searching and filtering
* Brute force detection techniques
* Log enrichment using iplocation
* Traffic analysis and anomaly identification
* Building security-focused dashboards
* Learned to create **new alerts** based on SPL queries
* Gained a little hands-on experience with SOC-style monitoring

This project demonstrates practical Splunk usage for security monitoring and basic threat hunting.  

> **Note:** Please find screenshots and visual charts in the **`splunk (SIEM) LAB`** folder.
