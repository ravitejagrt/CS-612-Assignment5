#RESTful webservice using Docker

* Link to video : https://paceuniversity-my.sharepoint.com/:v:/g/personal/rg49526n_pace_edu/EcQVTx27tKRCu7wdAUhirAgBCAcEn6QTv2qiryE2udz5ww?e=jQZTfn

Created a RESTful Web service that displays data of empires in JSON format using two get routes: 
   
* /empires
   
* /empires/{empireid}

* /empires/{empireId}/army

* /empires/{empireid}/army/{armyid}

* Empires data is in the Empires.JSON file

* Armies data is in the Army.JSON file
    
Steps to run RESTful web service:

* Create the project with app.py and JSON file in a single folder.
  The templates folder consists of the page.html file which displays the json result on the webpage
  
* Install docker. After installing docker follow the below steps.

* A Docker Image is created by running the following command: -
### `docker build -t empires-image:latest .`

* Check the docker image created using the command
### `docker images`

* You will find the image empires-image under the list.

* Run the created empires-image image inside a container using the following command
### `docker run -d -p 5000:5000 --name empires-container empires-image`

* You will find the container empires-container in the list

* Check running of docker container created using the command 
### `docker ps`

* Check the ip address of the docker using the command
### `docker-machine ip default`
* This will be the host_ip_address.

* App will now be running at the following urls: -
  http://<host_ip_address>:5000

* http://<host_ip_address>:5000/empires

* http://<host_ip_address>:5000/empires/{empire_id} 

### `http://<host_ip_address>:5000/empires/101` --- 101 is the id you wish to search

* Empires ids are from 101 to 105

* http://<host_ip_address>:5000/empires/101/army

* http://<host_ip_address>:5000/empires/101/army/{army_id}

### `http://<host_ip_address>:5000/empires/101/army/1001`

* Army ids are 1001 and 1002

* For data in json format: -

### `http://<host_ip_address>:5000/empires?type=json`
### `http://<host_ip_address>:5000/empires/101?type=json`
### `http://<host_ip_address>:5000/empires/101/army?type=json`
### `http://<host_ip_address>:5000/empires/101/army/101?type=json`

* If you are running the project in pycharm IDE, use 
### `localhost:5000/empires` or 
### `0.0.0.0:5000/empires`
