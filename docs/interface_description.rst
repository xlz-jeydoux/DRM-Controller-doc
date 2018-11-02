Interface description
=====================

The communication on the DRM Bus uses a private protocol where the IP Activator is a slave, the DRM Controller being the master. The DRM Bus I/F of the DRM Controller depends on the number of Protected IPs to be connected: one common part and one socket per Protected IP.


**DRM Bus Common Part**

Proprietary protocol

**DRM Bus Socket per IP**

Proprietary protocol

|

The communication with the System is done with an AXI4-Lite slave interface (Version: 2.0)

**AXI4-Lite I/F**


.. list-table::
   :header-rows: 1

   * - Name
     - Direction
     - Size
     - Description
   * - **SYS_AXI4_aCLK**
     - in
     - 1
     - AXI4 clock
   * - **SYS_AXI4_aRSTn**
     - in
     - 1
     - AXI4 asynchronous reset active low
   * - **SYS_AXI4_BUS_SLAVE_I_AW_VALID**
     - in
     - 1
     - AXI4 write address valid
   * - **SYS_AXI4_BUS_SLAVE_I_AW_ADDR**
     - in
     - 32
     - AXI4 write address value
   * - **SYS_AXI4_BUS_SLAVE_I_AW_PROT**
     - in
     - 3
     - AXI4 write address protection type
   * - **SYS_AXI4_BUS_SLAVE_O_AW_READY**
     - out
     - 1
     - AXI4 write address ready
   * - **SYS_AXI4_BUS_SLAVE_I_AR_VALID**
     - in
     - 1
     - AXI4 read address valid
   * - **SYS_AXI4_BUS_SLAVE_I_AR_ADDR**
     - in
     - 32
     - AXI4 read address value
   * - **SYS_AXI4_BUS_SLAVE_I_AR_PROT**
     - in
     - 3
     - AXI4 read address protection type
   * - **SYS_AXI4_BUS_SLAVE_O_AR_READY**
     - out
     - 1
     - AXI4 read address ready
   * - **SYS_AXI4_BUS_SLAVE_I_W_VALID**
     - in
     - 1
     - AXI4 write valid
   * - **SYS_AXI4_BUS_SLAVE_I_W_DATA**
     - in
     - 32
     - AXI4 write data value
   * - **SYS_AXI4_BUS_SLAVE_I_W_STRB**
     - in
     - 4
     - AXI4 write strobes
   * - **SYS_AXI4_BUS_SLAVE_O_W_READY**
     - out
     - 1
     - AXI4 write ready
   * - **SYS_AXI4_BUS_SLAVE_I_R_READY**
     - in
     - 1
     - AXI4 read ready
   * - **SYS_AXI4_BUS_SLAVE_O_R_VALID**
     - out
     - 1
     - AXI4 read valid
   * - **SYS_AXI4_BUS_SLAVE_O_R_DATA**
     - out
     - 32
     - AXI4 read data value
   * - **SYS_AXI4_BUS_SLAVE_O_R_RESP**
     - out
     - 2
     - AXI4 read response
   * - **SYS_AXI4_BUS_SLAVE_I_B_READY**
     - in
     - 1
     - AXI4 write response ready
   * - **SYS_AXI4_BUS_SLAVE_O_B_VALID**
     - out
     - 1
     - AXI4 write response valid
   * - **SYS_AXI4_BUS_SLAVE_O_B_RESP**
     - out
     - 2
     - AXI4 write response
     
     
**DNA Register I/F**

This interface is used only if user want access to limited Chip ID FPGA primitive. This latter is also used internally for the DRM Controller.

The DNA can be directly read with a simple register I/F synchronous with the DRM bus clock:

.. list-table::
   :header-rows: 1

   * - Name
     - Direction
     - Size
     - Description
   * - **CHIP_DNA**
     - out
     - 128
     - DNA value
   * - **CHIP_DNA_VALID**
     - out
     - 1
     - DNA value is valid

