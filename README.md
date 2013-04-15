Overview
--------
This repo will get you up and running with graphite with a vagrant image. To use follow the below steps:

$`git clone git://github.com/charliek/vagrant-graphite.git`

If you are on a 1.1.x vagrant verison go to:

$`cd vagrant-graphite/vagrant/1.1.x`

If you are on a 1.0.x vagrant verison go to:

$`cd vagrant-graphite/vagrant/1.0.x`

$`vagrant up`

Once this command completes you should be able to see your new vagrant install at http://192.168.33.10/ and can add new metrics as you would normally on the 192.168.33.10 host and 2003 port. For example to create a test metric you can do:

```
echo "local.random.diceroll 4 `date +%s`" | nc 192.168.33.10 2003;
```
The repo as is was tested with vagrant 1.1.5 and virtual box 4.1.12.

