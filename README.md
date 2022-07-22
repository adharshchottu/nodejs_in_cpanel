# NodeJS app in sub-diretory in cPanel

Install node app in a sub directory in cpanel

part 1 - setup nodejs app

part 2 - redirect it from a subdirectory

# set up NodeJS app

1. Upload the source code in to a file manager inside a folder
2. In cPanel click on the `Setup Node.js App`
3. click on *create application*
4. select the `Node.js version`.
5. select the `Application mode`
6. enter the directory where the source files are as `Application root`
7. select the appropriate `Application URL`
8. enter the `Application startup file`
9. click on *create*
10. click on the *npm install*. make sure the application is stopped before installing the npm modules
11. restart the application.
12. if api server is not running make sure to run the script inside the nodejs application manager by clicking the *Run JS Script* button. select the *start* script to run.

## Redirect from  a sub-directory

1. for that go to the directory entered as `Application URL` in the file manager.
2. there will be a `.htaccess` file inside the directory. it will have two parts. first part will be the node environment configurations and the second part will be `<IfModule Litespeed></IfModule>`
3. inside the `<IfModule>` enter the redirection rules as given in the `.htaccess` file in the source code.


note: The "Setup Node.js App" button is provided by the CloudLinux Node.js Selector. It is only available on CloudLinux servers. contact your hosting provider for more.

note: in order to kill the process, need to access via terminal
- `ps aux | grep server.js` will list all the process
- `kill -9 PIDNUMBER` to kill a process, replace the *PIDNUMBER* accordingly
