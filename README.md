# How to use it

Refer to these official documenations and the blog post for Docker commands.

1. [Build a Node.js and React app with npm](https://jenkins.io/doc/tutorials/build-a-node-js-and-react-app-with-npm/#setup-wizard)
2. [Create a Pipeline in Blue Ocean](https://jenkins.io/doc/tutorials/create-a-pipeline-in-blue-ocean/)
3. [How to use Docker commands](https://www.steadylearner.com/blog/read/How-to-use-Docker-commands)

The speed of the processes depens on which machine it uses. I would use the server and servies from the Travis CI instead of Jenkins.

Create pipeline from UI takes so much time. I would build Jenkinsfile and use git CLI Instead also.

Its payload is Jenkinsfile with [the pipeline API](https://jenkins.io/doc/book/pipeline/syntax/) and shell commands to help it.

## Workflow

1. Install it with Docker and make volumes and link paths and login.
2. Help it which codes use. GitHub etc.
3. Write Jenkinsfile with pipeline.
4. Make bash commands for each stage(process).
5. Read the documenation and navigate the UI.

## Commands

**1.** Minimal Setup

```console
docker run \
  -u root \
  -p 8080:8080 \
  -v jenkins-data:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v "$HOME":/home \
  --name jenkins jenkinsci/blueocean
``` 

**2.** When you want to control the jenkins container

```console
docker exec -it jenkins bash
```

**3.** Manage volumes made from it 

```console
docker volume ls
```

## Notes

1. If you want to use GitHub repositories in your local machine, you should save it in the right path.

2. It is simple but save credentials well before you login, if you couldn't find it, remove the container and volumes then start again. 
