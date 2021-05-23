# Secure Auth v0: Reverse 14

### One of NorzhNuclea's developers joined the team last quarter, specialized in authentication systems he found one he developed a few years ago with a innovative obfuscation method. Find the correct password to validate the checks.

I'm not going to lie this challenge made me think more than it probably should have. Essentially, all you needed to do was find the flag within the supplied ELF file.
This was my first time attempting such a task. Here's how I did it:

1. Downloaded the chall.zip with the file needed
2. Attempted to run the file via ```./chall```. Of course you don't know the correct string to input though. Kept getting the 'Failed !' response.
3. Ran ```file chall``` to see if it was stripped or not. It was.
4. Ran ```readelf -a chall``` just to get a glimpse at the files inner workings.
5. Ran ```strings chall``` and tried all output strings as password. None worked. I did notice a few interesting strings though.
6. Ran ```readelf -x .rodata chall``` gave me an output of hex codes and corresponding strings as expected.

<details>
  <summary>SPOILER: Flag</summary>

  ```Haven't Solved It Yet LOL```
  
</details>
