# WindowsDeployment
Automatically deploy Windows OS

## Reference

[基于WDS+MDT全自动部署WIN系统](https://www.sohu.com/a/198024963_733939)

[WDS为引导映像添加额外的网卡驱动支持](https://goxia.maytide.net/read.php/1422.htm)

## USB3.0问题
HCI (Host Controller Interface) 即主机控制接口。HCI是寄存器层级的界面接口，它允许一个主控制器（Host Controller 如 主板南桥southbridge of Motherboard）来实现与外设如（USB、火线以及蓝牙）之间的通讯。当外设与PC相连接后，系统先进行初始化，HCI开始线程（threads）读写，建立与外设的连接。接下来，HCI会重置然后读外设的缓存大小，建立与外设的通讯。而EHCI (Enhanced Host Controller Interface)是HCI增强的（Enhanced）版本。

EHCI英文全称为Enhanced Host Controller Interface，是增强型主机控制器接口规范，描述了一个通用串行总线USB2.0版的主机控制器的寄存器级接口。EHCI规范包括系统软件和主机控制器硬件之间的硬件/软件接口的描述，主要是为硬件组件设计，系统集成商和设备驱动程序（软件）开发。

简单来说，EHCI就是通常所说的USB2.0接口,如果你的电脑支持USB2.0的话,那么你使用的USB设备都是接在他上面的.

XHCI英文全称eXtensible Host Controller Interface，是一种可扩展的主机控制器接口，是Intel开发的USB主机控制器。Intel心意哎100系列芯片的USB协议采用的就是XHCI主控，主要面向USB 3.0标准的，同时也兼容2.0以下的设备。

简单来说，XHCI是Intel最新开发的主机控制器接口，广泛用户Intel六代Skylake处理器对应的100系列主板上，支持USB3.0接口，往下也兼容USB2.0。

EHCI和XHCI都属于主机控制器接口，前者针对的是USB2.0接口，而后者则根据最新的USB3.0开发，往下也兼容USB2.0，简单来说，XHCI是EHCI的增强版。

值得一提的是，由于Win7原生系统没有带有XHCI驱动，因此100系列主板安装Win7系统会出现USB鼠标键盘失效的情况，而Win8和Win10原生系统由于内置了XHCI驱动，因此不会出现这种情况。
