# Minecraft-Docker

1. How to run Dockercraft
              Install Minecraft: minecraft.net

The Minecraft client hasn't been modified, just get the official release.

Pull or build Dockercraft image: (an official image will be available soon)

docker pull gaetan/dockercraft
or

git clone git@github.com:docker/dockercraft.git
docker build -t gaetan/dockercraft dockercraft
Run Dockercraft container:
"""
docker run -t -i -d -p 25565:25565 \
-v /var/run/docker.sock:/var/run/docker.sock \
--name dockercraft \
gaetan/dockercraft
"""
Mounting /var/run/docker.sock inside the container is necessary to send requests to the Docker remote API.

The default port for a Minecraft server is 25565, if you prefer a different one: -p <port>:25565

Open Minecraft > Multiplayer > Add Server

The server address is the IP of Docker host. No need to specify a port if you used the default one.

If you're using Docker Machine: docker-machine ip <machine_name>

Join Server!

You should see at least one container in your world, which is the one hosting your Dockercraft server.

You can start, stop and remove containers interacting with levers and buttons. Some Docker commands are also supported directly via Minecraft's chat window, which is displayed by pressing the T key (default) or / key.
