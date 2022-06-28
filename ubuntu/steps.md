1. Run an image
`docker run -it --rm ubuntu:20.04 bash`
2. Check Ubuntu version
```
apt-get update
apt install lsb-core
lsb_release -a
```
3. Run an image in background
`docker run -it --rm -d ubuntu:20.04 bash`
4. Build a custom image
`docker build -t ubuntu-computacion . `
5. Check creation 
`docker images`
6. Run container
`docker run -it --rm -v ${PWD}/files:/home/files ubuntu-computacion bash`