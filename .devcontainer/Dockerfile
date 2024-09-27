# This is only required because metabase doesn't support duckdb on the alpine image, with debian image it works
FROM mcr.microsoft.com/devcontainers/typescript-node:22-bullseye

ENV TZ=Australia/Sydney

RUN apt-get update && apt-get -y install --no-install-recommends neovim git bash-completion

# configure dotfiles
RUN git clone https://github.com/altr/dotfiles && echo "cloned"

# configure terminal & fonts
RUN /dotfiles/font_install.sh
RUN rm -r /dotfiles

# configure git as node user
USER node
RUN git config --global user.email 'alain@altr.ch' && git config --global user.name 'Al'
RUN /dotfiles/bash_setup.sh
