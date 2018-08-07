
# Introduction
If you are using Docker for Mac or Docker for Windows, you can use http://localhost as the IP address, and open http://localhost:8000 in a web browser.

# References
https://docs.docker.com/compose/wordpress/

# Copy volumes
Usually what I do in this situation is use a container that can produce a tar file. For example:

docker run --rm -v volumename:/vol -w /vol alpine tar -C . > volumename.tar

It's a little longer than your proposed docker volume save, but it gets the job done.

Similarly, docker volume load becomes something like this:

docker run --rm -v volumename:/vol -w /vol -i alpine tar -x < volumename.tar

