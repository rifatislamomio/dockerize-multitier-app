VERSION:=v0.01
IMAGE_NAME:=backend
HOST_PORT:=8000
CONTAINER_PORT:=3000
CONTAINER_NAME:=backend

build:
	@ docker build -t ${IMAGE_NAME}:${VERSION} .

run:
	@ docker run -p ${HOST_PORT}:${CONTAINER_PORT} -e APP_PORT=${CONTAINER_PORT} -name ${CONTAINER_NAME} ${IMAGE_NAME}:${VERSION}

rm:
	@ docker stop ${CONTAINER_NAME}
	@ docker rm ${CONTAINER_NAME}
