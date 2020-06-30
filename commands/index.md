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

```markdown
# Syntax to open shell command prompt
docker exec -it <container_id> sh

# Syntax to open BASH command prompt
docker exec -it <container_id> bash

```

### Docker Management Commands:

| Command | Description |
| ---- | ---- |
| builder | Manage builds | 
| config | Manage Docker configs | 
| container | Manage containers | 
| context | Manage contexts | 
| image | Manage images | 
| network | Manage networks | 
| node | Manage Swarm nodes | 
| plugin | Manage plugins | 
| secret | Manage Docker secrets | 
| service | Manage services | 
| stack | Manage Docker stacks | 
| swarm | Manage Swarm | 
| system | Manage Docker | 
| trust | Manage trust on Docker images | 
| volume | Manage volumes | 

### Docker Commands:

Commands:

 | Command | Description |
 | ---- | ---- |
 | attach | Attach local standard input, output, and error streams to a running container |
 | build | Build an image from a Dockerfile |
 | commit | Create a new image from a container's changes |
 | cp | Copy files/folders between a container and the local filesystem |
 | create | Create a new container |
 | diff | Inspect changes to files or directories on a container's filesystem |
 | events | Get real time events from the server |
 | exec | Run a command in a running container |
 | export | Export a container's filesystem as a tar archive |
 | history | Show the history of an image |
 | images | List images |
 | import | Import the contents from a tarball to create a filesystem image |
 | info | Display system-wide information |
 | inspect | Return low-level information on Docker objects |
 | kill | Kill one or more running containers |
 | load | Load an image from a tar archive or STDIN |
 | login | Log in to a Docker registry |
 | logout | Log out from a Docker registry |
 | logs | Fetch the logs of a container |
 | pause | Pause all processes within one or more containers |
 | port | List port mappings or a specific mapping for the container |
 | ps | List containers |
 | pull | Pull an image or a repository from a registry |
 | push | Push an image or a repository to a registry |
 | rename | Rename a container |
 | restart | Restart one or more containers |
 | rm | Remove one or more containers |
 | rmi | Remove one or more images |
 | run | Run a command in a new container |
 | save | Save one or more images to a tar archive (streamed to STDOUT by default) |
 | search | Search the Docker Hub for images |
 | start | Start one or more stopped containers |
 | stats | Display a live stream of container(s) resource usage statistics |
 | stop | Stop one or more running containers |
 | tag | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE |
 | top | Display the running processes of a container |
 | unpause | Unpause all processes within one or more containers |
 | update | Update configuration of one or more containers |
 | version | Show the Docker version information |
 | wait | Block until one or more containers stop, then print their exit codes |

<br/><br/>
[<i class="fa fa-arrow-left"></i> **Back**](/documentation/)

