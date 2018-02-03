# AWS Lambda HTTP Proxy
An HTTP Proxy for AWS Lambda with ingoing and outgoing domains whitelist
for CORS requests.

## Configuration
You first need to create the `src/main/resources/whitelist.properties` file
and add your desired domains to whitelist
```properties
whitelist.ingoing=protocol://domain[:port].tld
whitelist.outgoing=somewebsite.tld,anotherwebsite.tld
```

## Deployment
Deployment is done through [Serverless](https://serverless.com/framework/docs/providers/aws/guide/credentials/)
```bash
npm install serveless -g
cd aws-lambda-http-proxy/
mvn package
export AWS_ACCESS_KEY_ID=<your-key-here>
export AWS_SECRET_ACCESS_KEY=<your-secret-key-here>
serverless deploy --stage [dev|production] --region [aws-region]
```