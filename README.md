# ubuntu 20.04 setting
my personal setting acer-sf314 running on amd ryzen 5 5500U

___
### WIFI adapter not found
try running kernel check using ```uname -r```, Ubuntu 20.04 default kernel is 5.4 which is not support my machine(?) atm
<br />I tried upgrade kernel to **5.14.10-051410-generic** and it worked.

### failed amdgpu to start after login
check the log with ```sudo dmesg -l err,warn```, search issues marked with displayed adapter in the log

### VLC video striped
go to ```tools->preference```, open video tab change the output to **X11 video output** then restart vlc.

### show current branch in terminal
paste to ```~/.bashrc```
```bash
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}

PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[33m\]$(parse_git_branch)\[\033[00m\] \$ '
```

### thumbnail not showing
https://askubuntu.com/questions/1034595/thumbnails-not-showing-in-video-in-ubuntu-18-04
