Docker + Spray micro service
======================
1. Run `sbt assembly` - this will create a fat-jar with the server

2. Build the docker image: `docker build .`. Note the final image id.

3. Run a container basing on the image, remapping the ports: `docker run --rm -p 9090:8080 [image id]`

4. Enjoy! Example requests:
```
curl "http://localhost:9090/hello"
curl "http://localhost:9090/counter/c1"
curl -XPOST "http://localhost:9090/counter/c1?amount=1234"
```

