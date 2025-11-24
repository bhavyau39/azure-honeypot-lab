
# Azure Honeypot Lab — KQL Queries

This repo contains KQL queries used in my Azure honeypot SOC lab experiment.  
The lab uses a deliberately exposed Windows VM with RDP open, logs flowing into Microsoft Sentinel, and geolocation enrichment via a custom watchlist.

## Queries

- `failed-logons.kql`: Filters EventID 4625 (failed logons) from SecurityEvent table.
- `geoip-lookup.kql`: Displays contents of the geoip watchlist (IP → location mapping).
- `geoip-join.kql`: Joins failed logons with geolocation data for analysis.

## How to Use

1. Import your geoip CSV as a Sentinel watchlist named `geoip`.
2. Run these queries in the Logs blade of Microsoft Sentinel.
3. Use map visualization to plot attacker IPs by location.

⚠️ This lab is intentionally insecure. Use only in a throwaway Azure subscription.
