# OpenStack-Installation-with-Octavia
openstack installation with octavia to use Loadbalancer


```
useradd -s /bin/bash -d /opt/stack -m stack
echo "stack ALL=(ALL) NOPASSWD: ALL" | sudo tee /etc/sudoers.d/stack
sudo su - stack
```

```
git clone https://git.openstack.org/openstack-dev/devstack -b stable/wallaby
cd devstack
```

local.conf작성

```
./stack.sh
```

eno2 -> no ip address interface
```
sudo ovs-vsctl add-port br-ex eno2
```


Simple jason error

/opt/stack/devstack/inc/python  line 198 (function pip_install)
```
$cmd_pip $upgrade \ -> $cmd_pip $upgrade --ignore-installed \
```


Blazor-nova requirements error
/opt/stack/blazor-nova/requirements

```
# The order of packages is significant, because pip processes them in the order
# of appearance. Changing the order has an impact on the overall integration
# process, which may cause wedges in the gate later.

# pbr>=5.8.0 # Apache-2.0
pbr>=5.5.0
# oslo.config>=8.6.0 # Apache-2.0
oslo.config>=8.5.0
# oslo.i18n>=5.1.0 # Apache-2.0
oslo.i18n>=5.0.0
# oslo.log>=4.6.1 # Apache-2.0
oslo.log>=4.4.0
```
