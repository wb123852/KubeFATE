NAME = federatedai/kubefate
VERSION = v1.2.0

build-linux-binary:
	go build -a -ldflags '-s' -installsuffix cgo -o kubefate kubefate.go

build-docker-image:
	docker build -t ${NAME}:${VERSION} .

release: build-linux-binary
	tar -czvf kubefate-k8s-${RELEASE_VERSION}.tar.gz kubefate cluster.yaml cluster-serving.yaml config.yaml kubefate.yaml rbac-config.yaml examples

clean:
	rm kubefate

# Run go fmt against code
fmt:
	go fmt ./...

# Run go vet against code
vet:
	go vet ./...