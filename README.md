# MATM Wallet Miner
MATM Wallet Miner is an open source project developed in GO.




## ATTENTION
It is RECOMMENDED (NOT OBLIGATORY) to disable windows defender or other antivirus when the miner is running as they limit the usable resources of the computer.
IF YOU DO NOT TRUST THE SOFTWARE, IT CAN CONTINUE TO WORK EVEN WITH DEFENDER ACTIVATED.

**--> IF YOU CONTINUE TO DOUBT ABOUT RELIABILITY READ THE CODE YOURSELF <--**

__NOBODY__ forces you to use my miner.

# Instructions for compiling
Download & install GO lang from https://go.dev/

Download & install MSYS2 from https://www.msys2.org/

Open C:\msys64\msys2.exe and run:
```
pacman -Syu
```
```
pacman -Su
```

Open C:\msys64\mingw64.exe and run these 2 commands: 

| 32 bit          | 64 bit            |
|     :---:    |     :---:      |
| ```pacman -S mingw-w64-i686-gcc```   | ```pacman -S mingw-w64-x86_64-gcc```     |
| ```pacman -S mingw-w64-i686-gcc```     | ```pacman -S mingw-w64-x86_64-gdb```       |


Now we need to add the gcc directory to the environment variables, to do that we need to find its location. Commonly found in:

| 32 bit          | 64 bit            |
|     :---:    |     :---:      |
| ```C:\msys64\mingw64\bin```   | ```C:\msys64\mingw32\bin```     |

Once found add it to your PATH variable from advanced system properties.

To verify correct installation run:
```
gcc –-version
```
and
```
gdb -–version
```
If you see an error then repeat the whole process. Otherwise you can continue with the guide

Open new terminal, go to the software folder and run
```
go build main.go
```
If you don't see any output the compiling process was successful and you should be able to see the main.exe file in the folder.


<details><summary>FAQ</summary>
<p>
__How does it work?__
  
> The software generates hexadecimal sequences of 32 bytes each, which will create a key.
The key will then be controlled by the software using free nodes (https://rpc.ankr.com/eth) which will return the wallet balance.
If it is greater than 0 it will mark it as valid.

__How can I use it?__
> At the moment the software is only available for Windows platforms.
To use it, simply go to the build folder and you will find the file already compiled.
Otherwise you can download the source code and compile it yourself but you will need a compiler.

__What are Threads and GoRutines?__
> Threads (also called GoRoutine) are child processes of the main (Main routine).
The higher the amount you choose, the faster the program will generate new keys.

Too many Threads can create inconvenience to your computer,
if you are unsure about the right amount for you just type 0 when prompted and the program will automatically detect the best settings for you.
</p>
</details>
