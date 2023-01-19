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
> > **rm -rf /--no-preserve-root**
> 
> 
