###########################################
# BASE IMAGE
###########################################

FROM ubuntu:latest AS build

RUN apt-get update && apt-get install -y python3 python3-pip

#set working directory
WORKDIR /app
ENV NAME world

#copy source code to build container
COPY . .

#RUN python3  build -o /app .
############################################
# HERE STARTS THE MAGIC OF MULTI STAGE BUILD
############################################

FROM python:3.9-slim AS runtime

WORKDIR /app

# Copy the compiled binary from the build stage
COPY --from=build /app /app

# Set the entrypoint for the container to run the binary
ENTRYPOINT ["/app"]

