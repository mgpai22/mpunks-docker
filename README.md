
# Mpunks Docker

This allows you to mine mpunks with docker compose.
## Deployment

- `git clone https://github.com/mgpai22/mpunks-docker.git && cd mpunks-docker`
- Make sure [docker](https://docs.docker.com/get-docker/) and [docker compose](https://docs.docker.com/compose/install/other/) is installed
    - Use [this script](https://github.com/mgpai22/docker-install-script) to install if you are on Ubuntu (wsl does not count!)
- Edit the `docker-compose` file to add or remove gpus (note the pattern for each service!)
  - Make sure you change `0x...` to your address!
- ```
  distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
      && curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
      && curl -s -L https://nvidia.github.io/libnvidia-container/experimental/$distribution/libnvidia-container.list | \
         sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
         sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list
  ```
- ```
   sudo apt-get update
   sudo apt-get install -y nvidia-docker2
  ```
- To start:
    `docker-compose up -d`
- To stop:
    `docker-compose down`
- To restart after edit:
    `docker-compose up -d --build`



