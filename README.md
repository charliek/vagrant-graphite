Overview
--------
This repo will get you up and running with graphite in a vagrant image. To get started follow the below steps:

$`git clone git://github.com/charliek/vagrant-graphite.git`

If you are on a 1.1.x vagrant verison:

$`cd vagrant-graphite/vagrant/1.1.x`

If you are on a 1.0.x vagrant verison:

$`cd vagrant-graphite/vagrant/1.0.x`

Then no matter what your vagrant version:

$`vagrant up`

Once this command completes you should be able to see your new vagrant install at http://192.168.33.10/ and can add new metrics as you would normally on the 192.168.33.10 host and 2003 port. For example to create a test metric you can do:

```
echo "local.random.diceroll 4 `date +%s`" | nc 192.168.33.10 2003;
```

This repo was tested with vagrant 1.1.5 / virtual box 4.1.12, and vagrant 1.0.5 / virtual box 4.2.1 both on a mac host.

