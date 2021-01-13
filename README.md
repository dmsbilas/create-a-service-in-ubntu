# Make a linux service for running a Javascript file

If we are making Systemd based system then we have to create a file by following name convention:
```
my_example_service.service
```

Remember : The file has to be with .service tailing. And your service's name is 
```
my_example_service
```
## Now let put contents in our service
```
[Service]
ExecStart=/home/user/my-javascript-file.js
Restart=on-failure
# Other restart options: always, on-abort, etc
```
If you have done so, your service is ready to run. For running the service you have to write following command:
```
sudo systemctl start my_example_service
```
## Controlling the service
```
# Control whether service loads on boot
sudo systemctl enable my_example_service
sudo systemctl disable my_example_service

# Manual start and stop
sudo systemctl start my_example_service
sudo systemctl stop my_example_service

# Restarting/reloading

# Run following command if .service file has changed
sudo systemctl daemon-reload
```
## View status and logs of the service
```
# See if running, uptime, view latest logs
sudo systemctl status
sudo systemctl status my_service
# Or for a user service
systemctl --user status my_service

# See all systemd logs
sudo journalctl

# Tail logs
sudo journalctl -f

# Show logs for specific service
sudo journalctl -u my_daemon
# For user service
journalctl --user-unit my_user_daemon
```
