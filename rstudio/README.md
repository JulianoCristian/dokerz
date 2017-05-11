### For building in a new folder with a Dockerfile in it (you can add your packages to it)

docker build --rm -t 42n4/rstudio .

https://github.com/rocker-org/rocker/wiki/Using-the-RStudio-image

https://github.com/rocker-org/rocker-versioned/tree/master/rstudio

### For linux with exact username and its user id and group id

docker run -d -p 8787:8787 -e USER=guest -e USERID=1001 -e GROUPID=100 -v $(pwd):/home/guest 42n4/rstudio

### For Windows Docker with Linux containers enabled and Powershell and shared disk c: in docker settings
https://github.com/pwasiewi/dokerz/blob/master/rstudio/linux_docker_in_windows10.png

docker run -d -p 8787:8787 --name=rstudio --restart=always -v c:/Users/Piotr/remote:/home/rstudio 42
n4/rstudio

### To turn off hyper-v in powershell after removing docker for windows in order to use e.g. Virtualbox, Vmware

Disable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-All

### In order to use VirtualBox with Docker use Docker ToolBox: https://www.docker.com/products/docker-toolbox

### Docker for Windows always use hyper-v disabling other vm providers

### https://forums.docker.com/t/volume-mounts-in-windows-does-not-work/10693/141
