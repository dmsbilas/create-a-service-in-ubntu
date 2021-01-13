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
```
If you have done so, your service is ready to run. For running the service you have to write following command:
```
sudo systemctl start my_example_service
```
## Controlling the service
```
# Control whether service loads on boot
sudo systemctl enable my_service
sudo systemctl disable my_service

# Manual start and stop
sudo systemctl start my_service
sudo systemctl stop my_service

# Restarting/reloading
sudo systemctl daemon-reload # Run if .service file has changed
sudo systemctl restart my_restart

# Or if working with a user service add --user flag
systemctl --user restart my_user_service
```

