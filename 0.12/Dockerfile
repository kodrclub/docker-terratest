FROM kodrclub/golang-gcc:1.14
LABEL maintainer="Juan Manuel Medina"

RUN wget https://releases.hashicorp.com/terraform/0.12.28/terraform_0.12.28_linux_amd64.zip \
    && unzip terraform_0.12.28_linux_amd64.zip \
    && rm terraform_0.12.28_linux_amd64.zip \
    && mv terraform /usr/local/go/bin/terraform

CMD ["go", "test"]