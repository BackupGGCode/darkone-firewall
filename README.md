#Darkone-firewall
Darkone Firewall is written in bash and uses iptables to make filtering.

It can have one or more configuration files and uses a specific syntax for rules definition. What Darkone Firewall is trying to offer is a simply as possible way to use iptables.

Example of rules definision:

any:10.2.0.1:WAN:FORWARD: tcp|22,25,80,443; udp|53:ACCEPT


Darkone Firewall is modular. That means a new module (for example qos, mark ... etc) can be added. For more information please read the README.txt and Release\_Notes.txt files.

Darkone Firewall is released under the GPL v3 License.
