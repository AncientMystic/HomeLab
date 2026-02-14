# HomeLab
HomeLab CheatSheet &amp; AwesomeList
<br> Created for the [HomeLab Group](https://smp6.simplex.im/g#P45YjyWy-__e3p3OqoRvU_4sjcSorUz0v8hCtWEPRtk) on Simplex Chat [![Simplex Chat](https://avatars.githubusercontent.com/u/59927747?s=48&v=4)](https://simplex.chat/)
<br>
<br> This page will be updated randomly with new information, contributions welcome!, so stay tuned. 
<br> Note: many of the hardware suggestions here are mostly the best items in their class for the lowest prices.
<br>
## Table of Contents

- [Hardware](#hardware)
  - [Recommended Devices](#recommended-devices)
    - [Minimal / Tiny PCs](#recommended-devices)
    - [SFF Suggestions](#sff-suggestion)
  - [NIC (Network Cards)](#nic)
  - [SAS / HBA Cards](#sas--hba-cards)
    - [LSI 9211-8i (IT Mode)](#sas--hba-cards)
    - [Newer Recommended Alternatives (SAS2308 / SAS3008)](#sas--hba-cards)
  - [GPU](#gpu)
    - [NVIDIA (vGPU / AI / Virtualization)](#gpu)
      - Supported Generations
      - Tesla Low-Power Options
      - vGPU Licensing Notes
      - vGPU Resources
    - [Intel (SR-IOV / Arc Pro)](#gpu)
      - Arc Pro B-Series
      - Firmware / Early Adopter Notes
    - [AMD (MxGPU / SR-IOV)](#gpu)
      - Supported Professional Series
      - MxGPU Overview
      - Contribution Request
    - [GPU Model Comparison Table](#gpu-models-to-compare-them-side-by-side)

- [Suggested OS](#suggested-os)
  - [Proxmox](#proxmox)
  - [Filesystems](#filesystems)

- [Software](#software)
  - [RDP](#rdp)
  - [Gaming](#gaming)
  - [File Management](#file-management)
  - [Caching](#caching)
  - [Firewall / Networking](#firewallnetworking)
  - [Host Power Management](#host-power-management)
<br>
<br><b>Hardware:</b>
<br>Recommended Devices:
<br>Optimal minimal setup device: Lenovo Tiny PC's 
  <p align="left">
  <img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/Lenovo-tiny-pc.jpg"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-thinkcentre-m715q-gen2-tiny-pc-amd-ryzen-5-2400ge.jpg"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-gpu.png"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-nvme.jpg">
</p>
  There are many hardware configuration options, some have intel cpus, some ryzen, some single nvme + sata 2.5in drives, some 2x nvme, some 2x nvme + pci-e slot, etc 
   <br>Popular Uses for the Pci-e slot:
  <ul><li>Nvidia Quadro P600/P620/P1000/T400/T600 included with some models</li>
  <li>A Quad Port Nic (popular for router setups, such as Opnsense/Pfsense)</li>
  <li>Nvme Expansion Card for 2x additional Nvme drives making for 4xnvme on some models</li></ul>
  <br> Tiny PC's average as little as 5-7w idle power consumption depending on configuration and have Medium to Medium-high performance 35w TDP CPUs. 32GB to 128GB Ram support with 2 Slots (max ram depends on model), Mini Pci-e card slots for Wifi+bluetooth cards if desired and typically include 4-6 USB 3+ ports in newer models. these are basically the perfect AIO mini server for most any use cases. the intel versions iGPU can also be used with proxmox to share the iGPU to multiple virtual machines. They are small, powerful and perfect to plug a bunch of external hard drives into.
  <br> Other mini pc's and SFF Pcs can be worthwhile, but personally, i feel these are the most optimal cost effective options. 
<table border="1" class="dataframe">
<thead>
<tr>
<th>Model</th>
<th>CPU</th>
<th>Cores / Threads</th>
<th>Passmark CPU Bench</th>
<th>RAM Max</th>
<th>Drives / NVMe Slots</th>
<th>PCIe Slot</th>
<th>iGPU</th>
<th>Quick Sync</th>
<th>Idle Power*</th>
<th>Power (TDP)</th>
<th>Year</th>
<th>Best Use Case</th>
</tr>
</thead>
<tbody>

<tr>
<td>ThinkCentre M715q Gen2</td>
<td>
<a href="https://www.hacktiny.com/wp-content/uploads/2019/09/M920x-Tiny.pdf" target="_blank">Ryzen 5 2400GE</a>
</td>
<td>4C / 8T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=AMD+Ryzen+5+2400GE" target="_blank">7192</a>
</td>
<td>32GB</td>
<td>1x 2.5" / 1x M.2</td>
<td>None</td>
<td>Vega 11</td>
<td>N/A</td>
<td>~7–10W</td>
<td>35W</td>
<td>2018</td>
<td>Budget NAS, light Proxmox</td>
</tr>

<tr>
<td>ThinkCentre M720Q</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/129940/intel-core-i58400t-processor-9m-cache-up-to-3-30-ghz/specifications.html" target="_blank">i5-8400T</a> /
<a href="https://www.intel.com/content/www/us/en/products/sku/129948/intel-core-i78700t-processor-12m-cache-up-to-4-00-ghz/specifications.html" target="_blank">i7-8700T</a>
</td>
<td>6C / 6T – 6C / 12T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-8400T+%40+1.70GHz" target="_blank">7419</a> /
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-8700T+%40+2.40GHz" target="_blank">10225</a>
</td>
<td>32GB</td>
<td>1x 2.5" / 1x M.2</td>
<td>1x PCIe 3.0 x8 (riser)</td>
<td>Intel UHD 630</td>
<td>Gen9.5</td>
<td>~8–12W</td>
<td>35W</td>
<td>2018</td>
<td>NAS, Network appliance, media server, Proxmox host</td>
</tr>

<tr>
<td>ThinkCentre M920q</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/129940/intel-core-i58400t-processor-9m-cache-up-to-3-30-ghz/specifications.html" target="_blank">i5-8400T</a> /
<a href="https://www.intel.com/content/www/us/en/products/sku/129948/intel-core-i78700t-processor-12m-cache-up-to-4-00-ghz/specifications.html" target="_blank">i7-8700T</a>
</td>
<td>6C / 6T – 6C / 12T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-8400T+%40+1.70GHz" target="_blank">7419</a> /
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-8700T+%40+2.40GHz" target="_blank">10225</a>
</td>
<td>32GB</td>
<td>1x 2.5" / 1x M.2</td>
<td>1x PCIe 3.0 x8 (riser)</td>
<td>Intel UHD 630</td>
<td>Gen9.5</td>
<td>~8–12W</td>
<td>35W</td>
<td>2018</td>
<td>Same as M720Q + vPro enterprise features</td>
</tr>

<tr>
<td>
<a href="https://www.hacktiny.com/wp-content/uploads/2019/09/M920x-Tiny.pdf" target="_blank">ThinkCentre M920x</a>
</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html" target="_blank">i5-9400T</a> /
<a href="https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html" target="_blank">i7-9700T</a>
</td>
<td>6C / 6T – 8C / 8T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz" target="_blank">8148</a> /
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz" target="_blank">10553</a>
</td>
<td>32GB</td>
<td>2x M.2</td>
<td>1x PCIe 3.0 x8</td>
<td>Intel UHD 630</td>
<td>Gen9.5</td>
<td>~9–13W</td>
<td>35W</td>
<td>2019</td>
<td>Dual NVMe NAS, serious homelab</td>
</tr>

<tr>
<td>
<a href="https://thinkstation-specs.com/wp-content/uploads/2019/09/P330-Tiny-Lenovo-ThinkStation.pdf" target="_blank">ThinkCentre P330</a>
</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html" target="_blank">i5-9400T</a> /
<a href="https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html" target="_blank">i7-9700T</a>
</td>
<td>6C / 6T – 8C / 8T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz" target="_blank">8148</a> /
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz" target="_blank">10553</a>
</td>
<td>64GB</td>
<td>2x M.2</td>
<td>1x PCIe 3.0 x8</td>
<td>Intel UHD 630</td>
<td>Gen9.5</td>
<td>~9–13W</td>
<td>35W</td>
<td>2019</td>
<td>Best 9th gen Tiny for virtualization</td>
</tr>

<tr>
<td>
<a href="https://www.lenovo.com/content/dam/lenovo/pcsd/north-america/en/solutions/workstations/datasheets/na-datasheet-thinkstation-p340-tiny.pdf" target="_blank">ThinkCentre P340</a>
</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html" target="_blank">i5-9400T</a> /
<a href="https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html" target="_blank">i7-9700T</a>
</td>
<td>6C / 6T – 8C / 8T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz" target="_blank">8148</a> /
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz" target="_blank">10553</a>
</td>
<td>64GB</td>
<td>2x M.2</td>
<td>1x PCIe 3.0 x8</td>
<td>Intel UHD 630</td>
<td>Gen9.5</td>
<td>~8–11W</td>
<td>35W</td>
<td>2020</td>
<td>Improved efficiency, better thermals</td>
</tr>

<tr>
<td>
<a href="https://news.lenovo.com/wp-content/uploads/2021/07/ThinkStationP350TinyDatasheet-Final.pdf" target="_blank">ThinkCentre P350</a>
</td>
<td>
<a href="https://www.intel.com/content/www/us/en/products/sku/212251/intel-core-i711700t-processor-16m-cache-up-to-4-60-ghz/specifications.html" target="_blank">i7-11700T</a>
</td>
<td>8C / 16T</td>
<td>
<a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-11700T+%40+1.40GHz" target="_blank">15363</a>
</td>
<td>64GB</td>
<td>2x M.2</td>
<td>1x PCIe 4.0 capable</td>
<td>Intel UHD 750</td>
<td>Gen12</td>
<td>~7–10W</td>
<td>35W</td>
<td>2021</td>
<td>Best for Plex, heavy VM host</td>
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
  <li> built in iGPU doesn't always work / default back to itself after having a dGPU, so if you buy it used have a low profile dGPU handy. upside the bios allows for iGPU+dGPU and will boot with a dGPU such as a tesla that includes zero display ports </li>
  <li> be careful with the 2.5in sata. if the cables aren't sitting quite right they can snap the data port off the drive, found that one out the hard way. there is a lot packed into very little space in this model so you have to be a bit mindful.</li></ul>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Model</th>
      <th>CPU</th>
      <th>Passmark CPU Bench</th>
      <th>RAM Max</th>
      <th>Drives/NVMe Slots</th>
      <th>PCIe Slot</th>
      <th>iGPU</th>
      <th>Power (TDP)</th>
      <th>Best Use Case</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://www.pcmag.com/reviews/hp-z240-sff-workstation?test_uuid=04IpBmWGZleS0I0J3epvMrC&test_variant=A" target="_blank">HP z240 SFF</a></td>
      <td><a href="https://www.intel.com/content/www/us/en/products/sku/88196/intel-core-i76700-processor-8m-cache-up-to-4-00-ghz/specifications.html" target="_blank">i7-6700</a></td>
      <td><a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-6700+%40+3.40GHz" target="_blank">8037</a></td>
      <td>64GB</td>
      <td>1x 2.5” + 2x 3.5” + 1xM.2</td>
      <td>2x PCIe x16</td>
      <td>Intel HD 530</td>
      <td>~65W</td>
      <td>Proxmox host, AI/ML, multi-GPU dev</td>
      <td> 7.5/10 </td>
    </tr>
    <tr>
      <td><a href="https://www.hardware-corner.net/desktop-models/Dell-OptiPlex-3020-SFF/" target="_blank">Dell Optiplex 3020</a></td>
      <td><a href="https://www.intel.com/content/www/us/en/products/sku/77486/intel-core-i34150-processor-3m-cache-3-50-ghz/specifications.html" target="_blank">i3-4150</a></td>
      <td><a href="https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i3-4150+%40+3.50GHz" target="_blank">3400</a></td>
      <td>16GB</td>
      <td>1x 3.5”</td>
      <td>1x PCIe x16</td>
      <td>Intel HD 4400</td>
      <td>~54W</td>
      <td>light server, media server, backup server.</td>
      <td> 4.5/10 </td>
    </tr>
  </tbody>
</table>
<br><a href="https://tachytelic.net/2021/12/dell-optiplex-7020-nvme-ssd/" target="_blank">Bios Mod - Install and boot from an NVMe SSD on a Dell OptiPlex 9020, 7020 or 3020</a>
<br> i have tested this on a Dell Optiplex 3020 and can verify it works if done properly. 
</details>
<details>
<summary>NIC:</summary>

<br>
<a href="https://www.digikey.com/htmldatasheets/production/2068431/0/0/1/intel-ethernet-server-adapter-i350-brief.html" target="_blank">Intel I350</a> (Quad-Port 1GbE)

<p align="left">
<img width="300" src="https://files.ekmcdn.com/itinstock/images/dell-intel-i350-t4-t34f4-quad-ports-1gbps-express-network-interface-card-1-89168-p.jpg?v=59DFCD45-8FDB-4D7E-BDFA-478F44C87A24">
</p>

The Intel I350 (commonly the I350-T4 variant) is one of the most popular server-grade 1GbE NICs for homelab and virtualization use.

<hr>

<b>Why It’s Recommended:</b>

• 4x independent 1GbE ports  
• PCIe 2.1 x4 interface  
• Very low CPU overhead  
• Excellent Linux / BSD support  
• Stable and widely supported in Proxmox, ESXi, TrueNAS, pfSense  

<hr>

<b>Virtualization Features:</b>

• <b>SR-IOV</b> (Single Root I/O Virtualization)  
• VLAN tagging offload  
• Checksum offloading  
• Interrupt moderation  
• PXE boot support  

SR-IOV allows you to assign virtual functions of the NIC directly to VMs, reducing overhead and improving network performance in virtualized environments.

If you are not running VMs or advanced networking, a simpler Intel NIC (like I210/I211) may be sufficient.

<hr>

<b>Performance Notes:</b>

• Each port is fully independent (not a simple switch internally)  
• Can be bonded (LACP) for redundancy or throughput  
• Ideal for firewall/router builds, lab segmentation, or Ceph/cluster networking  

<hr>

<b>Power Usage:</b>

• ~4–6W typical  
• Runs relatively cool compared to older quad NICs  

<hr>

<b>⚠️ Clone Warning:</b>

There are many counterfeit / cloned I350 cards on the used market.

Signs of genuine cards:
• Dell / HP / IBM branded versions are usually safe  
• Proper Intel markings on controller chip  
• Recognized correctly by `lspci` as Intel I350  

Clones may:
• Have unstable drivers  
• Fail under load  
• Not support SR-IOV properly 
</details>
<details>
<summary>SAS / HBA cards:</summary>

<a href="https://docs.broadcom.com/doc/12353333" target="_blank">LSI / Inspur 9211-8i</a> (Flashed to IT Mode)

<p align="left">
<img width="300" src="https://m.media-amazon.com/images/I/81Xb3aRiUuL._AC_.jpg">
</p>

The LSI 9211-8i is a classic 6Gb/s SAS HBA based on the LSI SAS2008 controller (PCIe 2.0 x8).  
Originally released around 2008, it remains extremely popular in homelab setups due to price and reliability.

<b>Important:</b> It must be flashed to <b>IT mode firmware</b> for proper ZFS usage (Proxmox, TrueNAS, Unraid, etc.).  
RAID firmware (IR mode) will force hardware RAID configuration and is NOT recommended for ZFS.

<hr>

<b>Technical Overview:</b>

• 8x internal drives (2x SFF-8087)  
• SAS2 – 6Gb/s per lane  
• PCIe 2.0 x8 (~4GB/s total bandwidth)  
• Full passthrough in IT mode  
• Uses mpt2sas driver (excellent Linux/BSD support)  

<hr>

<b>⚠️ TRIM / SSD Warning:</b>

The SAS2008 chipset does NOT properly pass TRIM / UNMAP to SATA SSDs in most configurations.  

For HDD arrays → perfectly fine.  
For SSD pools → use a newer SAS3 HBA.

<hr>
<hr>

<h4>✅ Newer Recommended Alternatives (SSD Safe / TRIM Support)</h4>

These models are frequently recommended on Proxmox forums, Level1Techs, and TrueNAS communities.

<hr>

<b>1) LSI 9207-8i (SAS2308)</b>

• SAS2 (6Gb/s)  
• PCIe 3.0 x8  
• Better power efficiency than 9211  
• TRIM/UNMAP passthrough works properly  
• Uses mpt2sas driver  
• Often ~$30–50 used  

This is widely considered the “safe upgrade” from the 9211-8i.

<hr>

<b>2) LSI 9300-8i (SAS3008)</b>

• SAS3 – 12Gb/s per lane  
• PCIe 3.0 x8  
• Full TRIM/UNMAP support  
• Uses mpt3sas driver  
• Lower latency and better SSD handling  
• ~$50–80 used  

Very commonly recommended for SSD ZFS pools.  
Excellent Proxmox / Ceph / TrueNAS card.

<hr>

<b>3) OEM Variants (Often Cheaper)</b>

Many rebranded versions exist:

• Dell HBA330  
• Dell H330 (in IT mode)  
• IBM M1215 (crossflashed)  
• Fujitsu D3307  
• Supermicro AOC-S3008L-L8e  

These often use the same LSI SAS2308 or SAS3008 chipsets internally and can be significantly cheaper on the used market.

Always confirm chipset before buying.

<hr>

<b>Why Upgrade From 9211?</b>

| Feature | 9211-8i | 9207-8i | 9300-8i |
|----------|-----------|-----------|------------|
| PCIe Gen | 2.0 | 3.0 | 3.0 |
| SAS Gen | SAS2 | SAS2 | SAS3 |
| TRIM | ❌ | ✅ | ✅ |
| SSD Friendly | ⚠️ | ✅ | ✅ |
| Idle Power | ~8–10W | ~6–8W | ~6–8W |

<hr>

<b>Thermals:</b>

All LSI cards run warm.

• Active airflow recommended  
• Especially important in Lenovo Tiny builds  
• Keep under ~70°C for stability  

<hr>

<b>Bottom Line:</b>

• Budget HDD-only array → 9211-8i is still unbeatable value  
• Mixed HDD + SSD → 9207-8i is safer  
• SSD-heavy / modern build → 9300-8i or SAS3008-based card  
• Double check you buy a model with IT mode firmware for homelab use. 

</details>
<details>
<summary>GPU:</summary>
<br><b>NVIDIA (vGPU / AI / Virtualization):</b>

<hr>

<b>Supported for vGPU (with vGPU Unlock):</b>

• Most GPUs from the Maxwell 2.0 generation (GTX 9xx, Quadro Mxxxx, Tesla Mxx) <b>EXCEPT the GTX 970</b>
• All GPUs from the Pascal generation (GTX 10xx, Quadro Pxxxx, Tesla Pxx)
• All GPUs from the Turing generation (GTX 16xx, RTX 20xx, Txxxx)

<b>Not Supported:</b>

• RTX 30 Series  
• RTX 40 Series 
• RTX 50 Series  

<br>Newer consumer GPUs do <b>NOT</b> work with vGPU Unlock. they have a different vBios/Firmware and added SR-IOV support, but the only person who has figured out how to make it work with unlock will not release the details fearing Nvidia may sue. so it is <b>NOT Publicly available</b> although their method breaks SR-IOV and makes vGPU supported the same way it was in turing and older versions. 

<hr>

<b>Architecture Notes:</b>

• <b>Pascal (GTX 10 Series / Tesla P4/P40)</b>  
  - Good for virtualization  
  - Fine for gaming VMs  
  - Not ideal for modern AI workloads
  - NVENC Has x265 support, Tesla models have 2x chips  

• <b>Turing (RTX 20 Series / Tesla T4)</b>  
  - Better NVENC  
  - Much better AI performance  
  - Best overall balance for homelab users  

If AI workloads are important → Turing or newer is strongly preferred.  (the P100 i believe is the only pascal that can properly handle AI, although turing is still recommended.) 
<br>If you only care about gaming VMs → Pascal is still perfectly usable. (on pascal they ONLY support FP32 so prompt processing and overall performance for AI tanks <b>HARD</b> compared to turing or newer.)

<hr>

<b>Tesla Cards:</b>

Tesla cards (P4, T4, L4) work very well for vGPU setups, but:

• Require NVIDIA vGPU licensing  
• Licensing server setup can be tedious  
• Additional configuration overhead compared to consumer cards  

That said, they are extremely efficient and powerful once configured properly.

<hr>

<b>Recommended Low-Power Options (Homelab Friendly):</b>

• Tesla P4 (8GB)  
• Tesla T4 (16GB) 
• Tesla L4 (24GB)

These typically run in the 60–75W range and offer performance comparable to much higher TDP consumer cards.

Example:

The Tesla P4 is essentially an underclocked GTX 1080 core,  
while the GTX 1080 has a 180W TDP — over 100W higher.

<a href="https://askgeek.io/en/gpus/vs/NVIDIA_Tesla-P4-vs-NVIDIA_GeForce-GTX-1080-Desktop" target="_blank">Tesla P4 vs GTX 1080 Benchmarks</a>

<hr>

<b>Real-World Experience:</b>

I personally use a Tesla P4 8GB.

• Successfully ran multiple 1080p gaming VMs simultaneously  
• Tested GTA V in two VMs at the same time  
• Stable performance once properly configured  

The only downside is the added complexity around licensing and setup.
<details>
<summary>Nvidia vGPU resources</summary>
<a href="https://gitlab.com/polloloco/vgpu-proxmox" target="_blank">NVIDIA vGPU Guide</a> 
<br><a href="https://alist.homelabproject.cc/foxipan/vGPU" target="_blank">Drivers</a> 
<br> licensing related:
<br><a href="https://git.collinwebdesigns.de/vgpu/gridd-unlock-patcher" target="_blank">gridd-unlock-patcher aka guest driver patch for versions after 18</a> 
<br><a href="https://git.collinwebdesigns.de/oscar.krause/fastapi-dls" target="_blank">FastAPI-DLS aka the licensing server.</a> 
<br><a href="https://github.com/GreenDamTan/vgpu_unlock-rs" target="_blank">vgpu_unlock-rs mirror by GreenDamTan</a> 
<br><a href="https://github.com/GreenDamTan/fastapi-dls_mirror" target="_blank">fastapi-dls_mirror by GreenDamTan</a>
</details>
<br><b>Intel (SR-IOV / vGPU Capable GPUs):</b>

<hr>

<b>Important:</b>

• Only <b>Intel Arc Pro</b> cards and Intel <b>iGPUs</b> officially support SR-IOV  
• Standard consumer Arc GPUs (A310, A380, A750, A770, etc.) do <b>NOT</b> support SR-IOV  

If you want hardware-level GPU virtualization without NVIDIA licensing, Arc Pro is currently one of the lowest-cost modern options.

<hr>

<a href="https://www.techpowerup.com/gpu-specs/arc-pro-b50.c4345" target="_blank">Intel Arc Pro B50</a>

<p align="left">
<img width="200" src="https://www.servethehome.com/wp-content/uploads/2025/05/Intel-Arc-Pro-B50-SFF-at-Computex-2025-2.jpg">
</p>

The Arc Pro B50 is one of the lowest-priced GPUs offering:

• 16GB VRAM  
• SR-IOV support  
• vGPU-style profile creation  
• Modern AV1 encode/decode  

Each SR-IOV profile presents itself as a separate GPU device that can be passed through directly to individual VMs.

This makes it extremely attractive for Proxmox and multi-VM lab setups.

<hr>

<b>Potential Issues / Early Adopter Warnings:</b>

<ul>
<li>
<b>BIOS / Firmware Updates:</b>  
SR-IOV may require a firmware update that officially must be done on Windows.  
Some users report success flashing from Linux, but others report bricking their cards when attempting it outside of Windows.
</li>

<li>
<b>Quick Sync / Media Encoding Issues:</b>  
QSV / media encoding on SR-IOV profiles can be inconsistent.  
Some users report that hardware encoding does not function properly inside GPU profiles.

Reference discussion:  
<a href="https://forum.level1techs.com/t/intel-arc-sr-iov-hack/200804/112" target="_blank">
"While the new Xe driver will have SR-IOV it will be useless as it seems to lack HUC firmware so no HW encoding"
</a>
</li>

<li>
<b>AI / Compute Ecosystem Limitations:</b>  
Support for Intel IPEX / XPU tooling is still limited compared to NVIDIA CUDA or even AMD ROCm.  
Vulkan and OpenCL performance is improving but still not as mature.

(Experience note: Tested with Arc A310 4GB — performance and driver stability can vary depending on workload.)
</li>
</ul>

<hr>

<b>Community Discussion (Proxmox 9+):</b>

<a href="https://forum.level1techs.com/t/proxmox-9-0-intel-b50-sr-iov-finally-its-almost-here-early-adopters-guide/238107?page=5" target="_blank">
Proxmox 9.0 + Intel Arc Pro B50 SR-IOV – Early Adopter’s Guide
</a>

<hr>

<b>When It Makes Sense:</b>

• You want real SR-IOV without NVIDIA licensing  
• You need 16GB VRAM per card at lower cost
• You are comfortable being an early adopter  

<b>When It Might Not:</b>

• Heavy AI workloads (CUDA ecosystem still dominates)  
• Production-critical media servers  
• Users wanting "it just works" stability  
<br>
<br><b>AMD (SR-IOV / vGPU Support):</b>

<hr>

AMD offers a hardware virtualization technology similar to NVIDIA’s vGPU and Intel’s SR-IOV called  
<a href="https://github.com/amd/MxGPU-Virtualization" target="_blank">MxGPU</a>

Unlike consumer Radeon cards, **only professional / datacenter GPUs** support SR-IOV / hardware virtualization.

<hr>

<b>Which AMD GPUs Support MxGPU / SR-IOV:</b>

• AMD Radeon Pro series (e.g., WX / W-series)  
• AMD MI Series (e.g., MI25, MI50 — Nvidia-equivalent compute cards)  
• AMD FirePro (older pro cards with SR-IOV)  

Consumer Radeon cards (RX 5000 / 6000 / 7000 series) do **NOT** support SR-IOV / MxGPU.

<hr>

<b>Key Things to Know:</b>

<ul>
<li>
<b>Hardware Virtualization:</b>  
MxGPU provides SR-IOV capable virtualization, allowing a single physical GPU to present multiple virtual GPUs to guest VMs.
</li>

<li>
<b>Driver & OS Support:</b>  
Strongest support in enterprise Linux distributions (RHEL / CentOS / Ubuntu) and supported hypervisors.  
Best results are typically seen with AMD’s enterprise drivers and platforms.
</li>

<li>
<b>Use Cases:</b>  
• VDI / graphical desktops  
• Virtualized compute workloads  
• Workloads requiring multi-tenant sharing of GPU resources
</li>

<li>
<b>Not Like NVIDIA vGPU Licensing:</b>  
Unlike NVIDIA’s licensed vGPU ecosystem, AMD’s MxGPU/SR-IOV support does *not* currently require the same type of licensing server or software keys.
</li>

<li>
<b>Documentation is Limited:</b>  
Community resources and forum posts are the most detailed sources of information so far — official AMD SR-IOV documentation is not as comprehensive as NVIDIA’s.
</li>
</ul>

<b>Contribution Request:</b>

If anyone in the community has direct experience with AMD SR-IOV (MxGPU) setup, BIOS/firmware fixes, driver configs, or guest compatibility tips, contributions would be very welcome here.

<hr>

AMD does have a hardware virtualization / SR-IOV capable ecosystem, but:

• It is **not** available on consumer Radeon cards / It is limited to **professional / compute series** GPUs  
• Documentation and real-world guides are still comparatively sparse  

For anyone experimenting with AMD GPUs + vGPU workflows, community experience is a very valuable resource!

<hr>
<br><b>GPU Models to compare them side by side:</b>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Model</th>
      <th>VRAM</th>
      <th>FP16 (half)</th>
      <th>FP32 (float)</th>
      <th>TDP</th>
      <th>Suggested PSU</th>
      <th>Bandwidth</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/arc-pro-a40.c3925" target="_blank">Intel Arc Pro A40</a></td>
  <td>6GB</td>
  <td>6.963 TFLOPS (2:1)</td>
  <td>3.482 TFLOPS</td>
  <td>50w</td>
  <td>250w</td>
  <td>192.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/arc-pro-a50.c3926" target="_blank">Intel Arc Pro A50</a></td>
  <td>6GB</td>
  <td>9.626 TFLOPS (2:1)</td>
  <td>4.813 TFLOPS</td>
  <td>75w</td>
  <td>250w</td>
  <td>192.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/arc-pro-a60.c4160" target="_blank">Intel Arc Pro A60</a></td>
  <td>12GB</td>
  <td>16.79 TFLOPS (2:1)</td>
  <td>8.397 TFLOPS</td>
  <td>130w</td>
  <td>300w</td>
  <td>384.0 GB/s</td>
</tr>
    <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/arc-pro-b50.c4345" target="_blank">Intel Arc Pro B50</a></td>
      <td>16GB</td>
      <td>21.30 TFLOPS (2:1)</td>
      <td>10.65 TFLOPS </td>
      <td>70w</td>
      <td>250w</td>
      <td>224.0 GB/s </td>
    </tr>
        <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/arc-pro-b60.c4350" target="_blank">Intel Arc Pro B60</a></td>
      <td>24GB</td>
      <td>24.58 TFLOPS (2:1)</td>
      <td>12.29 TFLOPS </td>
      <td>200w</td>
      <td>550w</td>
      <td>456.0 GB/s </td>
    </tr>
    <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/tesla-p4.c2879" target="_blank">NVIDIA Tesla P4</a></td>
      <td>8GB</td>
      <td>89.12 GFLOPS (1:64)</td>
      <td>5.704 TFLOPS </td>
      <td>75w</td>
      <td>250w</td>
      <td>192.3 GB/s</td>
    </tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/tesla-p40.c2878" target="_blank">NVIDIA Tesla P40</a></td>
  <td>24GB</td>
  <td>N/A</td>
  <td>N/A</td>
  <td>250w</td>
  <td>600w</td>
  <td>(384-bit GDDR5)</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/tesla-p100-pcie-12-gb.c2915" target="_blank">NVIDIA Tesla P100 PCIe 12GB</a></td>
  <td>12GB HBM2</td>
  <td>19.05 TFLOPS (2:1)</td>
  <td>9.526 TFLOPS</td>
  <td>250w</td>
  <td>600w</td>
  <td>549.1 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/tesla-p100-sxm2.c3183" target="_blank">NVIDIA Tesla P100 SXM2 16GB</a></td>
  <td>16GB HBM2</td>
  <td>21.22 TFLOPS (2:1)</td>
  <td>10.61 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>732.2 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-16-gb.c2957" target="_blank">NVIDIA Tesla V100 PCIe 16GB</a></td>
  <td>16GB HBM2</td>
  <td>28.26 TFLOPS (2:1)</td>
  <td>14.13 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>897.0 GB/s</td>
</tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-32-gb.c3184" target="_blank">NVIDIA Tesla V100 PCIe 32GB</a></td>
  <td>32GB HBM2</td>
  <td>~28.26 TFLOPS (2:1)</td>
  <td>~14.13 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>897.0 GB/s</td>
</tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-p5000.c2864" target="_blank">NVIDIA Quadro P5000</a></td>
  <td>16GB</td>
  <td>N/A</td>
  <td>N/A</td>
  <td>180w</td>
  <td>550w</td>
  <td>(256-bit GDDR5X)</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-p6000.c2865" target="_blank">NVIDIA Quadro P6000</a></td>
  <td>24GB</td>
  <td>0.1974 TFLOPS</td>
  <td>12.63 TFLOPS</td>
  <td>250w</td>
  <td>600w</td>
  <td>432.8 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-gp100.c2994" target="_blank">NVIDIA Quadro GP100</a></td>
  <td>16GB</td>
  <td>20.69 TFLOPS (2:1)</td>
  <td>10.34 TFLOPS</td>
  <td>235w</td>
  <td>550w</td>
  <td>732.2 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-gv100.c3066" target="_blank">NVIDIA Quadro GV100</a></td>
  <td>32GB HBM2</td>
  <td>33.32 TFLOPS (2:1)</td>
  <td>16.66 TFLOPS</td>
  <td>250w</td>
  <td>600w</td>
  <td>868.4 GB/s</td>
</tr>
  <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-rtx-6000.c3307" target="_blank">NVIDIA Quadro RTX 6000</a></td>
  <td>24GB GDDR6</td>
  <td>32.62 TFLOPS (2:1)</td>
  <td>16.31 TFLOPS</td>
  <td>260w</td>
  <td>600w</td>
  <td>672.0 GB/s</td>
</tr>
        <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/tesla-t4.c3316" target="_blank">NVIDIA Tesla T4</a></td>
      <td>16GB</td>
      <td>65.13 TFLOPS (8:1)</td>
      <td>8.141 TFLOPS  </td>
      <td>70w</td>
      <td>250w</td>
      <td>320.0 GB/s</td>
    </tr>
     <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/l4.c4091" target="_blank">NVIDIA Tesla L4</a></td>
      <td>24GB</td>
      <td>30.29 TFLOPS (1:1)</td>
      <td>30.29 TFLOPS </td>
      <td>72w</td>
      <td>250w</td>
      <td>192.3 GB/s</td>
    </tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-gtx-1080.c2839" target="_blank">NVIDIA GeForce GTX 1080</a></td>
  <td>8GB</td>
  <td>0.139 TFLOPS (1:64)</td>
  <td>8.873 TFLOPS</td>
  <td>180w</td>
  <td>450w</td>
  <td>320.3 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-gtx-1080-ti.c2877" target="_blank">NVIDIA GeForce GTX 1080 Ti</a></td>
  <td>11GB</td>
  <td>0.177 TFLOPS (1:64)</td>
  <td>11.34 TFLOPS</td>
  <td>250w</td>
  <td>600w</td>
  <td>484.4 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-2070.c3252" target="_blank">NVIDIA GeForce RTX 2070</a></td>
  <td>8GB</td>
  <td>14.93 TFLOPS (2:1)</td>
  <td>7.465 TFLOPS</td>
  <td>175w</td>
  <td>450w</td>
  <td>448.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-2080.c3224" target="_blank">NVIDIA GeForce RTX 2080</a></td>
  <td>8GB</td>
  <td>20.14 TFLOPS (2:1)</td>
  <td>10.07 TFLOPS</td>
  <td>215w</td>
  <td>550w</td>
  <td>448.0 GB/s</td>
</tr>
         <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-2080-ti.c3305" target="_blank">NVIDIA GeForce RTX 2080 Ti</a></td>
      <td>11GB</td>
      <td>26.90 TFLOPS (2:1)</td>
      <td>13.45 TFLOPS  </td>
      <td>250w</td>
      <td>600w</td>
      <td>616.0 GB/s</td>
    </tr>
         <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-3080-ti.c3735" target="_blank">NVIDIA GeForce RTX 3080 Ti</a></td>
      <td>12GB</td>
      <td>34.10 TFLOPS (1:1) </td>
      <td>34.10 TFLOPS </td>
      <td>350w</td>
      <td>7500w</td>
      <td>912.4 GB/s</td>
    </tr>
         <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-3090.c3622" target="_blank">NVIDIA GeForce RTX 3090</a></td>
      <td>24GB</td>
      <td>35.58 TFLOPS (1:1) </td>
      <td>35.58 TFLOPS </td>
      <td>350w</td>
      <td>7500w</td>
      <td>936.2 GB/s</td>
    </tr>
         <tr>
      <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-3090-ti.c3829" target="_blank">NVIDIA GeForce RTX 3090 Ti</a></td>
      <td>24GB</td>
      <td>40.00 TFLOPS (1:1)</td>
      <td>40.00 TFLOPS </td>
      <td>450w</td>
      <td>850w</td>
      <td>1.01 TB/s </td>
    </tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-4080.c3888" target="_blank">NVIDIA GeForce RTX 4080</a></td>
  <td>16GB</td>
  <td>48.74 TFLOPS (1:1)</td>
  <td>48.74 TFLOPS</td>
  <td>320w</td>
  <td>700w</td>
  <td>716.8 GB/s</td>
</tr>
      <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-4080-super.c4182" target="_blank">NVIDIA GeForce RTX 4080 SUPER</a></td>
  <td>16GB</td>
  <td>52.22 TFLOPS (1:1)</td>
  <td>52.22 TFLOPS</td>
  <td>320w</td>
  <td>700w</td>
  <td>736.3 GB/s</td>
</tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/geforce-rtx-4090.c3621" target="_blank">NVIDIA GeForce RTX 4090</a></td>
  <td>24GB</td>
  <td>~82.6 TFLOPS*</td>
  <td>~82.6 TFLOPS*</td>
  <td>450w</td>
  <td>1000w</td>
  <td>1008 GB/s</td>
</tr>
  <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-a2000.c3820" target="_blank">NVIDIA RTX A2000</a></td>
  <td>6GB</td>
  <td>7.987 TFLOPS (1:1)</td>
  <td>7.987 TFLOPS</td>
  <td>70w</td>
  <td>250w</td>
  <td>288.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-a2000-12-gb.c3853" target="_blank">NVIDIA RTX A2000 (12GB)</a></td>
  <td>12GB</td>
  <td>7.987 TFLOPS (1:1)</td>
  <td>7.987 TFLOPS</td>
  <td>70w</td>
  <td>250w</td>
  <td>288.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-a4500.c3849" target="_blank">NVIDIA RTX A4500</a></td>
  <td>20GB</td>
  <td>23.65 TFLOPS (1:1)</td>
  <td>23.65 TFLOPS</td>
  <td>200w</td>
  <td>550w</td>
  <td>640.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-a5000.c3748" target="_blank">NVIDIA RTX A5000</a></td>
  <td>24GB</td>
  <td>27.77 TFLOPS (1:1)</td>
  <td>27.77 TFLOPS</td>
  <td>230w</td>
  <td>550w</td>
  <td>768.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-a6000.c3686" target="_blank">NVIDIA RTX A6000</a></td>
  <td>48GB</td>
  <td>38.71 TFLOPS (1:1)</td>
  <td>38.71 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>768.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/rtx-6000-ada-generation.c3933" target="_blank">NVIDIA RTX 6000 Ada Generation</a></td>
  <td>48GB</td>
  <td>91.06 TFLOPS (1:1)</td>
  <td>91.06 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>960.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/quadro-rtx-6000.c3307" target="_blank">NVIDIA Quadro RTX 6000</a></td>
  <td>24GB</td>
  <td>32.62 TFLOPS (2:1)</td>
  <td>16.31 TFLOPS</td>
  <td>260w</td>
  <td>600w</td>
  <td>672.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xt.c3912" target="_blank">AMD Radeon RX 7900 XT</a></td>
  <td>20GB</td>
  <td>103.0 TFLOPS (2:1)</td>
  <td>51.48 TFLOPS</td>
  <td>300w</td>
  <td>700w</td>
  <td>800.0 GB/s</td>
</tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xtx.c3941" target="_blank">AMD Radeon RX 7900 XTX</a></td>
  <td>24GB</td>
  <td>122.8 TFLOPS (2:1)</td>
  <td>61.39 TFLOPS</td>
  <td>355w</td>
  <td>750w</td>
  <td>960.0 GB/s</td>
</tr>
    <tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/radeon-rx-9060-xt.c???" target="_blank">AMD Radeon RX 9060 XT</a></td>
  <td>8–16GB</td>
  <td>~51.3 TFLOPS (2:1)</td>
  <td>~25.6 TFLOPS</td>
  <td>150–160w</td>
  <td>450w</td>
  <td>320.0 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/radeon-rx-9070.c???" target="_blank">AMD Radeon RX 9070</a></td>
  <td>16GB</td>
  <td>~72.25 TFLOPS (2:1)</td>
  <td>~36.12 TFLOPS</td>
  <td>~220w</td>
  <td>600w</td>
  <td>896–960 GB/s</td>
</tr>
<tr>
  <td><a href="https://www.techpowerup.com/gpu-specs/radeon-rx-9070-xt.c???" target="_blank">AMD Radeon RX 9070 XT</a></td>
  <td>16GB</td>
  <td>~97.32 TFLOPS (2:1)</td>
  <td>~48.66 TFLOPS</td>
  <td>~304w</td>
  <td>750w</td>
  <td>960.0 GB/s</td>
</tr>
  </tbody>
</table>
</details>
</details>
<br>
<br><b>Suggested OS:</b>
<br><a href="https://www.proxmox.com/en/" target="_blank">Proxmox</a>
<details>
<summary>Proxmox related content:</summary>
Additional Resources:
<br><a href="https://community-scripts.github.io/ProxmoxVE/" target="_blank">Proxmox VE Helper scripts</a> - Hundreds of scripts to quickly setup a wide range of projects on proxmox.
<br><a href="https://github.com/MacRimi/ProxMenux" target="_blank">ProxMenux</a> - Seperate Dashboard / CLI menu with more information & management options handy for proxmox management.
<br>VMs:
<br><a href="https://github.com/kholia/OSX-KVM" target="_blank">OSX-KVM</a> - Mac OSX (multiple versions to choose from) On Proxmox. 
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
<br><b>Useful Software:</b>
<details>
<summary><b>RDP:</b></summary>
<a href="https://github.com/ClassicOldSong/Apollo" target="_blank">Apollo Sunshine fork</a>
<br><a href="https://github.com/LizardByte/Sunshine" target="_blank">Original Sunshine</a>
<br><a href="https://github.com/moonlight-stream" target="_blank">Moonlight</a>
<br>Windows: <a href="https://github.com/Upinel/BetterRDP" target="_blank">BetterRDP for windows to enable 60fps and GPU acceleration on RDP connections</a> - Better RDP for more so seemless and native like interaction which makes the experience seem more like a native PC insted of RDP over the local network. this is great for most games and more intensive / latency dependant softwares.
</details>
<details>
<summary><b>Gaming:</b></summary>
Windows: <a href="https://github.com/microsoft/RdpGamepad" target="_blank">RdpGamepad - a Remote Desktop Plugin for Xbox Gamepads</a> - Use Xbox 360/One controllers over RDP/moonlight/sunshine
</details>
<details>
<summary><b>File management:</b></summary>
Windows: <a href="https://github.com/evsar3/sshfs-win-manager" target="_blank">SSHFS-Win Manager is a GUI for SSHFS on Windows</a>
<br> Linux: <a href="https://github.com/libfuse/sshfs" target="_blank">SSHFS</a>
</details>
<details>
<summary><b>Caching:</b></summary>
Windows: <a href="https://www.romexsoftware.com/en-us/primo-cache/" target="_blank">Primo Cache</a>
</details>
<details>
<summary><b>Firewall/Networking:</b></summary>
Linux: <a href="https://github.com/evilsocket/opensnitch" target="_blank">OpenSnitch</a> - Network monitoring and rule based control
<br> Windows: <a href="https://github.com/henrypp/simplewall" target="_blank">SimpleWall</a> - Windows firewll management and rules.
<br> Mac: <a href="https://www.obdev.at/products/littlesnitch/index.html" target="_blank">LittleSnitch</a> - Network monitoring and control.
<br> Win/Linux: <a href="https://safing.io/download/" target="_blank">Safing Portmaster</a>
<br> Windows: <a href="https://www.netlimiter.com/" target="_blank">NetLimiter</a> - Per application bandwitdh limits
</details>
<details>
<summary><b>Host Power Management:</b></summary>
Linux: <a href="https://github.com/fenrus75/powertop" target="_blank">PowerTop</a> - Tweak Host for power savings.
</details>
<Br><b>SelfHosted:</b>
<br><a href="https://github.com/awesome-selfhosted/awesome-selfhosted" target="_blank">Awesome-Selfhosted</a>
