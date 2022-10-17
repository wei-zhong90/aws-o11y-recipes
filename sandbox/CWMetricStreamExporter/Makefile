.DEFAULT_GOAL := go_build

go_build:
	cd lambda && go build -o main main.go

go_test:
	cd lambda && go test -v -race -count=1 ./...

npm_build:
	cd cdk && npm install && npm run build

npm_test:
	cd cdk && npm run build && npm test

npm_lint:
	cd cdk && npm run lint

build:
	@npm run build

destroy:
	@cd cdk && cdk destroy
	@aws amp delete-workspace --workspace-id `aws amp list-workspaces --alias prometheus-sample-app --query 'workspaces[0].workspaceId' --output text`
