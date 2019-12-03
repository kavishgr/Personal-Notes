# Dumping memory on Windows

On 64-bit, there's `procdump64.exe`. 

Through `evil-winrm`, the upload function can be used to upload the executable. 

The `Sysinternals Suite` contains the executable. It contains both 32 and 64-bit. The download link:

{% embed url="https://docs.microsoft.com/en-us/sysinternals/downloads/sysinternals-suite" %}

Download it and unzip it, then upload it on the target through evil-winrm:

![](.gitbook/assets/procdump64.png)

Now use `Get-Process` to get a list of running processes:

![](.gitbook/assets/getproc.png)

Accept the procdump eula:

```text
./procdump64.exe -accepteula
```

Then run `./procdump64.exe -ma [ID]` to dump a process's memory:

![](.gitbook/assets/memdumped.png)



