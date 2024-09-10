###########################################
# BASE IMAGE
###########################################

FROM ubuntu:latest AS build

RUN apt-get update && apt-get install -y python3 python3-pip

ENV NAME World

COPY . .

#RUN python3 build -o /app .

ENTRYPOINT ["/app"]

