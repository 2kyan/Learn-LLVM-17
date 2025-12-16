# https://containers.dev/features & https://github.com/devcontainers/features
# https://github.com/devcontainers/images
# https://github.com/devcontainers/templates/
# https://containers.dev/guide/dockerfile
# https://hub.docker.com/u/microsoft

ARG VARIANT=5-linux
#FROM mcr.microsoft.com/devcontainers/cpp:${VARIANT}
FROM mcr.microsoft.com/devcontainers/universal:${VARIANT}

USER root

RUN find /etc/apt/sources.list* -type f -exec sed -i 's/ deb/ deb deb-src/' '{}' +

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive

RUN apt-get -y install vim cmake cppcheck valgrind clang lldb llvm gdb ninja-build

RUN apt-get autoremove -y && apt-get clean -y && rm -rf /var/lib/apt/lists/*

USER vscode

# [Optional] Uncomment this section to install additional packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>
