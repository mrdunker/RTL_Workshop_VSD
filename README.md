# iiitb_emil_class
This github repository summarises the work done on 31/07/2023

# Day 0
Following are the steps for installation:
<details>
<summary> Yosys</summary>

```
$ git clone https://github.com/YosysHQ/yosys.git<br />
$ cd yosys-master <br />
$ sudo apt install make (If make is not installed please install it) <br />
$ sudo apt-get install build-essential clang bison flex <br />
    libreadline-dev gawk tcl-dev libffi-dev git <br />
    graphviz xdot pkg-config python3 libboost-system-dev <br />
    libboost-python-dev libboost-filesystem-dev zlib1g-dev<br />
$ make config-gcc<br />
$ make <br />
$ sudo make install<br />
```
![yosys](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/345a1e66-96c9-4baa-b543-4c54a83c7f80)
</details>
<details>
<summary> Icarus verilog</summary>

```
Steps to install iverilog
sudo apt-get install iverilog
```
![iverilog](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/bb03caee-57ee-4d01-bd57-25e85e0f302f)
</details>
<details>
<summary> GTKWave </summary>

```
Steps to install gtkwave
sudo apt update
sudo apt install gtkwave
```    
![gtkwave](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/61dea6a3-487c-4308-a8c4-f1d4477c992a)
</details>

<details>
<summary>OpenSTA</summary>

```
Went to the github repo: https://github.com/The-OpenROAD-Project/OpenSTA
and did the processes mentioned


```
</details>
<details>
<summary>ngspice</summary>   

```
After downloading the tarball from https://sourceforge.net/projects/ngspice/files/ to a local directory, unpack it using:
$ tar -zxvf ngspice-40.tar.gz
$ cd ngspice-40
$ mkdir release
$ cd release
$ ../configure  --with-x --with-readline=yes --disable-debug
$ make
$ sudo make install

```
Image after installation:
![ngspice](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/22a4dab7-b6dc-4d07-b2a8-8f2d24b06568)
</details>

<details>
<summary>magic</summary>

```
$   sudo apt-get install m4
$   sudo apt-get install tcsh
$   sudo apt-get install csh
$   sudo apt-get install libx11-dev
$   sudo apt-get install tcl-dev tk-dev
$   sudo apt-get install libcairo2-dev
$   sudo apt-get install mesa-common-dev libglu1-mesa-dev
$   sudo apt-get install libncurses-dev
git clone https://github.com/RTimothyEdwards/magic
cd magic
./configure
make
make install

```
Image after installation:
</details>





