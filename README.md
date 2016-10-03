# Install Bika LIMS

### Start the vagrant 

```
vagrant up
```

### Login your vagrant 

```
vagrant ssh
```
 
### Install Plone

Download:

```
wget https://launchpad.net/plone/4.3/4.3.11/+download/Plone-4.3.11-UnifiedInstaller.tgz
```

Uncompress:

```
tar zxvf Plone-4.3.11-UnifiedInstaller.tgz
```

Create a folder for the instalation:

```
sudo mkdir /usr/local/Plone
```

Set the permissions in the folder:

```
sudo chown vagrant:vagrant /usr/local/Plone
```

Install Plone:

```
./Plone-4.3.11-UnifiedInstaller/install.sh --target=/usr/local/Plone --build-python zeo
```

Configure buildout.cfg:

```
nano /usr/local/Plone/zeocluster/buildout.cfg
```

Edit the eggs property as:

``` 
eggs =
    Plone
    Pillow
    bika.lims
```

Install dependencies:

```
/usr/local/Plone/zeocluster/bin/buildout
```

# Run Lims

Start Database

```
/usr/local/Plone/zeocluster/bin/zeoserver start
```

Start Plone

```
bin/client1 fg
```

Go to

```
http://localhost:9090
```



