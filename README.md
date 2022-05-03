## What is changepasswd
 changepasswd can modify the host password in batches through ssh interactively .

## Example Usage

Firstly, download the latest programs from [Release](https://github.com/sjwhi8989/changepasswd/releases) page according to your operating system and architecture.

Put `changepasswd` and `host.cfg` onto your PC .


1. Modify `host.cfg` :

  ```ini
  # host.cfg
[testPC01:vars]
ssh_port=22
ssh_user=test
ssh_pass=pass01
ssh_pass_new=passnew01
#ssh_pass=passnew01
#ssh_pass_new=pass01

[testPC01]
h=192.168.100.1 ssh_port=22022  ssh_user=sjw  ssh_pass=pass03
h=192.168.100.2 ssh_pass=pass03

[testPC02]
h=192.168.100.3 ssh_port=22022  ssh_user=sjw  ssh_pass=pass03
h=192.168.100.4 ssh_port=22     ssh_user=sjw  ssh_pass=pass03
  ```

2. If you want to change the password of the host in the [testPC01]:

  `./changepasswd -s testPC01 -do changepasswd`

3. If you want to verify that the ssh login password in the host.cfg file  is correct :  
  
  `./changepasswd -s testPC01 `

4. `-h` for help

  `./changepasswd -h `
  ```
  v1.0 at 2022-05-03 created by <sjwwork@163.com>
Function: Modify the host password in batches through ssh interactively .
Options:
  -c file
    	set configuration file (default "host.cfg")
  -debug
    	print debug info
  -do checklogin | changepasswd
    	checklogin | changepasswd (default "checklogin")
  -h	this help
  -passnew
    	using ssh_pass_new in configuration file to checklogin
  -s string
    	using section in configuration file
  -timeout uint
    	the ssh connection timeout (seconds)  (default 5)
  -v	show version and exit

host.cfg Example

	[testPC01:vars]
	ssh_port=22
	ssh_user=test
	ssh_pass=pass01
	ssh_pass_new=passnew01
	#ssh_pass=passnew01
	#ssh_pass_new=pass01

	[testPC01]
	h=192.168.100.1 ssh_port=22022  ssh_user=sjw  ssh_pass=pass03
	h=192.168.100.2 ssh_pass=pass03

	[testPC02]
	h=192.168.100.3 ssh_port=22022  ssh_user=sjw  ssh_pass=pass03
	h=192.168.100.4 ssh_port=22     ssh_user=sjw  ssh_pass=pass03
```
