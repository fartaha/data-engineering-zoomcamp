# data-engineering-zoomcamp
**Review of Datatalks Data Engineering course:**  

::**MLOps**:: is putting machine learning in production:

## Week 1
### Docker
* It removes all **dependencies** and used for **reproducibility**
* Docker images can be used in different environments like Google cloud (Kubernetes), Amazon batch, local host, ...
* Install Docker directly from their website
```bash
docker --version
docker run hello-world
docker run -it ubunto bash
```
> **docker run hello-world**
> > it looks for hello-world Docker image from Docker hub and run the image and shows the result 
> 
> **docker run -it ubunto bash**
> > **run:** we want to run the image called ubunto
> > **-it:** we want to do this in interactive mode and **t** means	terminal meaning that we want to type sth
>> **ubuntu**: is the name of the image we want to run
>> **bash:** is a command we want to execute in this image
>> +  everything that comes after the image name is parameter to this container
>> + in this example we want to execute **bash** on this image and this way we get this **bash** prompt
> * now we can use **ls** to see the list of files and directories in the our docker image.
>> **rm -rf /**
>> + this command will delete everything in the image but it gives an warning not to doing this stupid thing. If you insist to do it, you can use the following command.
>> 
>> **rm -rf /--no-preserve-root**
>
>> **exit** 
>> 
>> command will bring you out from the container 
>> * now if you run the **ubuntu** docker image you will see it is not affected by your previous stupid thing and you can run **ls** normally and see everything is at their place.
>> + This is what isolation actually means: if an app does sth stupid, our host machine is not affected.
>> 
> Now lets try to run Python with the attack on 3.9 version of it with the following command:
>>
>> **docker run -it python:3.9**
>> 
>> This runs the Python prompt and we can try Python commands and libraries like:
>> ```python
>> print("hellow world")
>> import os
>> os.env
>> ```
>> > **ctrl+D** to exit from python prompt
>> * let say we want to write a Python script in our data pipeline which actually needs **Pandas** library.
>> ** to do so first get out of the python propmt and then somehow we need to get to bash to make it able to install command. For that, we need to overwrite the entry point (which is basically what exactly is executed when we run this container **Python:3.9**) by:
>> ```bash
>> docker run -it --entrypoint=bash python:3.9
>> ```
>> now instead of a python prompt we have a bash prompt and now we can install **Pandas**:
>> ```shell
>> pip isntall pandas
>> ```
>> Now, we are installing **pandas** on this specefic docker container. Type python in bash prompt to get the python prompt:
>> ```shell
>> python
>> ```
>> to make sure it works and pandas is installed:
>> >> ```python
>> import pandas
>> pandas.__version__
>> ```
