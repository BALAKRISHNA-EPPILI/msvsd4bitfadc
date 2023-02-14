# msvsd4bitfadc

# Week 0 AIs

## Day 1

Install Oracle virtual box (Version 6.0.10 platform) with Ubuntu 20.04 - RAM at least 4GB, hard-disk atleast 50GB

 ## Day 2

As, of now for starting this workshop we need some tools which one can say the prerequisites needed for this workshop .
So, for that we need to install some tools.

These tools are listed below-

--> magic

--> netgen

--> ngspice

--> xschem

--> open_pdks(sky130)

--> Align tool

### magic TOOL Installation

It is an open-source VLSI layout tool.<br /><br />
Install steps:
```
$  git clone git://opencircuitdesign.com/magic
$  cd magic
$	 ./configure
$  make
$  sudo make install
```
More information [http://opencircuitdesign.com/magic/index.html](http://opencircuitdesign.com/magic/index.html)


### Netgen
It is a tool for comparing netlists, a process known as LVS, which stands for "Layout vs. Schematic" <br /><br />
Install steps:
```
$  git clone git://opencircuitdesign.com/netgen
$  cd netgen
$	./configure
$  make
$  sudo make install
```
More information [http://opencircuitdesign.com/netgen/index.html](http://opencircuitdesign.com/netgen/index.html)

### Xschem
Xschem is a schematic capture program <br /><br />
Install steps:
```
$  git clone https://github.com/StefanSchippers/xschem.git xschem_git
$	./configure
```

![1](https://user-images.githubusercontent.com/88899069/218766060-0320b1a5-663f-4dc3-86de-4a5656cc478f.png)

![2](https://user-images.githubusercontent.com/88899069/218766097-5f4626bd-da6a-4e4a-9e76-dd0284c5b4fc.png)

(If the above configuration command fails with an error such as "xpm not found" or "Aborted (core dumped)", this indicates that the library is missing. If so, perform the command below:-

```
$	sudo apt install libxpm-dev
```

![3](https://user-images.githubusercontent.com/88899069/218766110-f17de430-7fdf-4ec8-a442-2a87469aca1b.png)

Now again run command

```
$	./configure
$  make
$  sudo make install
```


![4](https://user-images.githubusercontent.com/88899069/218766134-16ac9061-a584-4687-a495-42edec5c941f.png)

![5](https://user-images.githubusercontent.com/88899069/218766147-08dbc77f-41c4-4561-8dd9-21572cda57b4.png)

![6](https://user-images.githubusercontent.com/88899069/218766176-c5d7eaee-cc4b-4b5f-8ea9-d5288250bb65.png)

![7](https://user-images.githubusercontent.com/88899069/218766184-d35be9b3-ea00-49b2-b87a-159d6a281b2e.png)

![8](https://user-images.githubusercontent.com/88899069/218766195-05bdec4e-b3e0-4fd9-b504-06308a7d7395.png)

![9](https://user-images.githubusercontent.com/88899069/218766214-ca02cb60-8e85-4e3c-abd5-658127675aed.png)


More information [http://repo.hu/projects/xschem/index.html](http://repo.hu/projects/xschem/index.html)

### Ngspice
ngspice is the open-source spice simulator for electric and electronic circuits.<br /><br />
Install steps:<br />

After downloading the tarball from [https://sourceforge.net/projects/ngspice/files/](https://sourceforge.net/projects/ngspice/files/) to a local directory, unpack it using:
```
 $ tar -zxvf ngspice-37.tar.gz
 $ cd ngspice-37
 $ mkdir release
 $ cd release
 $ ../configure  --with-x --with-readline=yes --disable-debug
 $ make
 $ sudo make install
```
More information [https://ngspice.sourceforge.io/index.html](https://ngspice.sourceforge.io/index.html)

Please note that to view the simulation graphs of ngspice, xterm is required and can be installed using.
```
$ sudo apt-get update
$ sudo apt-get install xterm
```

### open_pdk

Open_PDKs is distributed with files that support the Google/SkyWater sky130 open process description [https://github.com/google/skywater-pdk](https://github.com/google/skywater-pdk). Open_PDKs will set up an environment for using the SkyWater sky130 process with open-source EDA tools and tool flows such as magic, qflow, openlane, netgen, klayout, etc.<br /><br />
Install steps:
```
$  git clone git://opencircuitdesign.com/open_pdks
$  open_pdks
$	./configure --enable-sky130-pdk
$  make
$  sudo make install
```


![1 1](https://user-images.githubusercontent.com/88899069/218765374-34f77769-6c97-4bf0-aee4-7b2e59444931.png)

![2](https://user-images.githubusercontent.com/88899069/218765439-510c504e-272f-41e6-aa43-05533be6dc3f.png)

![3](https://user-images.githubusercontent.com/88899069/218765460-ba93bf45-09b0-4c5b-a342-cefae7746734.png)

![4](https://user-images.githubusercontent.com/88899069/218765480-92eaa937-2ed4-492b-ad5b-2c196ec167b0.png)

![5](https://user-images.githubusercontent.com/88899069/218765494-57bd04eb-c1a2-42e0-b0b4-c16ebca70044.png)


Now that we have all the necessary tools installed let's understand the design flow!



### ALIGN TOOL Installation 

There are some prerequisites needed before installing the ALIGN Tool 

```
1. gcc >=6.1.0(For C++14 support)

2. Python>=3.7
```



Note:- In my UBUNTU 22.04 , 

gcc-9 version is Installed

and python3 3.10 version is installed

**If gcc or python is not installed then install it using the command which are given below:-

```
sudo apt-get install gcc-9
```


 check gcc –version

```
sudo apt-get install python3
```

check python3 –version

NOTE:- It is must to met the prerequisite before installing the tool

For installing the align tool , Just follow these steps which are given below:-

Go to Desktop or that directory/path where you want to install the ALIGN Tool and write these commands which is given below:- 


```
$           export CC=/usr/bin/gcc

$           export CXX=/usr/bin/g++

$            git clone https://github.com/ALIGN-analoglayout/ALIGN-public

$           cd ALIGN-public
```
![1](https://user-images.githubusercontent.com/88899069/218770277-88b5c184-a8fa-4835-b833-cf92ee021196.png)




#### Now we need to create a Python virtual environment

As , we have installed the Python 3 so, follow these commands which are given below inside the ALIGN-public directory:

```
$          python3 -m venv general

$          source general/bin/activate

$          python3 -m pip install pip --upgrade
```

Note :- If you have only python version then , write python command instead of python3 in above commands 




Now, there are 2 process that one can install ALIGN as a USER or as a DEVELOPER

#### For installing ALIGN as a USER 

```
$          pip install -v .
```
![12](https://user-images.githubusercontent.com/88899069/218771470-d973decd-1163-4d7e-a1a3-f7e91bd9a1ec.png)



Note:- If after running this command it’s showing some error like gcc is not there or wheel not found 
“Building wheel for align (pyproject.toml) did not run successfully”
Could not build wheels for align , which is required to install pyproject.toml-based projects “

run this command inside ALIGN-public 

```
$             python3 -m pip install wheel setuptools pip –upgrade
```


or for solving that gcc error if it’s coming like gcc already satisfied gcc not found when typing gcc –version then , for that we need to change the softlink from /usr/bin 

or create a new softlink or symbolic link 

before that run these commands and then try again to install 

```
$             sudo apt update
$             sudo apt install build-essential
$             sudo apt-get install manpages-dev 
```

Now , if still error persist then, create softlink now 

```
$             cd
$             cd /usr/bin/
$             ls
 see gcc is there or not 
if there are more than one gcc are there then run this command 
$             sudo rm /usr/bin/gcc
```

![3](https://user-images.githubusercontent.com/88899069/218777046-8ba934af-27f2-4ce5-8cec-3e11ab37e641.png)

![4](https://user-images.githubusercontent.com/88899069/218777072-044fe870-a31f-40ae-b38b-47fd42790eee.png)

!
Now again run this 

```
$             ls
$             sudo ln -s /usr/bin/gcc-9 /usr/bin/gcc
$             gcc –version
```

It will show now the version of gcc 

If you are again installing ALIGN as USER:-

```
$             pip install -v .
```


![7 1](https://user-images.githubusercontent.com/88899069/218777537-4300a9ab-ee7c-4b96-8053-0ce7dd7b8fe0.png)


Now, run that command of installing ALIGN as a user .
it will successfully run now .

```
$      git clone https://github.com/ALIGN-analoglayout/ALIGN-pdk-sky130
```

![7](https://user-images.githubusercontent.com/88899069/218771559-75fb9fd4-59ee-485e-9dbf-0326f063ff1d.png)


After installing ALIGN-pdk-sky130 go to ALIGN-public folder and copy the SKY130_PDK folder and paste inside pdks folder in ALIGN-public folder.




#### If you are installing ALIGN as a DEVELOPER:-


```
$             pip install -e .
```




Now, after this installation of either ALIGN as a user or ALIGN as a DEVELOPER then, run these commands :-   

```
$             pip install setuptools wheel pybind11 scikit-build cmake ninja
$             pip install -v -e .[test] --no-build-isolation
$             pip install -v --no-build-isolation -e . –no-deps –install-option=’-DBUILD_TESTING=ON’

```





Making ALIGN Portable to SKY130 technology 

clone the following Repository inside ALIGN-public directory

```
git clone https://github.com/ALIGN-analoglayout/ALIGN-pdk-sky130

```


move SKY130_PDK folder to the following location

/Users/balakrishna/ALIGN-public/pdks 


```
$ Installing Xschem

```


Install xchem where you have installed all the tools 

```
$             git clone https://github.com/StefanSchippers/xschem.git xschem_git   
$             cd xschem_git
$              ./configure

```


(If the above configure command is giving error like xpm not found “Aborted (core dumped)  it means that this library is missing then run this command which is given below :-)


```
$              sudo apt install libxpm-dev 

```  
Now , run ./configure command 



```
$              make

```                      

{# if tgis is also giving some error then run this command instead of this make -j$(nproc) }


```
$              sudo make install

```   

```
For opening or checking that xschem is installed or not , write this command under xschem_git directory

$                    xschem

This command opens up the xschem on your screen

for closing it write this 

exit

``` 






After the open_pdks is installed , verifying this installation and to do interface this with sky130 just follow the given steps mentioned below:-
    1) Create  folder with any name inside xschem . In my case , I have created a folder with the name xschem_simulations.
    
    2) Now, go to open_pdks/sky130/sky130A/libs.tech/xschem.
    
    3) Copy xschemrc file from this location 
    
    4) Go back to that folder which you have created in {step 1} and paste that xschemrc file inside the xschem_simulations .
    
    5) Now, open terminal in this xschem_simulations folder and type this command “xschem”
    
    6) You will notice that a display  has come in which xschem is now launched with all the sky130 processes , now you can proceed and start making your project.
    
    ![24](https://user-images.githubusercontent.com/90523478/218184601-6e911eb9-121b-41f3-9bd1-bbecac2fbf34.png)
    
