FROM docker.pkg.github.com/nolte/vscode-devcontainers/golang:latest

#RUN mkdir -p ${WORKON_HOME} \
#  && virtualenv -p python3 ${WORKON_HOME}/cookiecutter \
#  && source ${WORKON_HOME}/cookiecutter/bin/activate \
#  && pip install cookiecutter jinja2-ansible-filters pytest-cookies json-diff autopep8 pylint jsbeautifier \
#  && deactivate

ARG HUGO_VERSION=0.71.0

USER root

RUN mkdir -p /tmp/hugo \
  && curl -sSL -k https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_Linux-64bit.tar.gz -o /tmp/hugo/hugo.tar.gz \
  && tar -zxf /tmp/hugo/hugo.tar.gz -C /tmp/hugo/ \
  && mv /tmp/hugo/hugo /usr/local/bin/hugo \
  && chmod +x /usr/local/bin/hugo \
  && rm -rf /tmp/hugo

USER ${USERNAME}

