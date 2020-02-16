# Quarkus service running on AWS Lambda

This one is based on the `quarkus-amazon-lambda-http-archetype`. The main difference is that it is not usind SAM but the [serverless framework](https://serverless.com/).

Build with

    mvn clean package -Dnative=true -Dnative-image.docker-build=true

Try locally with

    sls invoke local --docker -f hello --path event.json --xtype=[native|jvm]

Deploy with

    aws-vault exec profilealias -- sls deploy -v --xtype=[native|jvm]

Try with

    aws-vault exec profilealias -- sls invoke -f hello -l --path event.json

Or simply

    curl https://<apigw-id>.execute-api.eu-central-1.amazonaws.com/dev/hello
