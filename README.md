# msvsd4bitfadc


As, of now for starting this worskhop we need some tools which one can say the prerequisites needed for this workshop .
So, for that we need to install some tools.

These tools are listed below-

--> magic
netgen
ngspice
xschem
open_pdks(sky130)
Align tool

## ALIGN TOOL Installation 

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


#### Now we need to create a Python virtual environment

As , we have installed the Python 3 so, follow these commands which are given below inside the ALIGN-public directory:

```
$          python3 -m venv general

$          source general/bin/activate

$          python3 -m pip install pip --upgrade
```

Note :- If you have only python version then , write python command instead of python3 in above commands 




Now, there are 2 process that one can install ALIGN as a USER or as a DEVELOPER

** For installing ALIGN as a USER 

```
$          pip install -v .
```

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



!
Now again run this 

```
$             ls
$             sudo ln -s /usr/bin/gcc-9 /usr/bin/gcc
$             gcc –version
```

It will show now the version of gcc like this as shown below:-



Now, run that command of installing ALIGN as a user .
it will successfully run now .

### If you are installing ALIGN as a DEVELOPER:-


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

/Users/vanshikatanwar/ALIGN-public/pdks 


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




#Now install the Open_PDKS 

```
$                    git clone git://opencircuitdesign.com/open_pdks
$                    open_pdks
$                    ./configure --enable-sky130-pdk
$                    make
$                    sudo make install

``` 

After the open_pdks is installed , verifying this installation and to do interface this with sky130 just follow the given steps mentioned below:-
    1) Create a folder with any name inside xschem . In my case , I have created a folder with the name xschem_simulations.
    
    2) Now, go to open_pdks/sky130/sky130A/libs.tech/xschem.
    
    3) Copy xschemrc file from this location 
    
    4) Go back to that folder which you have created in {step 1} and paste that xschemrc file inside the xschem_simulations .
    
    5) Now, open terminal in this xschem_simulations folder and type this command “xschem”
    
    6) You will notice that a display  has come in which xschem is now launched with all the sky130 processes , now you can proceed and start making your project.
    
    ![24](https://user-images.githubusercontent.com/90523478/218184601-6e911eb9-121b-41f3-9bd1-bbecac2fbf34.png)
    
