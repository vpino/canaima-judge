# Steps to build and try the functionality of a package

## Create the Work Environment:

Install of depends to tests:


### Dependencies generic to build a package

* git.
* git-buildpackage.
* build-essential.

> git-buildpackage and build-essentia are Meta-Packages that have all depends generic to build a packages

```bash
apt install git-buildpackage build-essential
``` 

### Dependecies to execute the test of PIUPARTS:

* piuparts.
* pbuilder.

```
$ apt install piuparts pbuilder
```

##### Create pbuilder to piuparts:

```bash
$ pbuilder --create
```

#### Create pbuilder to packages amd64 and i386

Execute AMD64:

```bash
$ DIST=jessie ARCH=amd64 git-pbuilder create
```

and i383:

```bash
$ DIST=jessie ARCH=amd64 git-pbuilder create
```

### If you dont want to damage your machine for the test the functionality of a package:

---- Section in build -------

################################################

# Build of package


### 1. Git clone the package

Execute:

```bash
$ git clone <url-repository>
```

### 2. Check the scripts of Maintainer


### 3. Build Package

Build without pbuilder:

```bash
$ gbp buildpackage -tc --git-tag --git-retag -uc -us --git-debian-branch="branch"
```

Build with pbuilder and a package amd64

```
$ gbp buildpackage --git-pbuilder --git-dist=jessie --git-arch=amd64 --git-upstream-tree=master -us -uc 
```

i386 package:

```
$ gbp buildpackage --git-pbuilder --git-dist=jessie --git-arch=i386 --git-upstream-tree=master -us -uc 
```

### 4. Piuparts


Execute:

```bash
piuparts -p -d stable <package_generated.deb> -D debian --mirror="http://ftp.debian.org/debian" --extra-repo="deb http://200.11.148.219/canaima chimanta usuarios" --extra-repo="deb http://200.11.148.219/linuxmint betsy main import upstream" --extra-repo="deb http://200.11.148.219/seguridad jessie/updates main contrib non-free"  --extra-repo="deb http://multimedia.canaima.softwarelibre.gob.ve jessie main non-free" -l <path_to_log>
```

### 5. Test of functionality





