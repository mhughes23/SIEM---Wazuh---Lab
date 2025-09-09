# Project 1: SIEM Deployment with Wazuh

## Overview
I deployed a Wazuh SIEM on Ubuntu using UTM, connected a macOS agent, and verified log collection.

## Architecture
- Ubuntu VM (Wazuh Manager + Dashboard + Indexer via Docker)
- macOS Agent
- Logs collected: SSH activity, system events, file changes

## Steps Taken
1. Installed Wazuh single-node deployment on Ubuntu
2. Installed Wazuh agent on macOS and connected it to manager
3. Verified log collection in Wazuh Dashboard

## Screenshots
- Dashboard login page
- Connected agents list
- Example security alert (failed SSH login)

## Skills Demonstrated
- SIEM deployment
- Agent configuration
- Log analysis
- SOC workflow simulation
