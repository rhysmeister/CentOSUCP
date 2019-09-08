
# Build docker image
docker build --no-cache -t rhys .
# Start a container
docker run -ti --rm --privileged -v /sys/fs/cgroup:/sys/fs/cgroup:rw  rhys /usr/sbin/init
# Get container name
docker ps
# Access container by name
docker exec -ti boring_raman bash
