FROM kodrclub/golang-gcc:1.14
LABEL maintainer="Juan Manuel Medina"

RUN wget https://releases.hashicorp.com/terraform/0.12.28/terraform_0.12.28_linux_amd64.zip
RUN unzip terraform_0.12.28_linux_amd64.zip
RUN rm terraform_0.12.28_linux_amd64.zip
RUN mv terraform /usr/local/go/bin/terraform

CMD ["go", "test"]