# (nova) oercamp-venueless-standalone

We have no dev-setup, because no changes were made to the code. 
But we have our own version, because we host it on our servers.

## Production Setup:

* Tips here: https://venueless.readthedocs.io/en/latest/admin/setup.html#create-your-world


* Edit `.docker/volumes/conf/venueless.cfg`


* Add and prepare `.env` file


* [Suboptimal temporary solution] The data volumes need to have user of the venueless-container.  
Create `.docker/volumes/data` and do  `chown -R 15371:15371 .docker/volumes/data`


* Create superuser: `sudo docker exec --user venueless -it venueless /bin/bash` -> `~/server$ venueless createsuperuser`


* Create world: `sudo docker exec --user venueless -it venueless /bin/bash` -> `~/server$ venueless create_world`

* Add cronjob:

```
55 * * * * cd /sites/oercamp/oercamp-venueless && docker compose exec -u venueless -T venueless venueless cleanup 2>&1
```
