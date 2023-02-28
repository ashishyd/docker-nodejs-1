Commands to execute

To build a docker image. The '.' character signifies the location of the DockerFile
`docker build .`

to build image using name and tag
`docker build -t <name>:<tag> .`

Once build is complete, run command to get generated id
`docker images`

Once you have the id, execute where p is to publish the local port 3000 for container port 80 (attached mode)
`docker run -p 3000:80 <id>`

`docker run -p 3000:80 -d <id>` where d is for de-attached flag

`docker run -p 3000:80 -d --rm <id>` where rm is for removing container after exit automatically

`docker run -p 3000:80 -d --rm --name <name> <id>` where rm is for removing container after exit automatically

Alternatively, you can use `docker start <id>`, this does not block the terminal (de-attached mode)

`docker start -a <id>` to start in attached mode

`docker attach <id>` to attach to running container

To stop the container, open separate terminal and execute
`docker stop <id>` or `docker stop <name>`  

`docker ps` shows all running containers, ps is short for process

*All instructions in docker act as a cacheable layer, hence package.json copy is written separately, as now if we make any changes to code file then only copying other files to container will change and we save time. Please note if anytime an instruction is changed like in our case all the following instructions will be reevaluated.*

`docker logs <id>` to output all the logs in the container

`docker logs -f <id>` to output all the logs in the container in listening mode

`docker images inspect <id>` to get all details of the image

`docker cp <source_folder>/. <id>:/<container_path>` to copy the file from local to running container