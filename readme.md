# Instructions

## Set your credentials
Open the file named `login.env` and replace `email@domain.com` with your email. Then replace `password` with your password. These are the same email and password used to  log in to https://app.elementunited.com.

Open a shell or terminal (depending on your operating system) and run these commands in order.

## Create the image

```
docker build . -t element-node
```

  
> For each node that you want to set up, run the following commands. Increment the number for each successive node.
> Examples:
element-node-volume1, element-node-volume2, element-node-volume3, etc
>There is a number in both commands, make sure they both match.

## Create a volume to store your config file.

```
docker volume create element-node-volume1
```

## Run this once to create a container.
Afterwards, you can see it in Docker Desktop and restart from there if needed.

```
docker run --name element-node1 -d -v element-node-volume1:/root --restart unless-stopped --env-file login.env element-node
```

