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
