### RT kernel installation
```
sudo apt-get install build-essential bc curl ca-certificates fakeroot gnupg2 libssl-dev lsb-release libelf-dev bison flex
```

```
curl -SLO https://www.kernel.org/pub/linux/kernel/v5.x/linux-5.4.59.tar.xz
```

```
curl -SLO https://www.kernel.org/pub/linux/kernel/projects/rt/5.4/older/patch-5.4.59-rt36.patch.xz
```

```
xz -d linux-5.4.59.tar.xz
```

```
xz -d patch-5.4.59-rt36.patch.xz	
```

```
tar xf linux-5.4.59.tar
```

```
cd linux-5.4.59
```

```
patch -p1 < ../patch-5.4.59-rt36.patch
```

```
make oldconfig
```

select Fully Preemptible Kernel (RT)

```
sudo make -j16
```

```
sudo make modules_install
```

```
sudo make install
```





if error in "sudo make -j16"

```
gedit .config 
```

search                CONFIG_SYSTEM_TRUSTED_KEYS="debian/canonical-certs.pem"

change to          CONFIG_SYSTEM_TRUSTED_KEYS=""

continue the steps


### Allow a user to set real-time permissions for its processes

```
sudo addgroup realtime
sudo usermod -a -G realtime $(whoami)
```
Afterwards, add the following limits to the realtime group in /etc/security/limits.conf:
```
@realtime soft rtprio 99
@realtime soft priority 99
@realtime soft memlock 102400
@realtime hard rtprio 99
@realtime hard priority 99
@realtime hard memlock 102400
```






