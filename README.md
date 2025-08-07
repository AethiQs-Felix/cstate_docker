# cstate_docker

This repository builds and automates Docker images for [cState](https://github.com/cstate/cstate), a popular status page system. The images are built from the upstream cState project, and both the cState license and the MIT license (for this automation) apply.


## How to Run the Docker Image


You can run the cState Docker image with the following command:

```bash
docker run -d --name cstate --restart unless-stopped -p 8080:80 -v $(pwd)/app_data:/app ghcr.io/aethiqs-felix/cstate:latest
```

Then visit `http://localhost:8080` in your browser.

This command is equivalent to the following `docker-compose` service:

```yaml
cstate:
	image: ghcr.io/aethiqs-felix/cstate:latest
	container_name: cstate
	restart: unless-stopped
	ports:
		- "8080:80"
	volumes:
		- ./app_data:/app
```

## License
This repository is licensed under the MIT License. The upstream cState project is licensed under its own terms; see the [cState repository](https://github.com/cstate/cstate) for details. Both licenses are applicable when using the Docker images built by this automation.
