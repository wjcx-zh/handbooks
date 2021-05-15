### ==> ERROR: A specified local key could not be updated from a keyserver

** Change the default keyserver**
```c
pacman-key --refresh-keys --keyserver hkp://keyserver.kjsl.com:80
pacman-key --refresh-keys --keyserver hkp://pgp.mit.edu:11371
pacman-key --refresh-keys --keyserver hkp://ipv4.pool.sks-keyservers.net:11371
```
Try the above three commands to find which can run without error, and then copy that keyserver address, adding it into the keyserver configuration of pacman :<br/>
	1. edit file : /etc/pacman.d/gnupg/gpg.conf <br/>
		```c
		keyserver hkp://ipv4.pool.sks-keyservers.net:11371
		```
	2. init the pacman-key
		```c
		pacman-key --init
		pacman-key --populate archlinux
		pacman-key --refresh-keys
		```

- refer link [https://bbs.archlinux.org/viewtopic.php?id=226770](https://bbs.archlinux.org/viewtopic.php?id=226770)


### Archlinux更新提示invalid or corrupted package (PGP signature)
e.g.
```c
error: python-pytoml: signature from "Eli Schwartz <eschwartz@archlinux.org>" is unknown trust
:: File /var/cache/pacman/pkg/python-pytoml-0.1.20-1-any.pkg.tar.xz is corrupted (invalid or corrupted package (PGP signature)).
```
1. view the key status <br/>
	```c
	sudo pacman-key --list-sigs Schwartz
	```
2. if "expired", refresh `sudo pacman-key --refresh-keys`
3. if no tips, view the key status of master `sudo pacman-key --list-sigs Master`
4. if find key "undefined", delete the key id and re-import <br/>
	```c
	pacman-key --delete key-id
	pacman-key --populate archlinux
	```



