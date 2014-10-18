
dpendencies:
pbuilder
pdebuild
pbuilder-scripts
debhelper
libssl-dev
packaging-dev

# Create deboostrap script for different archs
ls -la /usr/share/debootstrap/scripts/

# create pbuilder chroots
pcreate --distribution trusty-amd64
pcreate --distribuiton trusty-i386

# Create sourc file directory structure

# create base tar file


cd /vagrant/ossec-hids/ossec-hids-2.8.1
quilt pop -a
while quilt push; do quilt refresh -p ab; done 

quilt push -f
quilt refresh
