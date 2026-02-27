# Special file permissions

there are another 3 special permissions, you may encounter on your pen test journey it like *execute permission *
1. SUID bits  denoted by *s*  (set user ID bit) 4 numeric value 4000
2. SGID bits denoted by *s* (set group ID bit) 2  numeric value 2777
3. Sticky bits denoted by *t* (set other ID bit) 1  numeric value 1602
after enter to the root directory use the command 
`chmod +s root`

# Package installation on Linux

package manager microsoft store for window
package manager for LInux is eg for debian package *apt* also there is called *dpkg*
*package managers* are free software user interface that work with an online server to handle the installation and remove of software on debian

how it work 

*linux system -> package manager -> repository(server) ->packages -> package dependencies -> package metadata*

apt is advanced package tool /apt/

if you use apt you must be online

old apt use as apt-get 
now we use apt only

sudo apt update

*dpkg* is an offline package managing program
sudo dpkg -i ( for installation)
sudo dpkg -r (for remove)
sudo dpkg -p(for remove with all )

*flatpak*  univeral software packaging for install linux desktop application   

if the go file must inter in ./go/bin but after using sudo mv filename /usr/bin is work 

*Processes* running instances of programs
*service* background programs that start automatically or manually 
`ps` for process running on my shell
`ps -A` for view all running process
`ps -u username` view users process
#### managing processes
to stop process
- kill PID
- killall [program name]
-more on kill
- kill -19 PID stop the process
- kill -18 PID to resume 
- kill -9 PID strongly to stop the process
those kill are not real time 
*top* real time process to exit press Q
*htop* real time process with good colorful  to exit press f10
and also using htop we can kill real time processes  using press f9 before that we need to search the file using f3 

#### Foreground and background

to give the foreground file to background after the thing put *&*
and to send the bakground to foreground using *fg*
services to stop
*sudo systemctl stop <serviceName> -stop the service*
