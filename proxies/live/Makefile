

list:
	@grep '^[^#[:space:]].*:' Makefile

build:
	rm -rf ./dist || true
	mkdir -p ./dist/apiproxy
	cp -r ./apiproxy ./dist

deploy: build
	cd ./dist && apigeetool deployproxy -V -o nhsd-nonprod -e internal-dev -n ambulance-analytics-api -t $$(get_token)

undeploy:
	apigeetool undeploy -V -o nhsd-nonprod -e internal-dev -n ambulance-analytics-api  -t $$(get_token)

delete:
	apigeetool delete -V -o nhsd-nonprod -n ambulance-analytics-api  -t $$(get_token)

install:
	npm install --dev
