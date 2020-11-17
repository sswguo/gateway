# Gateway
API gateway works as a facade to hide micro services from end users.
Under the hook, it receives HTTP requests from client (e.g., mvn) and
forward to different services.

There is a classifier which determines the target service via Url
patterns. For example, "/api/content" go to indy and "/api/promote"
go to promotion.

## Prerequisite
1. jdk11
2. mvn 3.6.2+

## Try it!
```$ mvn compile quarkus:dev```

This will start Gateway in debug mode. Open another terminal and try
some maven build, e.g,

```$ mvn clean install -s <path-to>/settings-gateway.xml```

The settings-gateway.xml is at the project root directory for test
purpose.

You can also deploy artifacts to a repository, e.g,

```$ mvn deploy -s <path-to>/settings-gateway.xml```

To test it, you need to **start a local Indy** and the artifacts are put on
**maven/hosted/local-deployments**.
