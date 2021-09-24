```
sudo add-apt-repository ppa:graphics-drivers/ppa
```

```
sudo apt-get update
```

```
ubuntu-drivers devices
```

会有一个recommended，下一条数字代替那个

```
sudo apt install nvidia-数字
```

重启

```
nvidia-smi
```

应显示显卡信息，则正确

