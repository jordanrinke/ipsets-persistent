ipsets-persistent
=================

init.d script for iptables-persistent on Debian/Ubuntu that also saves/loads IP sets.

I added checking for and saving IP sets. Sets are saved in the same place as other rules in a file named `rules.ipset`. Sets are only saved if they are defined, same with flushing and loading. Instead of checking to see if the module is loaded at load time, I just check for the `rules.ipset` file, since if that doesn't exist loading the module does't make sense. There might be better ways to do it, feel free to submit a pull request. This is just the way I made it work for me.

Added `10-ipset`, which goes into `/usr/share/netfilter-persistent/plugins.d/` to enable IP sets handling for the newer netfilter-presistent package on Debian Jessie.
