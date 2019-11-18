### MyROCm
This repo provide MyROCm binary build and installation guide.

#### Why MyROCm
Official rocm release lack the support for new hardware like Navi.

#### Dependancy
MyROCm running on  ubuntu 19.10 + ( linux kernel 5.3+ ).

#### Installation guide.

 * Prepare your ubuntu 19.10 environment.

Hint:  ubuntu 19.10 ship with kernel 5.3+ but missing navi firmware. it can be download from https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/amdgpu   and put into  /lib/firmware/amdgpu. 

 * Download MyROCm from:

https://github.com/smartbitcoin/MyROCm/releases/download/2.9_navi10/myrocm.2.9.tar.bz2

cd /opt

tar xvf myrocm.2.9.tar.bz2

 * Config ROCm library path.
 
 sudo touch /etc/ld.so.conf.d/rocm.conf
 
 and put following two line into rocm.conf
 
 /opt/rocm/lib
 
 /opt/rocm/hsa/lib
 
  * Try it out.
  
  check your navi was found:
  
  /opt/rocm/bin/rocminfo
  ![](docs/rocminfo.png)
   
  /opt/rocm/bin/hipInfo
  ![](docs/hipinfo.png)
  
  test the hip sample
  
  /opt/rocm/hip/samples/0_Intro/bit_extract
  
  make
  
  ./bit_extract
  
  
  
  