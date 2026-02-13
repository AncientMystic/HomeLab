# HomeLab
HomeLab CheatSheet &amp; AwesomeList
<br> Created for the [HomeLab Group](https://smp6.simplex.im/g#P45YjyWy-__e3p3OqoRvU_4sjcSorUz0v8hCtWEPRtk) on Simplex Chat [![Simplex Chat](https://avatars.githubusercontent.com/u/59927747?s=48&v=4)](https://simplex.chat/)
<br>
<br> This page will be updated randomly with new information, contributions welcome!, so stay tuned. 
<br>
<br><b>Hardware:</b>
<details>
<summary>Recommended Devices</summary>
<details>
<summary>Minimal setups:</summary>
Optimal minimal setup device: 
  <br>Lenovo Tiny PC's 
  <p align="left">
  <img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/Lenovo-tiny-pc.jpg"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-thinkcentre-m715q-gen2-tiny-pc-amd-ryzen-5-2400ge.jpg"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-gpu.png"><img width="300" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-nvme.jpg">
</p>
  There are many hardware configuration options, some have intel cpus, some ryzen, some single nvme + sata 2.5in drives, some 2x nvme, some 2x nvme + pci-e slot, etc 
   <br>Popular Uses for the Pci-e slot:
  <ul><li>Nvidia Quadro P600/620 included with some models</li>
  <li>A Quad Port Nic (popular for router setups, such as Opnsense/Pfsense)</li>
  <li>Nvme Expansion Card for 2x additional Nvme drives making for 4xnvme on some models</li></ul>
  <br> Tiny PC's average as little as 5w power consuption depending on configuration and have Medium to Medium-high performance 35w TDP CPUs. 32GB to 128GB Ram support with 2 Slots (max ram depends on model), Mini Pci-e card slots for Wifi+bluetooth cards if desired and typically include 4-6 USB 3+ ports in newer models. these are basically the perfect AIO mini server for most any use cases. the intel versions iGPU can also be used with proxmox to share the iGPU to multiple virtual machines. They are small, powerful and perfect to plug a bunch of external hard drives into.
  <br> Other mini pc's and SFF Pcs can be worthwhile, but personally, i feel these are the most optimal cost effective options. 
  
  <details>
    <summary>SFF Suggestion:</summary>
    <br> One of the most cost effective SFF PCs for price vs hardware potential
    <br> HP z240 SFF
    <p align="left">
  <img width="300" src="https://i.pcmag.com/imagery/reviews/02pEw0PoQLzntoO4LnGl1jE-1.fit_lim.size_740x416.v_1569469958.jpg">
  <br> typically features an i7-6700 with 4x DDR4 ram slots and 64GB support. Plus it has 2x3.5 1x2.5 Hard drive slots and 2xPci-e slots, as far as expansion options go for a SFF PC this one has a lot of options.
  <br>
  <br> issues i have experinced: 
  <ul><li> takes some work to get 64GB ram to boot properly doesn't seem to like ram in the wrong order </li>
  <li> built in iGPU doesn't always work / default back to itself after having a dGPU, so if you buy it used how a low profile dGPU handy. upside the bios allows for iGPU+dGPU and will boot with a dGPU such as a tesla that includes zero display ports </li>
  <li> be careful with the 2.5in sata. if the cables aren't sitting quite right they can snap the data port off the drive, found that one out the hard way. there is a lot packed into very little space in this model so you have to be a bit mindful.</li></ul>  
</details>
</details>
<details>
<summary>Nic:</summary>
 <br> Intel I350: 
  <p align="left">
<img width="300" src="https://files.ekmcdn.com/itinstock/images/dell-intel-i350-t4-t34f4-quad-ports-1gbps-express-network-interface-card-1-89168-p.jpg?v=59DFCD45-8FDB-4D7E-BDFA-478F44C87A24">
    </p>
  <br> this device has support for SR-IOV and other worthwhile features for Virtual machines. if you do not need this, any other NIC should be fine. 
  <br> Be aware of knock offs, google “clone i350 intel” to learn how to spot them. Dell branded they are most likely genuine. <a href="https://forum.level1techs.com/t/compatible-quad-nic-for-dell-optiplex-7020-sff/170581/2" target="_blank">Discussion mentioning this</a>
</details>
<details>
<summary>GPU:</summary>
<details>
<summary>Nvidia:</summary>
<br> GTX 10 series to RTX 20 Series for vGPU. quadro and tesla also work, but teslas need licensing. 30-50 series  cunsomer cards will <b>NOT</b> work with vGPU Unlock. 
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
</details>
<details>
<summary>Intel vGPU Suggestion</summary>
Intel Arc Pro B50: 
<p align="left">
<img width="300" src="https://www.servethehome.com/wp-content/uploads/2025/05/Intel-Arc-Pro-B50-SFF-at-Computex-2025-2.jpg">
    </p>
this is one of the lowest priced GPUs with 16gb vram with virtual GPU profile support. each profile also appears as a new GPU you can passthrough to the Virtual machine. 
<br>Protential issues:
<ul><li>SR-IOV can require a bios update that must be done on windows, some users report success from linux but others report bricking their card when using linux.</li>
<li>QSV Encoding can be buggy. some users report that it does not function on the gpu profiles</li>
<li>Support for specifically intel IPEX/XPU is very limited compared to Nvidia or even AMD and vulkan/OpenCL performance is not great on ARC devices in my experience. (although i am only using a Arc A310 4GB currently) </li></ul>
</details>
</details>
</details>
<br>
<br><b>Suggested OS:</b>
<br><a href="https://www.proxmox.com/en/" target="_blank">Proxmox</a>
<details>
<summary>Proxmox related content:</summary>
<details><summary>Additional Resources:</summary>
<a href="https://community-scripts.github.io/ProxmoxVE/" target="_blank">Proxmox VE Helper scripts</a> 
<br><a href="https://github.com/MacRimi/ProxMenux" target="_blank">ProxMenux</a>
</details>
<details><summary>VMs:</summary>
<a href="https://github.com/kholia/OSX-KVM" target="_blank">OSX-KVM</a>
</details>
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
