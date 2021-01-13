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
