# docker-exifsort

I created a docker image for a pretty handy script to sort my personal photo's on my ubuntu server.
The git repo of the creator can be found [here](https://github.com/mb243/exifsort)

## Howto use the container
Use a shared volume to mount your photo folder into the container. Be carefull! the photo's will be moved to other folders in the given shared volume. 

```bash
docker run --rm -it -v <path/to/photo>:/var/photo exifsort
```

## Configuration options
Environment variables can be set:
`TS_AS_FILENAME, USE_LMDATE, USE_FILE_EXT, JPEG_TO_JPG, ENV FILETYPES`

For more info about the configuration see the [script](./exifsort.sh).
```bash
# Use -e to override the environment variable.
docker run --rm -it -v <path/to/photo>:/var/photo -e TS_AS_FILENAME=TRUE exifsort
```