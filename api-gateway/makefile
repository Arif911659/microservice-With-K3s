VERSION:=v0.01
IMAGE_NAME:=api-gateway
HOST_PORT:=8000
CONTAINER_PORT:=3000
CONTAINER_NAME:=api-gateway
DOCKER_REGISTRY:=docker.io

build:
	@ docker build -t ${IMAGE_NAME}:${VERSION} .

run:
	@ docker run --name ${CONTAINER_NAME} -p ${HOST_PORT}:${CONTAINER_PORT} ${IMAGE_NAME}:${VERSION} 

rm:
	@ docker stop ${CONTAINER_NAME}
	@ docker rm ${CONTAINER_NAME}
print-vars:
    @echo "DOCKER_REGISTRY=${DOCKER_REGISTRY}"
    @echo "DOCKER_USERNAME=${DOCKER_USERNAME}"
docker-login:
	@echo "Logging in to Docker..."
	@echo ${DOCKER_TOKEN} | docker login -u ${DOCKER_USERNAME} --password-stdin ${DOCKER_REGISTRY}
	@echo "Login successful!"

# push:
# 	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ docker push ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ echo "Image pushed: ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}"
push:
	@ if [ -z "${DOCKER_REGISTRY}" ]; then \
	    echo "DOCKER_REGISTRY is not set. Using default (docker.io)"; \
	    DOCKER_REGISTRY="docker.io"; \
	fi
	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
	@ docker push ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
	@ echo "Image pushed: ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}"