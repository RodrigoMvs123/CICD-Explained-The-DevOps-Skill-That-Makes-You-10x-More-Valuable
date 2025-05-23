## CICD Explained The DevOps Skill That Makes You 10x More Valuable

- https://www.youtube.com/watch?v=AknbizcLq4w 

What is CI/CD ? 

CI Pipeline 

- Build
- Unit Test
- Package
- Integration Tests

> Artifact Repository

CD Pipeline 

- Deploy to Dev Environment
- Integration / Security / Acceptance Tests / E2E Tests
- Deployment to Staging Environment
- Deployment to Production Environment 
- Monitoring / Logging / Alerting

**Continuous Integration**

> How do we fix merge issues and test failures ? ( Feature into the main branch )

Continuos Integration ( CI )
```
Better approach
Integrating our code changes often in small sizes into the main branch.
> Program the entire thing locally first for days and then push it to the remote 
 - Commit and push to remote more often 
 - Smaller changes are tested more frequently
``` 

CodeRabbit ( Testing before deployment using CI ) 

- https://www.coderabbit.ai/?utm_source=google&utm_medium=cpc&utm_campaign=20944421732&utm_content=158532047035&utm_term=code%20rabbit&matchtype=e&gad_source=1&gad_campaignid=20944421732&gbraid=0AAAAAqBNyQUlQeZyYpiM6wUbNtu_2avTf&gclid=Cj0KCQjwlMfABhCWARIsADGXdy_KxI3DCcgpoDv9FGZXDSY5q9o7tDgdxtHcvhUBUJbTj-Mke5EzVJcaAj6zEALw_wcB 

> Brilliant AI-Powered code review tool that helps identify this issues much earlier in the process.

> CodeRabbit analyzes the pull request automatically detecting potential bugs, security vulnerabilities and perform issues before they break the pipeline.

> It provides root course analyzes right in the pull request, so you can fix problems immediately.   

**Continuous Delivery**

> Github or Jenkins 

After tests are successful, and after been merged into the main branch, build the app into docker image, push to Docker Registry ( new artifact created ), connect to the server/cluster  ( dev environment ), run Docker image container and/or kubectl apply: 

```
$ nano deployment.yaml
$ docker build -t my-app:v2 .
$ kubectl config use-context dev
$ kubectl apply -f deployment.yaml
```

- Configure deployment tools
- Secure access settings
- Grant Jenkins permissions 
- Test workflow

#### Dev - End to End ( E2E ) Tests

Test the application in each step of the pipeline.

```
Click UI
Call API
Update DB
Confirm on UI
```

Post Deployment Pipeline checks:

> Verify app is running correctly 
> Check for security issues 

Security is important at all levels of the pipeline.

> Infrastructure 
> Runtime
> Application 

```bash
$ git pull origin main
```

Running against staging ( Continuous Deployment )

- Performance Tests
- Compliance Checks
- Security Tests

Deployment Strategies 

> Blue-Green Deployment

> Canary Deployment

App1 ( Old Version )  <-> App2 ( New Version )

