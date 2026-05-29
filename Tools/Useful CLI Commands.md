# Useful CLI Commands

#### Copy files to a new directory and exclude files

`rsync -av --exclude='.git' path/to/copy .`

### Docker

#### Stop all running containers

`docker stop $(docker ps -q)`

#### Force stop all running containers immediately

`docker kill $(docker ps -q)`

#### Remove all containers

*Stops running containers prior to removal and removes all containers*
`docker rm -f $(docker ps -aq`

#### Clean up everything including images

`docker system prune -a` *The `-a` is what removes unused images as well*

### [[Git Commands]]

### [[AWS CLI Commands]]

### [[Terraform Commands]]
