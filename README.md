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
```
$ export PATH=$PATH:/opt/gcc-linaro-7.5.0-2019.12-x86_64_aarch64-elf/bin
```

### Build
```
$ source setenv.sh a4_ba400_a6432_release
$ make
```

The generated image can be found in the path `output/a4_ba400_a6432_release/images/aml_upgrade_package.img`.
