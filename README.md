# SaltStack

Install

https://docs.saltstack.com/en/latest/topics/tutorials/salt_bootstrap.html#salt-bootstrap

curl -o bootstrap-salt.sh -L https://bootstrap.saltstack.com
sudo sh bootstrap-salt.sh -M stable   # Master

vim /etc/minion     # Minion conf. file
master: localhost   # Uncomment master string

systemctl restart salt-master
systemctl restart salt-minion

salt-call --local state.apply

salt '*' test.ping

salt '*' state.highstate

salt-key -L   # List key request
salt-key -A   # Key add
