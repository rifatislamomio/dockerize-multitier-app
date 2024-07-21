VERSION:=v0.01
IMAGE_NAME:=frontend
HOST_PORT:=80
CONTAINER_PORT:=80
CONTAINER_NAME:=frontend
DOCKER_REGISTRY:=docker.io

build:
	@ docker build -t ${IMAGE_NAME}:${VERSION} .

run:
	@ docker run -p ${HOST_PORT}:${CONTAINER_PORT} -e APP_PORT=${CONTAINER_PORT} -name ${CONTAINER_NAME} ${IMAGE_NAME}:${VERSION}

rm:
	@ docker stop ${CONTAINER_NAME}
	@ docker rm ${CONTAINER_NAME}

docker-login:
	@ echo "Docker Login"
	@ @echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_USERNAME} --password-stdin ${DOCKER_REGISTRY}

docker-push:
	@ docker tag ${IMAGE_NAME}:${VERSION} ${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}
	@ docker push ${DOCKER_USERNAME}/${IMAGE_NAME}:${VERSION}