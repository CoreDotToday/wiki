<!-- TITLE: Apigateway -->
<!-- SUBTITLE: A quick summary of Apigateway -->

### 본문 매핑 템플릿
```
##  See http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-mapping-template-reference.html
##  This template will pass through all parameters including path, querystring, header, stage variables, and context through to the integration endpoint via the body/payload
#set($allParams = $input.params())
{
"body-json" : $input.json('$'),
"params" : {
#foreach($type in $allParams.keySet())
    #set($params = $allParams.get($type))
"$type" : {
    #foreach($paramName in $params.keySet())
    "$paramName" : "$util.escapeJavaScript($params.get($paramName))"
        #if($foreach.hasNext),#end
    #end
}
    #if($foreach.hasNext),#end
#end
},
"stage-variables" : {
#foreach($key in $stageVariables.keySet())
"$key" : "$util.escapeJavaScript($stageVariables.get($key))"
    #if($foreach.hasNext),#end
#end
},
"context" : {
    "account-id" : "$context.identity.accountId",
    "api-id" : "$context.apiId",
    "api-key" : "$context.identity.apiKey",
    "authorizer-principal-id" : "$context.authorizer.principalId",
    "caller" : "$context.identity.caller",
    "cognito-authentication-provider" : "$context.identity.cognitoAuthenticationProvider",
    "cognito-authentication-type" : "$context.identity.cognitoAuthenticationType",
    "cognito-identity-id" : "$context.identity.cognitoIdentityId",
    "cognito-identity-pool-id" : "$context.identity.cognitoIdentityPoolId",
    "http-method" : "$context.httpMethod",
    "stage" : "$context.stage",
    "source-ip" : "$context.identity.sourceIp",
    "user" : "$context.identity.user",
    "user-agent" : "$context.identity.userAgent",
    "user-arn" : "$context.identity.userArn",
    "request-id" : "$context.requestId",
    "resource-id" : "$context.resourceId",
    "resource-path" : "$context.resourcePath"
    }
}

```

#### Example
```
{'body-json': {},
 'context': {'account-id': '',
  'api-id': 'g9ulha7g39',
  'api-key': '',
  'authorizer-principal-id': '',
  'caller': '',
  'cognito-authentication-provider': '',
  'cognito-authentication-type': '',
  'cognito-identity-id': '',
  'cognito-identity-pool-id': '',
  'http-method': 'GET',
  'request-id': '9621af84-6b91-11e8-b44c-a764abb96d1a',
  'resource-id': 'zkg8wj',
  'resource-path': '/public-contents',
  'source-ip': '211.197.4.219',
  'stage': 'handson',
  'user': '',
  'user-agent': 'python-requests/2.18.4',
  'user-arn': ''},
 'params': {'header': {'Accept': '*/*',
   'Accept-Encoding': 'gzip, deflate',
   'Host': 'g9ulha7g39.execute-api.ap-northeast-2.amazonaws.com',
   'User-Agent': 'python-requests/2.18.4',
   'X-Amzn-Trace-Id': 'Root=1-5b1b4356-6a606680f4227493402ed5f3',
   'X-Forwarded-For': '211.197.4.219',
   'X-Forwarded-Port': '443',
   'X-Forwarded-Proto': 'https'},
  'path': {},
  'querystring': {'a': '1'}},
 'stage-variables': {},
 'test': 1}
 ```
