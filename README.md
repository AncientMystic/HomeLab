# HomeLab
HomeLab CheatSheet &amp; AwesomeList
<br> Created for the [HomeLab Group](https://smp6.simplex.im/g#P45YjyWy-__e3p3OqoRvU_4sjcSorUz0v8hCtWEPRtk) on Simplex Chat [![Simplex Chat](https://avatars.githubusercontent.com/u/59927747?s=48&v=4)](https://simplex.chat/)
<br>
<br> This page will be updated randomly with new information, contributions welcome!, so stay tuned. 
<br>
## Table of Contents
- [Hardware](#hardware)
  - [Recommended Devices](#recommended-devices)
    - [Minimal Setups](#minimal-setups)
    - [SFF Suggestions](#sff-suggestions)
  - [NIC](#nic)
  - [GPU](#gpu)
- [Suggested OS](#suggested-os)
  - [Proxmox](#proxmox)
  - [Filesystems](#filesystems)
- [Software](#software)
  - [RDP](#rdp)
  - [Gaming](#gaming)
  - [File Management](#file-management)
<br>
<br><b>Hardware:</b>
<br>Recommended Devices:
<br>Optimal minimal setup device: Lenovo Tiny PC's 
  <p align="left">
  <img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/Lenovo-tiny-pc.jpg"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-thinkcentre-m715q-gen2-tiny-pc-amd-ryzen-5-2400ge.jpg"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-gpu.png"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-nvme.jpg">
</p>
  There are many hardware configuration options, some have intel cpus, some ryzen, some single nvme + sata 2.5in drives, some 2x nvme, some 2x nvme + pci-e slot, etc 
   <br>Popular Uses for the Pci-e slot:
  <ul><li>Nvidia Quadro P600/P620/T400 included with some models</li>
  <li>A Quad Port Nic (popular for router setups, such as Opnsense/Pfsense)</li>
  <li>Nvme Expansion Card for 2x additional Nvme drives making for 4xnvme on some models</li></ul>
  <br> Tiny PC's average as little as 5w power consumption depending on configuration and have Medium to Medium-high performance 35w TDP CPUs. 32GB to 128GB Ram support with 2 Slots (max ram depends on model), Mini Pci-e card slots for Wifi+bluetooth cards if desired and typically include 4-6 USB 3+ ports in newer models. these are basically the perfect AIO mini server for most any use cases. the intel versions iGPU can also be used with proxmox to share the iGPU to multiple virtual machines. They are small, powerful and perfect to plug a bunch of external hard drives into.
  <br> Other mini pc's and SFF Pcs can be worthwhile, but personally, i feel these are the most optimal cost effective options. 
  <table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Model</th>
      <th>CPU</th>
      <th>RAM Max</th>
      <th>Drives/NVMe Slots</th>
      <th>PCIe Slot</th>
      <th>iGPU</th>
      <th>Power (TDP)</th>
      <th>Best Use Case</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ThinkCentre M715q Gen2</td>
      <td>Ryzen 5 2400GE</td>
      <td>32GB</td>
      <td>1x 2.5"/1xM.2</td>
      <td>No </td>
      <td>Vega 11</td>
      <td>~35W</td>
      <td>Nas server, media server, Proxmox host</td>
    </tr>
    <tr>
      <td>ThinkCentre M720Q</td>
      <td>I5-8400T/i7 8700T</td>
      <td>32GB</td>
      <td>1x 2.5"/1xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 630</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
    <tr>
      <td>ThinkCentre M920q</td>
      <td>I5-8400T/i7 8700T</td>
      <td>32GB</td>
      <td>1x 2.5"/1xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 630</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
    <tr>
      <td><a href="https://www.hacktiny.com/wp-content/uploads/2019/09/M920x-Tiny.pdf" target="_blank">ThinkCentre M920x</a></td>
      <td>up to I5-9400T/i7-9700T</td>
      <td>32GB</td>
      <td>2xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 630</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
    <tr>
      <td><a href="https://thinkstation-specs.com/wp-content/uploads/2019/09/P330-Tiny-Lenovo-ThinkStation.pdf" target="_blank">ThinkCentre P330</a></td>
      <td>up to I5-9400T/i7-9700T</td>
      <td>64GB</td>
      <td>2xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 630</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
      <tr>
      <td><a href="https://www.lenovo.com/content/dam/lenovo/pcsd/north-america/en/solutions/workstations/datasheets/na-datasheet-thinkstation-p340-tiny.pdf" target="_blank">ThinkCentre P340</a></td>
      <td>up to I5-9400T/i7-9700T</td>
      <td>64GB</td>
      <td>2xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 630</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
    <tr>
      <td><a href="https://news.lenovo.com/wp-content/uploads/2021/07/ThinkStationP350TinyDatasheet-Final.pdf" target="_blank">ThinkCentre P350</a></td>
      <td>i7-11700T</td>
      <td>64GB</td>
      <td>2xM.2</td>
      <td>1x PCIe</td>
      <td>Intel UHD 750</td>
      <td>~35W</td>
      <td>NAS, Network appliance, media server, Proxmox host</td>
    </tr>
  </tbody>
</table>	
  <details>
    <summary>SFF Suggestion:</summary>
    <br> One of the most cost effective SFF PCs for price vs hardware potential
    <br> HP z240 SFF
    <p align="left">
  <img width="300" src="https://i.pcmag.com/imagery/reviews/02pEw0PoQLzntoO4LnGl1jE-1.fit_lim.size_740x416.v_1569469958.jpg">
  <br> typically features an i7-6700 with 4x DDR4 ram slots and 64GB support. Plus it has 2x3.5 1x2.5 Hard drive slots, 1xNVME m.2 slot and 2xPci-e slots, as far as expansion options go for a SFF PC this one has a lot of options.
  <br>
  <br> issues i have experienced: 
  <ul><li> takes some work to get 64GB ram to boot properly doesn't seem to like ram in the wrong order </li>
  <li> built in iGPU doesn't always work / default back to itself after having a dGPU, so if you buy it used how a low profile dGPU handy. upside the bios allows for iGPU+dGPU and will boot with a dGPU such as a tesla that includes zero display ports </li>
  <li> be careful with the 2.5in sata. if the cables aren't sitting quite right they can snap the data port off the drive, found that one out the hard way. there is a lot packed into very little space in this model so you have to be a bit mindful.</li></ul>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Model</th>
      <th>CPU</th>
      <th>RAM Max</th>
      <th>Drives/NVMe Slots</th>
      <th>PCIe Slot</th>
      <th>iGPU</th>
      <th>Power (TDP)</th>
      <th>Best Use Case</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://www.pcmag.com/reviews/hp-z240-sff-workstation?test_uuid=04IpBmWGZleS0I0J3epvMrC&test_variant=A" target="_blank">HP z240 SFF</a></td>
      <td>i7-6700</td>
      <td>64GB</td>
      <td>1x 2.5” + 2x 3.5” + 1xM.2</td>
      <td>2x PCIe x16</td>
      <td>Intel HD 530</td>
      <td>~65W</td>
      <td>Proxmox host, AI/ML, multi-GPU dev</td>
    </tr>
  </tbody>
</table>	
</details>
<details>
<summary>Nic:</summary>
 <br> <a href="https://www.digikey.com/htmldatasheets/production/2068431/0/0/1/intel-ethernet-server-adapter-i350-brief.html" target="_blank">Intel I350:</a> 
  <p align="left">
<img width="300" src="https://files.ekmcdn.com/itinstock/images/dell-intel-i350-t4-t34f4-quad-ports-1gbps-express-network-interface-card-1-89168-p.jpg?v=59DFCD45-8FDB-4D7E-BDFA-478F44C87A24">
    </p>
  <br> this device has support for SR-IOV and other worthwhile features for Virtual machines. if you do not need this, any other NIC should be fine. 
  <br> Be aware of knock offs, google “clone i350 intel” to learn how to spot them. Dell branded they are most likely genuine. <a href="https://forum.level1techs.com/t/compatible-quad-nic-for-dell-optiplex-7020-sff/170581/2" target="_blank">Discussion mentioning this</a>
</details>
<details>
<summary>GPU:</summary>
<br><b>Nvidia:</b>
<br> GTX 10 series to RTX 20 Series for vGPU. quadro and tesla also work, but teslas need licensing. 30-50 series consumer cards will <b>NOT</b> work with vGPU Unlock. 
<br> 20 series would be best, pascal is not great for AI, etc but if that isn't a worry pascal is also great. 
<br> i personally use a Tesla P4 8GB, the licensing server and all is kind of annoying but it works quite well aside from the added hassle around configuration.
<br> in my opinion the tesla P4, T4, L4 models are the most optimal devices at 60-75w power usage with speeds comparable to higher end cards, example the P4 is an underclocked GTX 1080, which has a TDP 105w higher (180w) <a href="https://askgeek.io/en/gpus/vs/NVIDIA_Tesla-P4-vs-NVIDIA_GeForce-GTX-1080-Desktop" target="_blank">Tesla P4 Vs GTX 1080 benchmarks</a>
<br> i have used the P4 to run games @ 1080p in multiple VMs simultaneously. (specifically GTA V in 2 VMs at once.) 
<details>
<summary>Nvidia vGPU resources</summary>
<a href="https://gitlab.com/polloloco/vgpu-proxmox" target="_blank">NVIDIA vGPU Guide</a> 
<br><a href="https://alist.homelabproject.cc/foxipan/vGPU)" target="_blank">Drivers</a> 
<br> licensing related:
<br><a href="https://git.collinwebdesigns.de/vgpu/gridd-unlock-patcher" target="_blank">gridd-unlock-patcher aka guest driver patch for versions after 18</a> 
<br><a href="https://git.collinwebdesigns.de/oscar.krause/fastapi-dls" target="_blank">FastAPI-DLS aka the licensing server.</a> 
<br><a href="https://github.com/GreenDamTan/vgpu_unlock-rs" target="_blank">vgpu_unlock-rs mirror by GreenDamTan</a> 
<br><a href="https://github.com/GreenDamTan/fastapi-dls_mirror" target="_blank">fastapi-dls_mirror by GreenDamTan</a>
</details>
<br><b>Intel:</b>
<br>only the Arc Pro and iGPUs support SR-IOV standard Arc GPUs do <b>NOT</b> support SR-IOV
<br>Intel Arc Pro B50: 
<p align="left">
<img width="300" src="https://www.servethehome.com/wp-content/uploads/2025/05/Intel-Arc-Pro-B50-SFF-at-Computex-2025-2.jpg">
    </p>
this is one of the lowest priced GPUs with 16gb vram with virtual GPU profile support. each profile also appears as a new GPU you can passthrough to the Virtual machine. 
<br>Protential issues:
<ul><li>SR-IOV can require a bios update that must be done on windows, some users report success from linux but others report bricking their card when using linux.</li>
<li>QSV Encoding can be buggy. some users report that it does not function on the gpu profiles</li>
<li>Support for specifically intel IPEX/XPU is very limited compared to Nvidia or even AMD and vulkan/OpenCL performance is not great on ARC devices in my experience. (although i am only using a Arc A310 4GB currently) </li></ul>
<br>
<br><b>AMD:</b>
<br> Much like intel, <b>ONLY</b> the professional series supports SR-IOV. if anyone can contribute any information on the AMD vGPU setups, it would be appreciated.
</details>
</details>
<br>
<br><b>Suggested OS:</b>
<br><a href="https://www.proxmox.com/en/" target="_blank">Proxmox</a>
<details>
<summary>Proxmox related content:</summary>
Additional Resources:
<br><a href="https://community-scripts.github.io/ProxmoxVE/" target="_blank">Proxmox VE Helper scripts</a> 
<br><a href="https://github.com/MacRimi/ProxMenux" target="_blank">ProxMenux</a>
<br>VMs:
<br><a href="https://github.com/kholia/OSX-KVM" target="_blank">OSX-KVM</a>
</details>
<details>
<summary>Filesystems:</summary>
<a href="https://blog.purestorage.com/purely-educational/xfs-vs-ext4-which-linux-file-system-is-better/" target="_blank">xfs-vs-ext4-which-linux-file-system-is-better</a>
<br> Beyond what they cover in the short article,
<br> In general XFS is more reliable for data in my experience, i have lost files to long term storage on EXT4. So media files, etc, for long term storage, XFS.
<br> When it comes to operating system disks, like for a laptop, etc. EXT4. But EXT4 also has a space reservation so you lose a chunk of your disk automatically (typically 5%) and the larger the disk <br> the more space is in that 5% which you have automatically lost.
<br> So XFS you can also fill with more files as it does not reserve space.
<br> XFS does not seem to nest/stack as well, so using a Vm with an XFS virtual disk on top of an XFS drive is terrible, avoid stacking them like that. (Use ext4 on top of XFS if you stack them
<br> Now comes the secret third thing nobody talked about:
<br> <b>ZFS:</b>
<br> <a href="https://itsfoss.com/what-is-zfs/" target="_blank">what-is-zfs</a>
<br><b>ZFS the Zettabyte file system</b>
<ul><li> Supports compression: 1z4, gzip, zstd, etc </li>
<li> Supports deduplication. (Requires a ton of memory and raid to get the most out of it)</li>
<li> Hashes files and in raid is self healing</li>
<li> CoW (copy on write) Verification, files are verified before being written to disk and verified whenever they are read based on a wide variety of checksum options / hash algorithms</li>
<li> Scales incredibly well</li>
<li> Supports RAW filesystems, I.e. a VM disk can be written directly into the filesystem kind of like a container instead of a virtual disk file layered on top as file.</li>
<li> Can copy live virtual machines.</li>
<li> Superior performance potential</li>
<li> Complex options for advanced and highly specific configurations</li></ul>
<br><b>ZFS</b> is great all around and extremely reliable, it is best in a raid environment with minimum 2+ disks, but if speed is not a concern and you merely want to take advantage of all the wonderful features it will work fine on a single disk, just expect it to be slow at times and use a lot of ram and has a fairly steep learning curve. (There is a LOT to cover and it is not simple as a normal filesystem is as it is made for datacenters)
<br>An alternative to ZFS for hash and ZSTD compression support is <b>BTRFS</b>
<br><a href="https://www.maketecheasier.com/what-is-btrfs/" target="_blank">what-is-btrfs</a>
<br>BTRFS can be better in some use cases but should not be considered reliable like ZFS. (Although its much easier to get the hang of and use)
<br>For example a large number of small file writes can crash the filesystem resulting in total loss of data. (Databases, torrents, VMs, etc) as it is also a copy on write system but is not as well made as ZFS.
<br>But for some uses it works quite well, in testing for example i ran a ubuntu VM with the filesystem and compressed the roughly 5.5gb of OS files to 2.8GB with ZSTD level 9 specified in FSTAB ( configuration file to mount disks in linux located at /etc/fstab)
<br>With ZSTD you want to use at least a 3 otherwise you're just wasting resources to use it for nothing and at most
9-11 otherwise the additional compression time goes up exponentially for minimal benefits, 5-7 is usually a safe middle ground option. That balances performance and compression ratio
You can utilise all of these on proxmox if you are interested in a homelab virtualization server.
</details>
<br>
<br><b>Software:</b>
<details>
<summary><b>RDP:</b></summary>
<a href="https://github.com/ClassicOldSong/Apollo" target="_blank">Apollo Sunshine fork</a>
<br><a href="https://github.com/LizardByte/Sunshine" target="_blank">Original Sunshine</a>
<br><a href="https://github.com/moonlight-stream" target="_blank">Moonlight</a>
<br><a href="https://github.com/Upinel/BetterRDP" target="_blank">BetterRDP for windows to enable 60fps and GPU acceleration on RDP connections</a>  
</details>
<details>
<summary><b>Gaming:</b></summary>
<a href="https://github.com/microsoft/RdpGamepad" target="_blank">RdpGamepad - a Remote Desktop Plugin for Xbox Gamepads</a>
</details>
<details>
<summary><b>File management:</b></summary>
<a href="https://github.com/evsar3/sshfs-win-manager" target="_blank">SSHFS-Win Manager is a GUI for SSHFS on Windows</a>
</details>
<Br><b>SelfHosted:</b>
<br><a href="https://github.com/awesome-selfhosted/awesome-selfhosted" target="_blank">Awesome-Selfhosted</a>

