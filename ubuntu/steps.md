1. Build image
`docker build -t ubuntu-computacion . `
2. Check creation 
`docker images`
3. Run container
`docker run -it --rm -v ${PWD}/files:/home/files ubuntu-computacion bash`