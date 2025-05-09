# Using Docker

Installation

1.
cd docker

bash models/pytorch/fetch_model.sh # Fetches the PyTorch model

Then move file caffemodel.pth to /docker/models/pytorch/

docker build -t colorize .

docker image ls

2.

xhost + 127.0.0.1

If you are using Windows or MacOS: docker run -e DISPLAY=host.docker.internal:0 colorize

If Ubuntu: 

sudo docker run -it \

  --env DISPLAY=$DISPLAY \
  
  --volume /tmp/.X11-unix:/tmp/.X11-unix \
  
  --user $(id -u):$(id -g) \
  
  colorize

