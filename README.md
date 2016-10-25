# VPS Configuration

This is a repo for holding configuration structures and instructions I use for setting up my VPS.



## Common Tasks

Copy text from a remote file to local clipboard

    ssh REMOTE-HOST "cat /etc/nginx/nginx.conf" | pbcopy

Paste text from local clipboard into remote file

    TODO


## nginx

Configuration file:

    /etc/nginx/nginx.conf

nginx can be controlled by invoking the executable with the -s parameter. Use the following syntax:

    nginx -s signal

Where signal may be one of the following:

    stop — fast shutdown
    quit — graceful shutdown
    reload — reloading the configuration file
    reopen — reopening the log files

To start nginx

    sudo /etc/init.d/nginx start

To stop nginx (Linux)

    sudo /etc/init.d/nginx stop

To reload nginx config (Linux)

    sudo /etc/init.d/nginx reload

To check to see if it is running

    ps -ef | grep nginx

To edit the nginx Config File

    sudo nano /etc/nginx/nginx.conf


## unix

To easily display all the permissions on a path, you can use:

    namei -om /path/to/check

Get my version

    uname -a

Start a long-running process

    tmux
    # start the process
    # Exit tmux: Ctrl+B, D

Exit the same process:

    tmux list-sessions
    tmux attach

* http://askubuntu.com/questions/8653/how-to-keep-processes-running-after-ending-ssh-session
* http://tmux.github.io/


## TODO

- [ ] Set up a virtual host for each domain
- [ ] The www-data users should only have access to the site location and nothing else to reduce the chance that a compromised server can do damage.
- [ ] Error and access logs per virtual host
- [ ] Unix command to count number of cores on my VPS
- [ ] Simply use the index directive one time. It only needs to occur in your http{} block and it will be inherited below. (My server blocks are not in http blocks. why the difference?)


## Sources

* https://gist.github.com/leommoore/2701379
* https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/
* https://www.nginx.com/resources/wiki/start/