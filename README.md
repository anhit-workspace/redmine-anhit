# Build readme with 2 vps database and ap

## Require:
Set on 2 VPS: Redmine and Database
OS: Debian or CentOS
Resource: Refer from docker hub: [docker hub](https://hub.docker.com/_/redmine)

## Setup step by step
### Step 1: Prepare
#### 1. VPS 1: Database
**IP:** 192.168.1.11

#### 2. VPS 2: App Redmine
**IP:** 192.168.1.10

### Step 2: Setup Redmine 4.2.1
````
git clone git@github.com:alex-workspace/redmine.git
````
Use version Redmine 4.2.1
This version is stable and can install most plugins.
Run command:
````
docker compose -f redmine-42-bullseye.yaml up -d
````

### Step3: Install Plugin

Git clone New plugin on [REDME-APP]\Plugins\
And run command: 
````
bundle install
bundle exec rake redmine:plugins:migrate RAILS_ENV=production
````
## Readme version 5.0.5
Newly installed plugins often have problems, many plugins are not compatible, setup is for reference only

Some links and reference articles about Redmine:
- https://hocvienagile.com/uu-nhuoc-diem-khi-quan-ly-du-an-bang-redmine/
- https://news.cloud365.vn/redmine-huong-dan-su-dung-redmine-de-quan-ly-cong-viec-phan-1/