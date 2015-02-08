###Build directory structure:
`sudo su`

`cd /tmp`

`apt-get update`

###build_env_dependencies
`apt-get install -f pbuilder pdebuild pbuilder-scripts packaging-dev`

###ossec_build_dependencies
`apt-get install debhelper libssl-dev`

###create arch specific pbuilder layout

`mkdir -p /var/cache/pbuilder/trusty-amd64/result`

`mkdir -p /var/cache/pbuilder/trusty-amd64/aptcache`

###create base tar file

```
pbuilder create --buildresult /var/cache/pbuilder/${codename}-${arch}/result/ --basetgz /var/cache/pbuilder/${codename}-${arch}-base.tgz --distribution ${codename} --architecture ${arch} --aptcache \
/var/cache/pbuilder/${codename}-${arch}/aptcache/
```

###Create sourc file directory structure

`cp -R /vagrant/ossec-hids /tmp`

download ossec archive to /root

unpack ossec-hids-2.8.1.tar.gz to /tmp/ossec-hids

mv debian directory to /tmp/ossec-hids/ossec-hids-version/

###make sure patches are applied correctly

```
cd /tmp/ossec-hids/ossec-hids-2.8.1
quilt pop -a
while quilt push; do quilt refresh -p ab; done
```

```
quilt push -f
quilt refresh
```

###run the generate script with -t flag

```
cd /vagrant
./generate.sh -t
```

###Output
/var/cache/pbuilder/result/
