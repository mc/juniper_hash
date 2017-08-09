juniper_hash
============

simple ruby script to parse juniper router configuration into a nested hash

Usage: 

```ruby
require 'juniper_hash'
hash_config = JuniperHash.get_hash(File.open('juniper.conf').read)
text_config = JuniperHash.build_config_from_hash(hash_config)
JuniperHash.get_hash(text_config) == hash_config
=> true
```

simple oneliner to print a config as YAML file:
```ruby
ruby -ryaml -rjuniper_hash -I. -e 'puts JuniperHash.get_hash(ARGF.read).to_yaml' < firewall.configdump
```
