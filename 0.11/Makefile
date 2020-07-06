user_name = kodrclub
repo_name = terratest
short_ver = 0.11
long_ver  = 0.11.13


image_name = ${user_name}/${repo_name}
short_fqin = ${image_name}:${short_ver}
long_fqin  = ${image_name}:${long_ver}



all: build tag push

build:
	docker build -t ${short_fqin} .

tag:
	docker tag ${short_fqin} ${long_fqin}

push:
	docker push ${short_fqin}
	docker push ${long_fqin}
