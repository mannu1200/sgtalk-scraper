# sgtalk-scrapper 
Scrapper for http://sgtalk.org/.
Just run and sit back. 
Look at the [following file](./data_format.md) for data being scrapped.

### Prerequisites
1. Mongo DB
2. Python

### Setup
 1. Setting up the python virtual env and installing the requirements.

Create the virtual env (one time process), virtualenv is in gitignore hence you 
have to create one on your local machine
```
virtualenv --no-site-packages env
```
Activate it:
```
source env/bin/activate
```
Install the requirements:
```
pip install -r requirements.txt
```

 2. Unique database and indexes in mongo
 ```
 use sgtalk
 db.posts.createIndex( {"post.post_url" : 1 }, {"unique": true })
 ``` 

### Running the scripts

 The script stores the [following data](./data_format.md) in mongo db.
 ```
scrapy crawl sgtalk
 ```
 
## License
This project is licensed under the MIT License.
