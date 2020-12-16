## Advent of code
Website containing fun coding challenges.

1. Choose one task, [aoc 3](https://adventofcode.com/2020/day/3), [aoc 8](https://adventofcode.com/2020/day/8)
1. Choose your language of choice
1. Lets solve it together

## Create an Ansible module
We deploy our services using Ansible. Each service runs on a number of virtual machines, each with a unique name (starting with 'vm' in the example file below). We use DNS CNAMES to identify the differnt parts of the service. The Ansible inventory file of a service contains all of the CNAMEs that make up the particular service. The inventory file below is an example of our Monitoring service, which contains components Loki, Grafana and Prometheus. To ensure that we comply with our internal CNAME naming standard we would like an Ansible module that checks the CNAMEs in the intenvory file, namely:

CNAMES follow standard ```<x>.<y>.<z>.swf.autoheim.net```
Each CNAME entry is valid, i.e ```dig``` on each CNAME succeeds

Create an initial version of that module and a naive playbook that can be used to test it. Store the code in a Git repo.

## Upgrade java version of Gerrit image to a -devel version
In the team we are responsible for providing Gerrit to all developers at Zenseact. We run gerrit using Docker and the image is based on ```https://hub.docker.com/r/gerritcodereview/gerrit/dockerfile``` image ```gerritcodereview/gerrit:2.16.13```. We are experiencing some strange behavior in Gerrit and require tools to execute stack traces (jstack) to debug the issue further. The default Java version installed does not have these tools so you are tasked to install (at the time of writing) ```java-1.8.0-openjdk-devel-1.8.0.272.b10```

A consequence of using this version of java is that we need to detect if that version is no longer available so we can update to use another one later on.

Add any code to a Git repo.
