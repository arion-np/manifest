# git-repo manifest
### ubuntu

```sh
curl https://storage.googleapis.com/git-repo-downloads/repo > repo
chmod 755 repo
sudo mv repo /usr/bin
```

### Download using repo command
#### Without git history (for build machine, fast)
```sh
# use buildroot.xml manifest
$ repo init -u git@github.com:arion-np/manifest -m buildroot.xml
$ repo sync --fetch-submodules
```

### Update to latest

After that, if you want to keep all repositories up-to-date, you can run the `repo sync` command as shown below.

```sh
# Update to latest
$ repo sync
```

### Environment Variables
#### Download U-boot build toolchain
[u-boot toolchain](http://ednanet.synology.me/amlogic/gcc-linaro-7.5.0-2019.12-x86_64_aarch64-elf.tar)

```
$ tar xf gcc-linaro-7.5.0-2019.12-x86_64_aarch64-elf.tar
$ sudo mv gcc-linaro-7.5.0-2019.12-x86_64_aarch64-elf /opt
```
```
$ export PATH=$PATH:/opt/gcc-linaro-7.5.0-2019.12-x86_64_aarch64-elf/bin
```

### Build
```
$ source setenv.sh a4_ba401_a6432_release
$ make
```

The generated image can be found in the path `output/a4_ba400_a6432_release/images/aml_upgrade_package.img`.

### asplay
```
$ asplay list

1: HDMI1 (true)
2: HDMI2 (false)
3: HDMI3 (false)
4: HDMIEARC (false)
5: HDMIARC (false)
6: SPDIF (false)
7: LINEIN (false)
8: AVS (false)
9: USB (false)
10: BT (false)
11: AIRPLAY (false)
12: CAST_LITE (false)
List output: Not implement yet
```

#### asplay mode change
```
asplay enable-input HDMI1
asplay enable-input HDMI2
asplay enable-input HDMIEARC
asplay enable-input HDMIARC
asplay enable-input SPDIF
asplay enable-input LINEIN
asplay enable-input BT
asplay enable-input USB
asplay enable-input AIRPLAY
asplay enable-input AVS
```

#### asplay file playback
```
$ asplay ./test.mp3 halaudio
```