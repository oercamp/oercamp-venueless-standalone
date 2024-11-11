# oercamp-venueless-standalone


### Setup:

* Tips here: https://venueless.readthedocs.io/en/latest/admin/setup.html#create-your-world
* Edit `.docker/volumes/conf/venueless.cfg`
* The data volumes need to have user of the venueless-container. Do  `chown -R 15371:15371 .docker/volumes/data`
* The data volumes need to have user of the venueless-container. Do  `chown -R 15371:15371 .docker/volumes/venueless-server`
* Create superuser: `sudo docker exec --user venueless -it venueless /bin/bash` -> `~/server$ venueless createsuperuser`
* Create world: `sudo docker exec --user venueless -it venueless /bin/bash` -> `~/server$ venueless create_world`
