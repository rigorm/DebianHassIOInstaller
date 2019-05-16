## HassIO Installer on a Debian based VM image
Virtual machine(VM) image based on Debian 9.9 including hassio installer

### Specs:
<ul>
  <li>Based on Debian 9.9</li>
<li>image format in raw</li>
<li>Uncompressed size is 1.5GB</li>
<li>upon booting, the main partition will resize it self to the total space allows (if using LVM)</li>
</ul>  

### Instructions:
  1. Uncompress file
  ``` bash
  gzip -dkcv filename.img.gz > filename.img
  ```
  2. If using LVM, inject the file directly into a newly made Logical Volume(LV)
  ``` bash
  dd if=filename.img of=/dev/VGname/LVname bs=4096
  ```
  3. Of if you're using the image file directly then consider adding space as the installer will not have enough space to install everything
  ```bash
  truncate filename.img +6G
  ```
  4. Use the image with your favorite flavor that supports **KVM**
  
