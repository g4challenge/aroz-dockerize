# aroz-dockerize

Docker support for https://github.com/tobychui/arozos

# Usage with docker-compose

1. Ensure docker && docker-compose installed
2. Clone/Download this repo
3. `$ docker-compose up`
4. Open http://localhost:8888/

# Usage with command line docker

1. Ensure docker installed
2. `docker run -d -p "8888:80" -p "2121:21" -v "aroz-files:/arozos/src/files:rw" -v "aroz-tmp:/arozos/src/tmp:rw" -v "aroz-system:/arozos/src/system:rw" --restart=always --name=aroz ghcr.io/gissehel/arozos:latest`
3. Open http://localhost:8888/

You can of course replace volume names *aroz-files*, *aroz-tmp* and *aroz-system* by some absolute local folder.
