All the requested functionality has been implemented and works as expected execept for `Testing hot reload for local development... ` fails when running `validate.sh`. However, when tested manually it works.

I have not exposed the app's port on the `Dockerfile` and `docker-compose.yml` so that it is only accessible via nginx.

I have used volumes on the docker-compose.yml file to add the ssl certificates to the running container without baking it in the container via Dockerfile.

I have used alpine based docker images as bas image for both `app` and `nginx` to make the image sizes as small as possible.
Multi-stage build can be used for images that compiles and package their code to reduce the size further.

Security on the docker images is ensured by using non-root user. For nginx for it to run as non-root will require as to run
nginx on port >1024, this affects port 80 and 444. 

Running ` docker-compose up` runs the application as expected.