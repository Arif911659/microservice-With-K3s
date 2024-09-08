VERSION := v0.01
IMAGE_NAME := api-gateway
HOST_PORT := 8000
CONTAINER_PORT := 3000
CONTAINER_NAME := api-gateway
DOCKER_REGISTRY := docker.io
DOCKER_USERNAME := arifhossain555
DOCKER_PASSWORD := your_docker_password_here
SHELL := /bin/bash
build:
	@ docker build -t ${IMAGE_NAME}:${VERSION} .

run:
	@ docker run --name ${CONTAINER_NAME} -p ${HOST_PORT}:${CONTAINER_PORT} ${IMAGE_NAME}:${VERSION} 

rm:
	@ docker stop ${CONTAINER_NAME} || true
	@ docker rm ${CONTAINER_NAME} || true

docker-login:
	@ echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_USERNAME} --password-stdin ${DOCKER_REGISTRY}

push: build docker-login
	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
	@docker push ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}

print-vars:
	@ echo "DOCKER_REGISTRY=${DOCKER_REGISTRY}"
	@ echo "DOCKER_USERNAME=${DOCKER_USERNAME}"
	@ echo "DOCKER_PASSWORD=${DOCKER_PASSWORD}"


# VERSION:=v0.01
# IMAGE_NAME:=api-gateway
# HOST_PORT:=8000
# CONTAINER_PORT:=3000
# CONTAINER_NAME:=api-gateway
# DOCKER_REGISTRY:=docker.io
# DOCKER_USERNAME:=arifhossain555
# DOCKER_PASSWORD:=A2743H+211093||@sm@||

# build:
# 	@ docker build -t ${IMAGE_NAME}:${VERSION} .

# run:
# 	@ docker run --name ${CONTAINER_NAME} -p ${HOST_PORT}:${CONTAINER_PORT} ${IMAGE_NAME}:${VERSION} 

# rm:
# 	@ docker stop ${CONTAINER_NAME}
# 	@ docker rm ${CONTAINER_NAME}

# docker-login:
# 	@ echo "Logging in to Docker..."
# 	@ echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_USERNAME} --password-stdin ${DOCKER_REGISTRY}
# 	@ echo "Login successful!"

# push: build
# 	@ if [ -z "${DOCKER_REGISTRY}" ]; then \
# 	    echo "DOCKER_REGISTRY is not set. Using default (docker.io)"; \
# 	    DOCKER_REGISTRY="docker.io"; \
# 	fi
# 	@ if [ -z "${DOCKER_USERNAME}" ]; then \
# 	    echo "Error: DOCKER_USERNAME is not set"; \
# 	    exit 1; \
# 	fi
# 	@ if [ -z "${DOCKER_PASSWORD}" ]; then \
# 	    echo "Error: DOCKER_PASSWORD is not set"; \
# 	    exit 1; \
# 	fi
# 	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ docker push ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ echo "Image pushed: ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}"

# print-vars:
# 	@ echo "DOCKER_REGISTRY=${DOCKER_REGISTRY}"
# 	@ echo "DOCKER_USERNAME=${DOCKER_USERNAME}"
# 	@ echo "DOCKER_PASSWORD=${DOCKER_PASSWORD}"

# build:
# 	@ docker build -t ${IMAGE_NAME}:${VERSION} .

# run:
# 	@ docker run --name ${CONTAINER_NAME} -p ${HOST_PORT}:${CONTAINER_PORT} ${IMAGE_NAME}:${VERSION} 

# rm:
# 	@ docker stop ${CONTAINER_NAME}
# 	@ docker rm ${CONTAINER_NAME}

# docker-login:
# 	@ echo "Logging in to Docker..."
# 	@ echo ${DOCKER_TOKEN} | docker login -u ${DOCKER_USERNAME} --password-stdin ${DOCKER_REGISTRY}
# 	@ echo "Login successful!"

# push: build
# 	@ if [ -z "${DOCKER_REGISTRY}" ]; then \
# 	    echo "DOCKER_REGISTRY is not set. Using default (docker.io)"; \
# 	    DOCKER_REGISTRY="docker.io"; \
# 	fi
# 	@ if [ -z "${DOCKER_USERNAME}" ]; then \
# 	    echo "Error: DOCKER_USERNAME is not set"; \
# 	    exit 1; \
# 	fi
# 	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ docker push ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
# 	@ echo "Image pushed: ${DOCKER_REGISTRY}/${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}"

# print-vars:
# 	@ echo "DOCKER_REGISTRY=${DOCKER_REGISTRY}"
# 	@ echo "DOCKER_USERNAME=${DOCKER_USERNAME}"

