XRT Debug/Profile

-------------------------------------------------------------------------------

The XRT Debug/Profile libraries are designed to be built and used in
conjunction with XRT and not as a standalone tool.  This set of loadable
modules implement debug/profiling functionality on host code, PL constructs,
and AIE components.

User controls are through the xrt.ini file.  Support exists for both PCIe
based platforms and embedded platforms.

-------------------------------------------------------------------------------

XRT, and subsequently XDP, is run on a variety of platforms with varying
hardware and capabilities.  Specifically, XDP supports the following:

1. Edge Hardware (boards like the vck190 and vek280).
1a. Host code on edge using load_xclbin.
1b. Host code on edge using hw_context.
1c. Supported features include host trace, PL profiling and trace, AIE profiling and trace, AIE status, PL deadlock detection.

2. Edge Hardware Emulation (QEMU + XSim for vck190 and vek280)
2a. Host code on edge emulation using load_xclbin.
2b. Host code on edge emulation using hw_context.
2c. Supported features include host trace, PL profiling and trace, AIE profiling and trace

3. Alveo Hardware (boards like the u250 and u55c)
3a. Host code on Alveo using load_xclbin.
3b. Supported features include host trace, PL profiling and trace

4. Alveo Hardware Emulation
4a. Host code on Alveo using load_xclbin.
4b. Supported features include host trace, PL profiling and trace

5. Client hardware - Windows
5a. Host code written for VAIML designs using hw_contexts.  Communication with
    the hardware must pass along hardware context IDs and use tranasactions
    (or elf) to configure the AIE
5b. Supported features include host trace, user events, AIE profiling and trace,
    and ML timeline.

6. Client hardware - Linux
6a. Host code written for VAIML designs using hw_contexts.  Communication with
    the hardware must pass along hardware context IDs and use tranasactions
    (or elf) to configure the AIE
6b. Supported features include host trace, user events, AIE profiling and trace,
    and ML timeline.

7. VE2 (Vitis)
7a. Host code written for Vitis designs using load_xclbin
7b. Host code written for Vitis designs using hw_context.
7c. Supported features include host trace, user events, AIE profiling and trace.
    All control of the AIE hardware is done through direct calls to aie driver
    and zocl.

8. VE2 (VAIML)
8a. Host code written for VAIML designs using hw_context.
8b. Supported features include host trace, user events, AIE profiling and trace.
    All control of the AIE hardware is done through direct calls to aie driver
    and zocl.

Plugins:

aie_base : No feature
aie_debug : No feature
aie_halt : Internal, used with ML Debugger on Client
aie_pc : No feature
aie_profile : Used on Client, Edge, Alveo, hardware emulation
aie_status : Used on Edge, Alveo, hardware emulation
aie_trace : Used on Client, Edge, Alveo, hardware emulation
device_offload : PL trace and counters, used on Edge, Alveo, and hardware emulation
hal : host trace used on Edge and Alveo, hardware emualation
hal_api_interface : Called from user host code to read PL device counters.  Available on Edge and Alveo
lop : Low-overhead OpenCL trace of host code.  Available on Edge, Alveo, hardware emulation
ml_timeline : Available on Client and VE2 (VAIML)
native : host trace used on Edge, Alveo, and Client, hardware emulation
noc : No feature
opencl : OpenCL trace of host code.  Available on Edge, Alveo, hardware emulation
pl_deadlock: Detect and interpret PL deadlock.  Available on Edge, Alveo
power: Available on Alveo
system_compiler : No feature
user : Called from user host code.  Available on Edge, Alveo, Client, hardware emulation.
vart : No feature
vp_base : No feature