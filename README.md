This fork modifies the original build process. 
<br>
Please use the following commands to compile the Zink(Make sure to execute it in the Ubuntu 18.04 environment):​
<br>
apt update && apt -y install python3 python3-pip python3-mako libzstd-dev cmake zlib1g-dev zlib1g bison flex pkg-config libx11-dev libxext-dev libxcb1-dev libxcb-randr0-dev libxrandr-dev libnm-dev libdrm-dev libdrm2 git ninja-build
<br>
pip3 install meson
<br>
git clone https://github.com/ocnedkf/mesa-zink-11.06.22
<br>
cd mesa-zink-11.06.22
<br>
meson . build -Dgallium-va=false -Ddri-drivers= -Dgallium-drivers=zink -Ddri3=false -Dvulkan-drivers= -Dglx=xlib -Dplatforms=x11 -Dbuildtype=release -Dllvm=disabled -Dlibunwind=disabled -Dzstd=true -Degl=disabled --prefix=/usr
<br>
ninja -C build -j$(nproc) install
