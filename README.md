# iiitb_emil_class
This GitHub repository summarises the class work done on Physical Design for ASICs (VL508)

# Day 0
Following are the steps for the installation of necessary tools:
<details>
<summary> Yosys</summary>
<br />
Yosys is a framework for Verilog RTL synthesis. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Selected features and typical applications:

- Process almost any synthesizable Verilog-2005 design
- Converting Verilog to BLIF / EDIF/ BTOR / SMT-LIB / simple RTL Verilog / etc.
- Built-in formal methods for checking properties and equivalence
- Mapping to ASIC standard cell libraries (in Liberty File Format)
- Mapping to Xilinx 7-Series and Lattice iCE40 and ECP5 FPGAs
- Foundation and/or front-end for custom flows<br />

Steps to install Yosys:
  
```
$ git clone https://github.com/YosysHQ/yosys.git
$ cd yosys-master 
$ sudo apt install make (If make is not installed please install it) 
$ sudo apt-get install build-essential clang bison flex 
    libreadline-dev gawk tcl-dev libffi-dev git 
    graphviz xdot pkg-config python3 libboost-system-dev
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
$ make config-gcc
$ make 
$ sudo make install
```
Image after Installation:
![yosys](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/345a1e66-96c9-4baa-b543-4c54a83c7f80)
</details>
<details>
<summary> Icarus verilog</summary>
<br />    
Icarus Verilog is an implementation of the Verilog hardware description language compiler that generates netlists in the desired format (EDIF). It supports the 1995, 2001 and 2005 versions of the standard, portions of SystemVerilog, and some extensions.<br />
Icarus Verilog is available for Linux, FreeBSD, OpenSolaris, AIX, Microsoft Windows, and Mac OS X. Released under the GNU General Public License, Icarus Verilog is free software.<br /><br />
Step to install iverilog: 
    
```
sudo apt-get install iverilog
```
Image after Installation:
![iverilog](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/bb03caee-57ee-4d01-bd57-25e85e0f302f)
</details>
<details>
<summary> GTKWave </summary>
<br />
GTKWave is a VCD waveform viewer based on the GTK library. This viewer supports VCD and LXT formats for signal dumps.<br />
Waveform dumps are written by the Icarus Verilog runtime program vvp. The user uses $dumpfile and $dumpvars system tasks to enable waveform dumping, then the vvp runtime takes care of the rest. The output is written into the file specified by the $dumpfile system task. If the $dumpfile call is absent, the compiler will choose the file name dump.vcd or dump.lxt, depending on runtime flags. The example below dumps everything in and below the test module.<br /><br />
Steps to install GTKWave:

```
sudo apt update
sudo apt install gtkwave
```
Image after Installation:
![gtkwave](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/61dea6a3-487c-4308-a8c4-f1d4477c992a)
</details>

<details>
<summary>OpenSTA</summary>
<br />
OpenSTA is a gate level static timing verifier. As a stand-alone executable it can be used to verify the timing of a design using standard file formats.

- Verilog netlist
- Liberty library
- SDC timing constraints
- SDF delay annotation
- SPEF parasitics

OpenSTA uses a TCL command interpreter to read the design, specify timing constraints and print timing reports.<br /><br />
Steps to install OpenSTA:
```
Went to the GitHub repo: https://github.com/The-OpenROAD-Project/OpenSTA
and did the process mentioned within (installed the prerequisites and installed OpenSTA with Cmake).
```
Image after installation:
![opensta png](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/bcc4cf94-2696-4f19-bfcd-20a48424276f)
</details>
<details>
<summary>Ngspice</summary>   
<br />
Ngspice is an open-source electronic circuit simulator software that allows engineers, researchers, and hobbyists to simulate and analyze electronic circuits. It is a part of the Spice (Simulation Program with Integrated Circuit Emphasis) family of circuit simulation tools, which have been widely used since the 1970s.

Ngspice is an evolution of the well-known Spice3 program, incorporating additional features and improvements. It is compatible with various operating systems, including Windows, Linux, and macOS. The software is primarily used for simulating analog, digital, and mixed-signal circuits.<br /><br />
Steps to install Ngspice:

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
<br />
Magic is a popular open-source tool used for ASIC (Application-Specific Integrated Circuit) design and layout. It is part of the Electric VLSI Design System and provides capabilities for creating and editing integrated circuit layouts. Magic is widely used in the semiconductor industry and academic settings for various ASIC design tasks.

<br /> Steps to install magic:

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
![magic](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/79c38c91-a0be-4b4b-a334-bb1ef3754af8)
</details>

<details>
<summary>OpenLANE</summary>
<br />
OpenLANE is an open-source ASIC (Application-Specific Integrated Circuit) design flow and methodology that aims to automate and standardize the process of designing and fabricating custom digital integrated circuits. It is developed and maintained by the OpenROAD (Open Research for Advanced Nanotechnologies) project, which is a collaboration of various academic and industrial organizations.

Key components and features of OpenLANE include:<br />
- RTL Synthesis: The flow starts with RTL synthesis, where the RTL code is converted into a gate-level representation using synthesis tools.
- Floorplanning: OpenLANE performs automatic floorplanning, which involves arranging the logical blocks and components on the chip's physical layout.
- Placement: It automatically places the gates and cells on the chip, optimizing for area, power, and performance.
- Clock Tree Synthesis (CTS): OpenLANE generates a clock tree to efficiently distribute the clock signal across the chip.
- Routing: The tool performs automatic routing to connect all the elements on the chip while adhering to design rules and constraints.
- Static Timing Analysis (STA): OpenLANE performs static timing analysis to verify that the design meets the required timing specifications.
- Design Rule Check (DRC) and Layout versus Schematic (LVS) verification: OpenLANE checks the physical layout against manufacturing rules (DRC) and compares the layout to the original schematic (LVS) to ensure consistency.
- Configuration and customization: OpenLANE allows users to configure various aspects of the design flow and customize different steps based on specific design requirements.
<br />
Steps to install OpenLANE:
    
```
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip make git

sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io

sudo docker run hello-world

sudo groupadd docker
sudo usermod -aG docker $USER
sudo reboot 

# After reboot
docker run hello-world

```
Image after installation:
![docker](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/ee51e4a0-bb4e-4e41-8ff6-e4cf30dcfcb7)
</details>

# Day 1
<details>
  <summary>Introduction</summary>
  <br />
  This section mainly focuses on Iverilog,GTKwave, and Yosys. The simulation and synthesis of a basic 2x1 mux is also done.<br /><br />
 A simulator refers to a software tool or program that simulates the behavior of the digital design described at the RTL level. It allows designers to test and verify 
 the functionality of their digital designs before actual hardware is fabricated. Simulators take the RTL description and execute it in a software 
 environment, allowing the designer to observe how the design behaves under different conditions and inputs. The simulator looks for changes in the input.Upon change inn 
 the input the output is evaluated. If no change in input is observed, there will be no change in output. 
 Icarus Verilog is an open-source RTL simulator that supports Verilog. It's widely used in academia and smaller projects due to its free and open nature.<br /><br/>
 A test bench is a set of simulation codes and associated data that is used to verify the correctness and functionality of a digital design described at the Register 
 Transfer Level (RTL) or other abstraction levels. It serves as a virtual environment in which the design can be tested before it's physically implemented in 
 hardware.The design may have  more than one input and output, while the Test bench doesn't a primary input or a primary output.<br /><br />

 **The Iverilog-based simulation flow is that of below:** <br />
 ![simulation flow](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/3d965540-bb96-4bb3-9284-b446b57621fb)

 After Simulation Synthesis is required. For this, we are using a tool called Yosys, which will give us a netlist, which is a representation of the design in standard 
 cells. There are certain commands like read_verilog, read_liberty, and write_verilog used for the synthesis process. After Synthesis verification of the netlist is also 
 done. <br /><br />
**A basic synthesis flow is as shown below:** <br />
 ![synthesis flow](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/abcd8a60-8222-433e-a53e-ff1485ecd810)
 <br />( .lib is explained in the 'Other Relevant Data' section)<br />
 <br />The set of primary inputs or primary outputs will remain the same in both RTL design and netlist,i.e. The testbench used for simulation and verification is same.<br />
</details>
<details>
    <summary>Verilog codes</summary>
  We are simulating a simple 2x1 mux using iverilog and GTKwave, the codes have been taken from the GitHub repo:<br />
  https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
  <br /><br />
  The above git has been cloned and saved in the local system as shown below.<br />
  
  ![git_clone](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/05e19c55-237f-47b0-b2df-4a4839a12e2c)
  
</details>

<details>
    <summary>Simulation: iverilog and GTKwave</summary>
  <br />
  The below Linux shell commands are typed into the terminal to get execute the mux design file and the test bench. A vcd(value change dump) file is generated
  and that is opened using GTKwave as shown below. 
  
```
iverilog good_mux.v tb_good_mux.v
./a.out
gtkwave tb_good_mux.vcd
```
Below are the Shell commands screenshot for the execution of both .v files (design and test bench):<br />
![iverilog_gtk](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/69775736-ff34-4c3c-8231-87dd9f111e2b)
<br />
<br />
Below is the GTKwave output for the same:<br />
![gtk](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/af652fdb-1222-484f-820c-51f3d4de732f)
</details> 
<details>
    <summary>Synthesis: Yosys</summary>
<br />
Here we are Synthesizing a basic 2x1 mux which we have simulated in iverilog and GTKwave as shown in the above sections.<br />
In the directory, we need to input the shell terminal command yosys for synthesis below shown are the commands used:
  
  ```
yosys> read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
yosys> read_verilog good_mux.v
yosys> synth -top good_mux
yosys> abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
yosys> show
  ```
To generate the netlist and view the 'netlist.v' file following commands are used:

 ```
yosys> write_verilog -noattr good_mux_netlist.v
yosys> !gvim good_mux_netlist.v
  ```

<br /> **The Screenshot below shows how commands read_liberty and read_verilog are done:** <br />
![synth1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/ef674f5e-94f0-4310-bd4a-dd87ab9c6a24)
<br />

**The Screenshot below is of the syth -top <name.v> command:** <br />
![synth2](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/35ee2316-6785-4509-a254-1d9e7607336f)
<br />

**The Screenshot below shows how the command abc -liberty is done:** <br />
![synth3](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/2f53dd5c-b782-4f0b-8185-c334c9d3f13a)
<br />

**The Screenshot below shows how the show command is done:** <br />
![synth4](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/f944ec4b-904a-45c4-8f3a-833a0753d9cb)
<br />

**The Figure below is the generated synthesized design:** <br />
![synth5_img](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/e036f7ba-aa4c-46ba-bfec-f26cdb14a426)
<br />

**The Screenshot below shows the 'write_verilog -noattr<'name of netlist'>' command and the <netlist>.v file:** <br />
![synth6_final](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/c0691b18-bae6-46ac-bd23-f03e20d01d6b)
  
</details>
<details>
    <summary>Other Relevant data</summary>
  <br />
  
  **RTL Design:** <br />
RTL stands for "Register Transfer Level," and in the context of digital hardware design, RTL design refers to the process of describing the behavior of a digital circuit 
or system using a hardware description language (HDL) at the register transfer level. It's a crucial step in designing complex digital systems such as microprocessors, 
application-specific integrated circuits (ASICs), field-programmable gate arrays (FPGAs), and more.
<br /><br />
In RTL design, the designer specifies the functionality and behavior of the digital system using a high-level hardware description language like Verilog or VHDL. This description focuses on the flow of data between registers and the operations that take place on that data.<br />

**Synthesis:** <br />
RTL design is the process of transforming a high-level functional description of a digital system into a gate-level netlist that can be physically implemented on 
hardware platforms. This process involves mapping the logic to standard cells, optimizing for performance, and ensuring timing requirements are met.
A Design is converted into gates and the connections are made between those gates, the final output file is what is termed as a netlist.<br /><br />

### What is .lib ?

1. .lib is a collection of various logical modules
2. It includes basic gates like and, or etc...
3. There are different flavours(versions) of the same gate
    - Slow
    - Medium
    - Fast

We need different flavors of gates because combinational delays in logical paths will determine the maximum speed of operation of digital logic circuits.<br />
<br />
### Why do we need different flavors of gates?

1. Different flavors of gates are necessary to provide a diverse toolkit for designing and implementing electronic circuits. They cater to various logical functions,
  optimization requirements, noise considerations, and implementation constraints, enabling the creation of complex and efficient systems.
2. Combinational delays in the logic path determine the max speed of operation of a digital logic circuit.

<br />

![dff_combi](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/01b72e99-69f9-4453-9e17-8f2a082de217)

- Based on the figure shown above, Tclk **Tcq_a**,**Tcombi**,**Tsetup_b** are the time period of the clock,propagation delay of A, Combinational delay, setup time of B 
  respectively.
- **Tclk > Tcq_a + Tcombi + Tsetup_b**
- one clock pulse should be long enough for the delay of the 'A'-D.FF,combinational delay and setup time for 'B'-D.FF to be incorporated.
- **Tsetup_b** is the time required for the the 'B'-D.FF data to be stable.

There is also a need for slow cells. The question of why we need them arises.<br />
- To ensure there are no 'HOLD' issues at B-D.FF, we need certain cells to work slowly
- We need cells that work fast to meet the required performance and we need cells that work slow to meet HOLD.

## Faster Cells Vs. Slower Cells:
- A load in digital logic is a capacitor
- A faster charging or discharging means less delay
- To increase the rate of charging or discharging we need to widen the transistors.
- Wider transistor gives lower delay: but more is required and more power is required
- Narrow transistors give out more delay  : we need less area and less power is consumed.


</details>

# Day 2
<details>
  <summary>Introduction</summary>
  In this section, we will briefly go about understanding a bit more about the .lib file and other stuff.
</details>
<details>
  <summary>Overview on .lib</summary>
  Firstly lets open the sky130_fd_sc_hd__tt_025C_1v80.lib using the Vim editer.<br />
 
  ```
  gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
  ```
The nomenclature of the above .lib file is :
1. sky - skywater
2. 130 - 130 nanometer(nm)
3. tt - typical  library
4. 025C - Temperature
5. 1v80 - Voltage
<br />

When we look into a library 'Process Voltage Temparature' is relevant for a design to work.<br />
1. Process is important because of variations in the fabrication.
2. Voltage is important because there will be variations in circuit behaviour due to the same.
3. Semiconductors are very dependent on temperature and we would need the design to work in a wide range of        geographies having different temperatures.

We need to factor in all these conditions when designing and so our libraries will also model these specifications.<br />

Below figure shows the the library sky130_fd_sc_hd__tt_025C_1v80.lib on Vim edior:<br />
![day1_1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/e2e76a6b-3316-45ee-9b08-71f0ba45e4e8)

The Below figure shows both the library sky130_fd_sc_hd__tt_025C_1v80.lib and the .v file sky130_fd_sc_hd.v which consists of the design of any given cell in the above-mentioned library:<br/>
![day1_2](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/cb52c2a2-9905-42a5-8c7d-1b8e9b9c0d05)

The Below side by side figure shows the details of different flavours of a 2 input and gate:<br />
Here it is seen that the area of all three are different.On Day 1 we discussed the effect of the area in efficiency and delay etc..<br />
![day1_3x](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/6d5738b1-5fa3-4a08-8103-c7ff45b55afe)

Below are some of the Vim commands used:<br />
```
:syn off "turn off highlighting
:se hls  "highlight cell
:se nu   "see line numbers
:g//     "see all the cells('highlighted ones')
:sp <directory>    "open a file with a directory along with 
:vsp     "opens the same file again side by side         

```
</details>
<details>
  <summary>Hierarchical Vs. Flat Synthesis</summary>
  
  ### Hierarchical Synthesis:
In hierarchical synthesis, the design of a complex digital circuit is divided into smaller, more manageable modules or blocks. Each module represents a functional unit or a specific sub-task the 
overall design. These modules are designed and optimized separately, and then they are integrated into the larger system. The design hierarchy can have multiple levels, with modules containing sub-
modules and so on.<br />

  ### Flat Synthesis:
  In flat synthesis, the entire digital circuit is synthesized as a single monolithic unit, without breaking it down into smaller modules. This approach is suitable for smaller designs where the 
  complexity doesn't warrant a hierarchical organization.<br />

  In this section, we will synthesize the same design in both Hierarchical and Flat to illustrate the difference in the netlist of both.<br />
  <br />
  **Hierarchical illustration**<br />
  (The Figure below shows the schematic diagram of a design named multiple_module.v:)<br />
![heir1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/602be1f3-2704-4d82-b754-688b467b89cb)
<br />
It is seen that everything is divided into smaller submodules.<br />

(The figure below is the netlist for the hierarchical design:)<br />
![heir_netlist](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/cd4d44e5-2681-4387-a000-87b4f1668e5f)
<br />
<br />
**Flat illustration**<br />
(The figure below shows the flattened-out netlist for the flattened design:)<br />
![flat](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/39b67082-8c56-4b3a-812c-03ef7bc66d34)
<br />
We write the 'flatten' command just before the write_verilog command to flatten the netlist.<br />
<br />
(The figure below shows the schematic diagram of the design).<br />
![flatten](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/ebb93a7c-9fee-40a7-b18a-637c54bdfc6f)
<br />
<br />

**Submodule Level Synthesis**<br />
Why is this done?
1. When we have multiple instantiations of the same module we prefer the submodule level by synthesis.
2. We might also want to use the divide and concur procedure, divide up the circuit to get the best possible design at the top level.

We need to make a small change in the synth command in yosys:

```
synth -top <sub_module_name>
```

<br />
(Illustrated below:)<br />

![submd1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/6ea4c027-ad4f-4a37-9fe8-bed3113761db)
<br />
(The design diagram for the same is shown below:)<br />

![sub1netlist](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/df1060dc-50eb-4943-8862-b787ace3629c)
  
  
</details>

<details>
  <summary>Various Flops and Flop coding styles</summary>
  <br />
  Here we are going to look at some questions such as the ones below:
  
  1. How to code a flop.
  2. What are the flops that are present
  3. What are the coding standards for it.
     
  #### Why do we need to use flops? <br />
  Consider the logic diagram given below consisting of an and gate and or gate.<br />
  there exists a propagation delay, and due to this the output glitches. This is a serious issue as the number of combinational circuits increases the number of glitches also increases.<br />
  
  ![logicdiagram](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/f20e2466-21d0-4a3a-974f-010eb8ef45d5)

  (In the figure below the glitch caused in the above logic diagram is illustrated in the blue shaded area:)<br />
  ![glitch](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/701d8ca3-badb-4587-8324-c110309eef6c)

  <br />
  Like mentioned above, more combinational circuits mean more glitches so to avoid glitches, we need to store the data, for that we use flops.<br />
  (The figure below illustrates the above problem and solution:)<br />
  
  ![combi](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/841dc701-aad2-4e15-82d9-d969d0ab10cc)
  <br />
  D-ff's give output only at the posedge of the clk. So, the next combinational circuit (block) will see only a stable input.

  ### How do I code the Flop?
  Below are the three different ways in which we can code the flop.
  1. Synchronous & Asynchronous reset
  2. Syncranous reset
  3. Asynchronous reset

  ![dffs](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/19af309b-8fa9-49bd-b0f4-4c235a07bc1c)

</details>
<details>
  <summary>Lab flop synthesis simulations</summary>
  <br />
  Here we are going to simulate D-Flip flops with Asynchronous reset & set, Synchronous, and Synchronous & Asynchronous reset with Iverilog and GTKwave.<br />

  ### Asynchronous reset:

  Here we are going to be using a .v file 'dff_asyncres.v' and its corresponding testbench. Run it on verilog and simulate it on GTKwave ash shown below.<br />
  ![d](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/72d36956-ffea-401c-ba45-2cb08adf5ce1)
  <br />
  Below we can see the output waveform of the design.<br />
  In this case, at around the 550ns range, we see that the output q follows the clk. i.e. q is synchronous with the clock.<br />
  ![d1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/81d9993f-d83b-48d0-a963-18b7afa9923c)
  <br />
  If we consider this point around the 1090ns-1100ns range. when the async_reset is high the output 'q' will immediately go low. This is called asynchronous reset. As illustrated below.<br />
  ![d2](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/a286d6dc-876b-4044-99bb-16ad429947be)

  ### Asynchronous set:
  <br />
  Here we do the same. The simulation output waveforms are shown below.<br />
  In the below waveform, in between the ranges of 500ns to 600 ns the async_set is low which makes the output looks for changes in 'd' upon the clock.<br />
  
  ![ds1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/46d2c9c8-fa56-40a7-9f5f-ef59a4265537)
  <br /><br />
  In the following waveform, when the async_set is high the output will be set high and will not follow  the 'd' input.<br />
  
  ![ds2](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/b203a94a-7fc0-4772-8787-d3b0afe513a4)
  
  ### Synchronous reset:
  <br />
  The steps for simulation are the same except here we use the dff_syncres.v file and its corresponding test bench.<br />
  In the below waveform, we can see between the 500ns-600ns range, when the sync_reset is high, the output follows the clock.<br /> As shown below:<br />
  
  ![db1](https://github.com/mrdunker/iiitb_emil_class/assets/38190245/aefed66f-eae9-498d-b0e5-57fa561f8fae)

  ### Synthesis of the above three designs:
  <br />
  
  
  
</details>

# References
1. https://yosyshq.net/yosys/
2. https://en.wikipedia.org/wiki/Icarus_Verilog
3. https://iverilog.fandom.com/wiki/GTKWave
4. http://ngspice.sourceforge.net/
5. https://github.com/The-OpenROAD-Project/OpenSTA
6. http://opencircuitdesign.com/magic/
7. https://github.com/The-OpenROAD-Project/OpenLane
8. https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop

