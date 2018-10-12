__Add an A Record to Windows DNS With Puppet Bolt__

This is a task that leverages Puppet Bolt to add an A record to Windows DNS. It was written to execute on the machine during provisioning, but should function from any host that has Puppet Bolt installed. 

Takes an input of Hostname, Zone, and IP address as inputs. Example is below 

__Running as a Script:__ 

bolt script run dns.ps1 Hostname='bolt1' Domain='domain.com' IP='xxx.xxx.xxx.xxx' --nodes winrm://dnsserver.domain.com --user adminuser --passwo
rd adminpass --no-ssl

__Running as a Task:__

bolt task run --nodes winrm://dnsserver.domain.com --user adminuser --password adminpass --no-ssl dns::dns hostname="bolt01" domain="domain.com" ip="xxx.xxx.xxx.xxx"
