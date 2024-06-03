# vmulti
Virtual Multiple HID Driver (multitouch, mouse, digitizer, keyboard, joystick) 

### Prerequisites

    Windows Driver Kit 7.1.0 (https://www.microsoft.com/whdc/devtools/wdk/wdkpkg.mspx) 

### Building

    Start a WDK build environment
    Navigate to the location of your vmulti source root directory (eg. C:\projects\vmulti)
    Build the drivers and test program using build -wgc 

### Installing

Note: This will not work on 64-bit systems without first properly signing the driver

    Gather together the vmulti.sys/vmulti.inf/hidkmdf.sys files into single directory
    Also copy the file WdfCoInstaller01009.dll (from the WDK) to your installation directory
    Also copy the file devcon.exe (from the WDK) to your installation directory
    Run the command: devcon install vmulti.inf djpnewton\vmulti 

### Testing

    Run testvmulti.exe /multitouch to move the cursor via virtual multitouch (only available on Win7 and above)
    Run testvmulti.exe /mouse to move the cursor via virtual mouse
    Run testvmulti.exe /digitizer to move the cursor via virtual digitizer 

错误提示内容：
这个设备运转正常。Windows 无法识别与该硬件连接的一个次要设备，原因使该设备没有有效的硬件标识号。请与硬件制造商联系取得协助。

解决方法
原项目没有硬件标识号的节，你可以去看看 微软官方的这份文档 https://learn.microsoft.com/zh-cn/windows-hardware/drivers/install/hardware-ids 然后添加上去
