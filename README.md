# opsworks-wordpress-app
Wordpress - Ready to be used as application on AWS OpsWorks

## Getting started

1. Launch a new OpsWorks **Chef 11 Stack** from [here](https://console.aws.amazon.com/opsworks/home?owc=true)
2. Add **MySQL Layer**, then add one instance to the MySQL layer and start it
    * Optional, instead of a MySQL layer you can add a RDS layer
3. Add **PHP App Server** layer, add an instance to the layer and start it
4. Add a new App
    * Data source type is OpsWorks, unless in step 2 RDS is used
    * Application source:
        * Repository Type = git
        * Repository URL = https://github.com/tinuva/opsworks-wordpress-app.git
5. Wait for all instances to be in 'running' state
6. Deploy App to all instances
7. At this point, the Wordpress install is finished. Visit the IP address of your instance and set up your wordpress install.

## What to do next

1. Add more instances to the PHP layer
2. Create a Classic ELB
    * On a note, the health check should be on '/' instead of the default '/index.html'
3. Edit the PHP App Server layer, then attach the ELB created in previous step
