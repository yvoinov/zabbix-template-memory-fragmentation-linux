# Linux memory fragmentation monitoring template for Zabbix
[![License](https://img.shields.io/badge/License-MIT--Clause-blue.svg)](https://github.com/yvoinov/zabbix-template-memory-fragmentation-linux/blob/main/LICENSE)
## Motivation

The template is designed as part of a deep monitoring system for the state of the system's RAM as a whole, as well as for performance optimization purposes.

Although this estimate is very rough, it corresponds to the dynamics of increasing swap space usage and, in general, fairly objectively reflects changes in the level of system memory fragmentation.

Unfortunately, due to system and security limitations, it is difficult or impossible to obtain a similar memory utilization breakdown in other operating systems.

The template is based on [this script](https://github.com/yvoinov/memory-tools/blob/main/mem_frag.sh), which was originally written by [Nick Parfenovich](https://github.com/bar0metr).

Note: Although the templates were developed for Zabbix 7.0, they will work on earlier versions as well. Just adjust the version in the template.

## Using template

Just put Linux_Memory_Fragmentation.conf to zabbix_agent.d (zabbix_agent2.d) or add file contents to zabbix_agent.conf (for older agents) and restart agent.

Then import template into Zabbix and apply to host(s).

### How to use

The template is used to plot graphs to monitor host fragmentation levels over time. Swapping levels can be overlaid on the graphs to directly assess the degree of fragmentation and host health.

The template defines a trigger that fires as a warning when the fragmentation level exceeds 80%. Typically, at this level, sporadic swapping becomes continuous.
