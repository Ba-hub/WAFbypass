# WAFbypass
Bypass firewalls via DNS history


Clone the repositories & run ./WAFbypass.sh

Need to install jq ( apt install jq )


This script will try to find:

The direct IP address of a server behind a firewall like Cloudflare, Incapsula, SUCURI ...
an old server which still running the same (inactive and unmaintained) website, not receiving active traffic because the A DNS record is not pointing towards it. Because it's an outdated and unmaintained website version of the current active one, it is likely vulnerable for various exploits. It might be easier to find SQL injections and access the database of the old website and abuse this information to use on the current and active website.
This script (ab)uses DNS history records. This script will search for old DNS A records and check if the server replies for that domain. It also outputs a confidence level, based on the similarity in HTML response of the possible origin server and the firewall.

