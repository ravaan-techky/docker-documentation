## Docker Commands

### Overview:
This page explains all important commands related to Docker CLI.

### Docker Import Commands:

**_System Command_**

Clean all containers. Should use when we are not using containers for long times.

**Output:** Clean Storage space.

```markdown
# Syntax
docker system prune
```

**_Create Command_**

Create container for a given image. This command does not start / run image within container.

**Output:** Return container ID.

```markdown
# Syntax
docker crete <image_id>

# Example:
docker crete bussyBox
# bussyBox is linux image which will be used to create container.
```

**_Start Command_**

Run image which deployed in container.

**Output:** Return container ID.

```markdown
# Syntax
docker start <container_id>

# Example:

# create container for hello-world image. Output of this coammand is container_id.
# command:
         docker create hello-world
# console output: 
         b6ae6459dc9e606b6b37279d2f22478c3a95be03f9a718dafd833e313f220351

# Use above container_id to start container. Output of this command is container_id. 
# command: 
         docker start b6ae6459dc9e606b6b37279d2f22478c3a95be03f9a718dafd833e313f220351
# console output: 
         b6ae6459dc9e606b6b37279d2f22478c3a95be03f9a718dafd833e313f220351

# Use above container_id to start container. Output of this command is container_id.
# -a option of command shows container execution console logs
# command:
         docker start b6ae6459dc9e606b6b37279d2f22478c3a95be03f9a718dafd833e313f220351 -a
# console output:
         Hello from Docker!
                  This message shows that your installation appears to be working correctly.
         To generate this message, Docker took the following steps:
          1. The Docker client contacted the Docker daemon.
          2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
             (amd64)
          3. The Docker daemon created a new container from that image which runs the
             executable that produces the output you are currently reading.
          4. The Docker daemon streamed that output to the Docker client, which sent it
             to your terminal.
         To try something more ambitious, you can run an Ubuntu container with:
          $ docker run -it ubuntu bash
         Share images, automate workflows, and more with a free Docker ID:
          https://hub.docker.com/
         For more examples and ideas, visit:
          https://docs.docker.com/get-started/
```

**_Exec Command_**

Execute command inside container.

**Output:** command execution result.

**Note: it flag represnt interactive input terminal flag.**

```markdown
# Syntax
docker exec -it <container_id> <command>

# Example:

# download and create container for redis in-memory database.
# command:
         docker create redis
# console output:
         c41ab591664e519a4ee9fe68b6e58466b24f0bb19e41ea844ee2d082df4e4916

# start redis.
# command:
         docker start c41ab591664e519a4ee9fe68b6e58466b24f0bb19e41ea844ee2d082df4e4916
# console output:
         c41ab591664e519a4ee9fe68b6e58466b24f0bb19e41ea844ee2d082df4e4916

# connect redis in-memory database container application through redis-cli command to perform operation / trouble-shooting purpose.
# command:
         docker exec -it c41ab591664e519a4ee9fe68b6e58466b24f0bb19e41ea844ee2d082df4e4916 redis-cli
# console output:
         127.0.0.1:6379> set my_variable 5
         OK
         127.0.0.1:6379> get my_variable
         "5"
```

**_Exec Command for Debugging purpose_**

Open shell / BASH / PowerShell of container virtual machine, for debugging purpose.

**Output:** Open shell / BASH / PowerShell command prompt.

**Note: it flag represnt interactive input terminal flag.**

```markdown
# Syntax to open shell command prompt using run docker command without any other process
docker run -it busybox sh

# Syntax to open BASH command prompt using run docker command without any other process
docker run -it busybox bash

# Syntax to open shell command prompt
docker exec -it <container_id> sh

# Syntax to open BASH command prompt
docker exec -it <container_id> bash

```

<br/><br/>
[<i class="fa fa-arrow-left"></i> **Back**](/docker-documentation/)

