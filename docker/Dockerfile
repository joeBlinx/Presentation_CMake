FROM debian:bullseye-slim

RUN apt-get update && apt-get install -y python3 \
			python3-pip \
			g++ \
			gcc \
            wget
			
RUN wget https://github.com/Kitware/CMake/releases/download/v3.21.2/cmake-3.21.2-linux-x86_64.tar.gz

RUN tar -xf cmake-3.21.2-linux-x86_64.tar.gz 
RUN useradd -m cmake_user && yes cmake | passwd cmake_user
RUN mv cmake-3.21.2-linux-x86_64 /home/cmake_user/cmake
RUN echo "export PATH=$PATH:/home/cmake_user/cmake/bin" >> /home/cmake_user/.bashrc

RUN apt-get clean
USER cmake_user
WORKDIR /home/cmake_user
