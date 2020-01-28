
IMAGE_TAG=stax:rails-6
REPO ?= $(REPO)

build:
	@docker build -t $(IMAGE_TAG) .

clean:
	@docker image rm $(IMAGE_TAG)

login:
	@eval $$(aws ecr get-login --no-include-email --region us-east-2)

tag:
	@docker tag $(IMAGE_TAG) $(REPO)/$(IMAGE_TAG)

push: login
	@docker push $(REPO)/$(IMAGE_TAG)


.PHONY: build clean login tag push
