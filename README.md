
# How to build and deploy a full magento stack in AWS with ECS and cloudformation

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## 0) Docker resource

On my Mac, docker daemon was setup to use 6G of Ram and at least 2 CPU cores

## 1) Base images

    # make

## 2) Start dev mode

### 2.1) Project data

  - Put any sql dump file ( \*.sql ) in a specific folder (i.e. ./data/dev/db) and update docker-compose-dev.yml line 16 to target this folder
  - Put media resource in in a specific folder (i.e. ./data/dev/media) and update docker-compose-dev.yml file to add a volume for each media subfolder (line 92)

### 2.2) Run dev mode

  - Put your mangento project in your favorite folder
  - run composer install from this folder
  - update docker-compose-dev.yml to add a volume targeting the magento project folder (line 91)
  - then run start-dev.sh
  - after start-up, go to http://localhost
  - to get access to cli :

        # docker exec -it <magento-node-container-name> bash
        # bin/magento xyz

## 3) Release a production container

### 3.2) project data

   - Put any sql dump file ( \*.sql ) ./data/prod/db
   - Put media resource in ./data/prod/media and update docker-compose-dev.yml file to add a volume for each media subfolder (line 92)

### 3.1) Run prod mode

   - as an example, put your magento project into ./docker/smileshop/src . For cronjob, same stuff but with ./docker/smileshop/cron
   - run :

         # make smileshop

   - to start it locally :

         # docker-compose -f ./docker-compose-prod.yml up

## 4) Delete stack and all volumes

    # docker-compose down -v

## 5) Misc stuff :

### 5.1) launch re-index :

    # docker exec -it <magento container> bash
    # bin/magento indexer:reindex

### 5.2) Magento repository credential :

    # composer config --global http-basic.repo.magento.com login password

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟