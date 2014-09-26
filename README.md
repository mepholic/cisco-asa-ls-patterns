This is a work in progress set of Logstash patterns for Cisco ASA syslog recognition.

Please feel free to help me add patterns to this.
Here are some resources that I've been using:
Complete list of Cisco Syslog codes and formats: http://www.cisco.com/c/en/us/td/docs/security/asa/syslog-guide/syslogs/logmsgs.html

The process of creating patterns can be tedious at times, but it pays off in the end :)

I'm currently struggling to find a way to aggregate the data to the smallest practical set of fields possible.
If anyone has any ideas to improve the field set, please let me know.

You can use the following command to check what fields the set of patterns will generate:
grep -Eo "%{[A-Z0-9_]+:[a-z_]+}" cisco-patterns/custom | sed -r 's/[%{}]//g' | cut -d':' -f2 | sort | uniq

I'm also not sure if there is a better way to do the logstash configuration. What I'm doing now works, but I'm not sure if it's the best way of accomplish what I'm attempting to achieve.
