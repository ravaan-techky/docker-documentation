## Docker Commands

### Overview:
This page explains how to create docker custome image.

### Dockerfile

Dockerfile is use to create docker custom image. 

Here is sample Dockerfil, - 

```markdown
#Use an existing docker image as base image
FROM alpine

#Download and install dependecny
RUN apk add --update redis

#Tell the image what to do when it starts the container
CMD ["redis-server"]
```

![Dockefile Steps](../../images/create_docker_file.png)

### Command run to Dockerfile

**Building docker image**
```markdown
# '.' period sign is represent current directory. We need to run this command from folder where we have dockerfile.

Command:
	docker build .

Console output: 
	Sending build context to Docker daemon  2.048kB
	Step 1/3 : FROM alpine
	 ---> a24bb4013296
	Step 2/3 : RUN apk add --update redis
	 ---> Running in 9631e316acc1
	fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/main/x86_64/APKINDEX.tar.gz
	fetch http://dl-cdn.alpinelinux.org/alpine/v3.12/community/x86_64/APKINDEX.tar.gz
	(1/1) Installing redis (5.0.9-r0)
	Executing redis-5.0.9-r0.pre-install
	Executing redis-5.0.9-r0.post-install
	Executing busybox-1.31.1-r16.trigger
	OK: 7 MiB in 15 packages
	Removing intermediate container 9631e316acc1
	 ---> dc5ef2531bbd
	Step 3/3 : CMD ["redis-server"]
	 ---> Running in 2d35daef80fb
	Removing intermediate container 2d35daef80fb
	 ---> 1a4653c9603f
	Successfully built 1a4653c9603f
	SECURITY WARNING: You are building a Docker image from Windows against a non-Windows Docker host. 
  All files and directories added to build context will have '-rwxr-xr-x' permissions. It is recommended 
  to double check and reset permissions for sensitive files and directories.

# Above mentioned command return docket image id which we can use to run docker image.
	docker run d82db9413796
	
```

**Building docker image with tagging**

```markdown

# 'tag' command use to give meaningful name to above docker image id.
	docker tag d82db9413796 ravaantechky/redis:latest
	
# Above mentioned command return docket image tag name which we can use to run docker image.
	docker run ravaantechky/redis
	
```

### How Docker tool use Dockerfile internally

Consider below example where we have task to install Google Chrome where we don't have Operating system also not installed.

![create_docker_description_2](../../images/create_docker_description_2.png

Workflow in-depth, -

![create_docker_image_flowchart](../../images/create_docker_image_flowchart.png)

<br/><br/>
[<i class="fa fa-arrow-left"></i> **Back**](/docker-documentation/)

