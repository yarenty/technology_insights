Just installed Vitis on linux mint.

If you plan to install Vitis on any ubuntu based linux, make sure to install libtinfo5 before starting the installer. https://support.xilinx.com/s/article/76616?language=en_US

I recommend to mount your /tools directory (or any other installation target) on a dedicated partition. This way, you can disable file system journaling in the hope of speeding up the installation process. Mine took 8 hrs on a SSD drive using ReiserFS with yournaling enabled.

It is also recommended to uncheck all components and parts you don't use, especially if you use an accelerator card, i.e. VCK5000, C1100 (--> no peta linux). The KV260 runs an embedded processor booting linux --> peta linux needed.

Only install Vitis (the uppermost radio button). Vivado comes with this.


