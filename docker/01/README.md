# Docker - custom httpd image - web server

## tasks

- Build a custom apache image from the latest httpd image , using Dockerfile, in which you override the default index file by the attached `index.html` file
- publish the image to the public docker register (create an account if you don't have one already)
- write a docker-compose.yml file using the custom built image
- (Optional) disable directory listing which is enable by default, hints : you will need a volume to provide your own `httpd.conf` file, or you can override it during the image build step.

# Solution

1. clone ur repository.
2. i have create the Dockerfile and i pull the httpd official image from the docker hub and i wrote the content of the Dockerfile.
3. i have builded the Apache image using this command:

```
docker build -t mohamedlehbib/custom-apache .
```

4. then i logged into my docker hub account using my username:

```
docker login -u mohamedlehbib
```

5. then i pushed the image into docker hub command:

```
docker push mohamedlehbib/custom-apache
```

6. then i created the docker-compose.yml and i wrote it content.
7. then i started the services in the docker-compose.yml using this command:

```
docker-compose up -d
```

8. then i have added a httpd.conf and code with totale help of chatgpt for the configuration code.
9. then i have added this line to the Dockerfile to override the httpd.conf
   `COPY ./httpd.conf /usr/local/apache2/conf/httpd.conf`
10. then i rebuilded the image and then i pushed it to docker hub

```
docker build -t mohamedlehbib/custom-apache . && docker push mohamedlehbib/custom-apache
```

## thanks for this katas i have got introduced to something new in it and i have had some help from google and chatgpt. And thanks for ur time.
