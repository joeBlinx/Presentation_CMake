FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y python3 \
			python3-pip \
			g++ \
			gcc
			
RUN python3 -m pip install cmake

RUN useradd -m cmake_user && yes cmake | passwd cmake_user
RUN apt-get clean
USER cmake_user
WORKDIR /home/cmake_user
