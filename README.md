# HomeLab
HomeLab CheatSheet &amp; AwesomeList
<br> Created for the [HomeLab Group](https://smp6.simplex.im/g#P45YjyWy-__e3p3OqoRvU_4sjcSorUz0v8hCtWEPRtk) on Simplex Chat [![Simplex Chat](https://avatars.githubusercontent.com/u/59927747?s=48&v=4)](https://simplex.chat/)
<br>
<br> The goal of this repo is to become your map to help you navigate the HomeLabbing experience. 
<br> This page will be updated randomly with new information, so stay tuned. (contributions welcome!)
<br>
<br> Note: many of the hardware suggestions here are mostly the best items in their class for the lowest prices.
<br>
<br>ToDo: 
<br> * Update table of contents...
<br> * Add CPU Tables 
<br> * Add more hardware information including more Nic models / HBA models / Enterprise drive models and information. 
<br> * Add more general filesystem information / ZFS information / tips with more links to obscure useful information that will help manage ZFS better.  
<br> * Add more software/Self hosting options and guide links. 
<br> * Add more proxmox related information and helpful guides, including those related to GPU passthrough, LXCs, etc 
# Table of Contents
1. [Hardware](#hardware)
   - [Recommended Devices](#recommended-devices)
     - [Minimal / Tiny PCs](#minimal--tiny-pcs)
     - [SFF Suggestions](#sff-suggestions)
   - [NIC (Network Cards)](#nic-network-cards)
   - [SAS / HBA Cards](#sas--hba-cards)
     - [LSI 9211-8i (IT Mode)](#lsi-9211-8i-it-mode)
     - [Newer Recommended Alternatives (SAS2308 / SAS3008)](#newer-recommended-alternatives-sas2308--sas3008)
   - [SSD/Nvme Drives](#SSD/Nvme-Drives)
     - [Enterprise NVMe / M.2 Drives with Endurance](#Enterprise-NVMe--M.2-Drives-with-Endurance)
     - [Consumer NVMe / M.2 Drives](#Consumer-NVMe--M.2-Drives)
     - [Consumer vs. Enterprise Price Comparison](#Consumer-vs.-Enterprise-Price-Comparison)
   - [GPU](#gpu)
     - [NVIDIA (vGPU / AI / Virtualization)](#nvidia-vgpu--ai--virtualization)
       - Supported Generations
       - Tesla Low-Power Options
       - vGPU Licensing Notes
       - vGPU Resources
     - [Intel (SR-IOV / Arc Pro)](#intel-sr-iov--arc-pro)
       - Arc Pro B-Series
       - Firmware / Early Adopter Notes
     - [AMD (MxGPU / SR-IOV)](#amd-mxgpu--sr-iov)
       - Supported Professional Series
       - MxGPU Overview
       - Contribution Request
     - [GPU Model Comparison Table](#gpu-model-comparison-table)
       - [Intel GPU Master Table](#intel-gpu-master-table)
       - [NVIDIA RTX 10 Series (Pascal)](#nvidia-rtx-10-series-pascal)
       - [NVIDIA RTX 20 Series (Turing)](#nvidia-rtx-20-series-turing)
       - [NVIDIA RTX 30 Series (Ampere)](#nvidia-rtx-30-series-ampere)
       - [NVIDIA RTX 40 Series (Ada Lovelace)](#nvidia-rtx-40-series-ada-lovelace)
       - [NVIDIA RTX 50 Series (Blackwell)](#nvidia-rtx-50-series-blackwell)
       - [NVIDIA Quadro / Professional GPUs](#nvidia-quadro-professional-gpus)
       - [NVIDIA RTX A-Series (Professional GPUs)](#nvidia-rtx-a-series-professional-gpus)
       - [NVIDIA Tesla Series](#nvidia-tesla-series)
       - [AMD Radeon RX 5000 Series (RDNA1)](#amd-radeon-rx-5000-series-rdna1)
       - [AMD Radeon RX 6000 Series (RDNA2)](#amd-radeon-rx-6000-series-rdna2)
       - [AMD Radeon RX 7000 Series (RDNA3)](#amd-radeon-rx-7000-series-rdna3)
       - [AMD Radeon RX 9000 Series (RDNA4)](#amd-radeon-rx-9000-series-rdna4)
       - [AMD Pro/Compute GPUs](#amd-procompute-gpus)

2. [Suggested OS](#suggested-os)
   - [Proxmox](#proxmox)
   - [Filesystems](#filesystems)

3. [Software](#software)
   - [RDP](#rdp)
   - [Gaming](#gaming)
   - [File Management](#file-management)
   - [File Sharing](#file-sharing)
   - [Caching](#caching)
   - [Firewall / Networking](#firewallnetworking)
   - [Host Power Management](#host-power-management)

4. [SelfHosted](#selfhosted)
   - [Awesome-Selfhosted](#awesome-selfhosted)
<br>
<br><b>Hardware:</b>
<br>Recommended Devices:

## Optimal Minimal Setup Device: Lenovo Tiny PCs
  <p align="left">
  <img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/Lenovo-tiny-pc.jpg"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-thinkcentre-m715q-gen2-tiny-pc-amd-ryzen-5-2400ge.jpg"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-gpu.png"><img width="200" src="https://github.com/AncientMystic/HomeLab/blob/main/img/devices/lenovo-tiny-pc/lenovo-tiny-pc-nvme.jpg">
</p>

---

### Hardware Configuration Options

Lenovo Tiny PCs offer various hardware configurations, such as:

- **Intel CPUs** or **AMD Ryzen CPUs**
- **Single NVMe + SATA 2.5in Drives**
- **2x NVMe** or **2x NVMe + PCIe Slot**

### Popular Uses for the PCIe Slot

- Nvidia Quadro P600/P620/P1000/T400/T600 (included with some models)
- A Quad Port NIC (popular for router setups, such as **Opnsense/Pfsense** )
- NVMe Expansion Card (adds 2x additional NVMe drives, providing up to 4x NVMe on some models)

---

### Power and Performance

- **Idle Power Consumption**: as low as 5-7W (depending on configuration)
- **CPU TDP**: Medium to Medium-High performance with 35W TDP CPUs
- **RAM Support**: 32GB to 128GB (depends on model, 2 slots)
- **Mini PCIe Slots**: For WiFi + Bluetooth cards
- **USB Ports**: 4-6 USB 3+ ports in newer models

These devices are small, powerful, and make perfect all-in-one mini servers for various use cases. The **Intel** versions even allow you to share the **iGPU** with **Proxmox** for multiple virtual machines.

---

### Why Lenovo Tiny PCs?

Other mini PCs and SFF PCs can be worthwhile, but personally, I find the Lenovo Tiny PCs to be the most optimal, cost-effective options for home labs and other small-scale setups.

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

### SFF Suggestion

One of the most cost effective SFF PCs for price vs hardware potential
<br><b>HP z240 SFF</b>
<p align="left"><img width="300" src="https://i.pcmag.com/imagery/reviews/02pEw0PoQLzntoO4LnGl1jE-1.fit_lim.size_740x416.v_1569469958.jpg"></p>
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

### NIC:

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

<hr>

### SAS / HBA cards:

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

Note: full trim support requires IT firmware and driver support. Some versions of the mpt3sas driver break trim. otherwise it is required that the SSD to support RZAT (deterministic read zeros after trim)

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

<hr>

### Enterprise SATA/SAS HDDs:

| **Drive Model**                                 | **Form Factor** | **Interface**   | **Capacity Options** | **Workload Rating (TB/yr)** | **Watts (Idle/Active)**   |
| ----------------------------------------------- | --------------- | --------------- | -------------------- | --------------------------- | ------------------------- |
| **HGST Ultrastar He10 / HC310**                 | 3.5"            | SATA / SAS 12Gb | 10TB                 | 550 TB/yr                   | ~5.8W / ~9.5W             |
| **HGST Ultrastar He12 / HC320**                 | 3.5"            | SATA / SAS 12Gb | 12TB                 | 550 TB/yr                   | ~6.0W / ~9.8W             |
| **HGST Ultrastar He14 / HC330**                 | 3.5"            | SATA / SAS 12Gb | 14TB                 | 550 TB/yr                   | ~6.2W / ~10W              |
| **HGST Ultrastar He16 / HC340**                 | 3.5"            | SATA / SAS 12Gb | 16TB                 | 550 TB/yr                   | ~6.4W / ~10.2W            |
| **HGST Ultrastar He18 / HC350**                 | 3.5"            | SATA / SAS 12Gb | 18TB                 | 550 TB/yr                   | ~6.5W / ~10.4W            |
| **WD Ultrastar DC HC500 (HGST Legacy)**         | 3.5"            | SATA / SAS 12Gb | 8TB, 10TB            | 550 TB/yr                   | ~5.6W / ~9.2W             |
| **WD Ultrastar DC HC550**                       | 3.5"            | SATA / SAS 12Gb | 14TB, 16TB, 18TB     | 550 TB/yr                   | ~5.8W / ~9.5W             |
| **WD Ultrastar DC HC560**                       | 3.5"            | SATA / SAS 12Gb | 20TB, 22TB           | 550 TB/yr                   | ~6.0W / ~9.8W             |
| **WD Ultrastar DC SA620 (SATA SSD/HDD Hybrid)** | 2.5"            | SATA 6Gb/s      | 960GB — 7.68TB       | *N/A (SSHD)*                | ~2.9W / ~5.5W             |
| **WD Gold Enterprise HDDs**                     | 3.5"            | SATA 6Gb/s      | 1TB — 18TB           | 550 TB/yr                   | 5W — 10W (varies by size) |
| **Seagate Exos X18**                   | 3.5"            | SATA 6Gb/s    | 10TB, 12TB, 14TB, 16TB, 18TB      | 550 TB/yr                     | 5.3W / 9.4W             |
| **Seagate Exos X20**                   | 3.5"            | SATA 6Gb/s    | 16TB, 18TB, 20TB                  | 550 TB/yr                     | 5.4W / 9.4W             |
| **Seagate Exos 7E10**                  | 3.5"            | SAS 12Gb/s    | 1TB, 2TB, 4TB, 8TB                | 550 TB/yr                     | 7.6W / 11.5W            |
| **Toshiba MG09 Series**                | 3.5"            | SATA / SAS    | 14TB, 16TB, 18TB                  | 550 TB/yr                     | 4.2W / 8.3W             |
| **Toshiba MG10 Series**                | 3.5"            | SATA / SAS    | 20TB, 22TB                        | 550 TB/yr                     | 4.4W / 8.6W             |
| **Seagate Exos 10E2400 (2.4TB)**       | 2.5"            | SAS 12Gb/s    | 600GB, 900GB, 1.2TB, 1.8TB, 2.4TB | 550 TB/yr                     | 3.8W / 6.9W             |
| **Western Digital Ultrastar 10K600**   | 2.5"            | SAS 12Gb/s    | 600GB, 900GB, 1.2TB               | 550 TB/yr                     | 3.6W / 6.5W             |

NOTES: HGST have the Lowest failure rates, followed by Western Digital. 
<br> Seagate / Toshiba models tend to have higher failure rates depending on models. but they are often cheaper, sometimes by a fair amount. 

<hr>

### SSD/Nvme Drives:

# Enterprise NVMe / M.2 Drives with Endurance

| **Drive Model**                                  | **Form Factor** | **Interface**   | **Endurance (TBW/PBW)**   | **Watts (Idle/Active)** |
|-------------------------------------------------|-----------------|-----------------|----------------------------|-------------------------|
| **Intel Optane M10 (16GB)**                     | M.2 2280        | PCIe 3.0 x2     | 365 TBW                    | .08W/2W                 |
| **Intel Optane M10 (32GB)**                     | M.2 2280        | PCIe 3.0 x2     | 182.5 TBW                  | 1W/3.5W                 |
| **Intel Optane SSD 905P (480GB, 960GB, 1.5TB)** | M.2 2280        | PCIe 3.0 x4     | 17.52 PB                   | 6W/16.4W                |
| **Samsung PM9A3 (960GB, 1920GB, 3840GB)**       | M.2 22110       | PCIe 4.0 x4     | 1.7 PBW / 3.5PBW / 7.0 PBW | 3.5W/8W(Avg)9.8W(Max)   |
| **Seagate Nytro 5000 (1.6TB, 3.2TB, 6.4TB)**    | M.2 22110       | PCIe 3.0 x4     | 3.2 PBW (3.2TB)            | 9W(Avg)/12.5W(Max)      |
| **Intel DC P5800X (400GB, 800GB, 1.6TB)**       | U.2             | PCIe 4.0 x4     | 73PBW / 146 PBW / 292 PBW  | 4.2W/18W                |
| **ADATA XPG SX8200 Pro (256gb,512GB,1TB,2TB)**  | M.2 2280        | PCIe 3.0 x4     | 160/320/640/NA TBW         | .05W/1.9W(Avg)/4.1W(Max)|
| **Intel DC P3700 400GB**                        | PCIE            | PCIe 3.0 x4     | 7.3 PBW                    | 4W/9W(Avg)/12W(Max)     |
| **Intel Optane P4801X 100GB**                   | M.2 2280        | PCIe 3.0 x4     | 10.9PBW                    | 3W/7W                   |

# Consumer NVMe / M.2 Drives

| **Drive Model**                                        | **Form Factor** | **Interface**   | **Endurance (TBW)**        |       **Quality**       |
|-------------------------------------------------------|-----------------|-----------------|----------------------------|--------------------------|
| **Crucial P3 1TB**                                    | M.2 2280        | PCIe 3.0 x4     | 220 TB                     |   Cheap QLC Consumer     |
| **Samsung 980 1TB**                                   | M.2 2280        | PCIe 3.0 x4     | 600 TB                     |    Normal TLC Consumer   |
| **Samsung 980 Pro 1TB**                               | M.2 2280        | PCIe 4.0 x4     | 600 TB                     |   Modern TLC Prosumer    |
| **Samsung 970 Pro 1TB**                               | M.2 2280        | PCIe 3.0 x4     | 1,200 TB                   | End-of-Life MLC Prosumer | 


---

## Consumer vs. Enterprise Price Comparison

Enterprise drives are designed to handle much higher workloads and offer greater durability compared to consumer-grade drives. While consumer drives may seem more affordable, they often burn out quickly in high-write environments such as servers or when used with ZFS, which requires frequent read/write operations. Enterprise SSDs are built for sustained performance, higher endurance (TBW/PBW), and reliability, making them the preferable choice for demanding applications where data integrity and long-term use are crucial.

### CPU: 
<br> section in progress / to be updated
<details>
<summary><b>Intel:</b></summary>
</details>

<details>
<summary><b>AMD:</b></summary>
</details>

### Disable Turbo Boost!

# Turbo Boost – Power, Heat & How to Disable It

Modern Intel CPUs support **Turbo Boost**, a feature that automatically increases clock speeds above the base frequency when thermal and power headroom allow.

While this improves burst performance, it also significantly increases:

- ⚡ Power consumption (PL2 spikes)
- 🌡️ CPU temperature
- 🔊 Fan noise
- 🔋 Idle-to-load power variance
- 🖥️ Sustained heat output in small form factor systems

Turbo works by temporarily raising power limits (PL2) well above the rated TDP (PL1). For example, a 65W CPU may briefly pull 200W+ under turbo. In compact builds, homelabs, or always-on systems, this can:

- Cause thermal throttling
- Increase system instability
- Raise long-term power costs
- Increase VRM and PSU stress

Disabling Turbo Boost forces the CPU to remain at base clocks (PL1), reducing peak temperatures and flattening power spikes.

---

## 1. Disabling Turbo Boost in BIOS (Recommended Method)

This is the most reliable and OS-independent method.

### Steps:

1. Reboot your system.
2. Enter BIOS/UEFI (usually `DEL`, `F2`, or `F10`).
3. Navigate to:
   - **Advanced CPU Settings**
   - **Processor Configuration**
   - **Overclocking / Performance**
4. Locate one of the following options:
   - **Intel Turbo Boost**
   - **Intel Turbo Boost Technology**
   - **Turbo Mode**
5. Set it to **Disabled**.
6. Save and exit.

**Advantages:**

- Completely prevents turbo at firmware level.
- Works across Linux, Windows, hypervisors, etc.
- Best method for servers and homelabs.

---

## 2. Disabling Turbo Boost on Linux

### Method A — Using rc.local

You can disable turbo at boot by writing to the Intel pstate driver.

Create the file:

```
/etc/rc.local
```

Ensure:

- Owner: `root`
- Group: `root`
- Permissions: `700` (`rwx------`)

Add the following content:

```bash
#!/bin/sh
echo 1 > /sys/devices/system/cpu/intel_pstate/no_turbo
exit 0
```

Save the file.

Reboot and verify:

```bash
cat /sys/devices/system/cpu/intel_pstate/no_turbo
```

If it returns:

```
1
```

Turbo is disabled.

---

### Method B — Using intel-noturbo

Project:

https://github.com/ShyVortex/intel-noturbo

This provides a cleaner toggle utility for enabling/disabling turbo without manually editing system files.

Useful for:

- Laptops
- Testing thermals
- Scripted power profiles

---

## 3. Disabling Turbo Boost on Windows

Windows does not expose a simple Turbo toggle by default, but you can disable it via Power Options.

A commonly used method involves importing a `.reg` file that adds the hidden processor performance boost mode setting into Windows Power Options.

- [.reg file link](https://www.geeks3d.com/dl/show/10060) 

After importing:

1. Open **Power Options**
2. Edit your current power plan
3. Go to:

```
Processor power management
```

4. Set:

```
Processor performance boost mode → Disabled
```

This effectively disables Turbo Boost at the OS level.

**Note:**  
BIOS-level disabling is more reliable. Windows-level disabling can sometimes be overridden by firmware or vendor utilities.

---

## When Should You Disable Turbo?

### Turbo OFF is useful for:

- Small form factor builds
- Passive cooling systems
- Homelabs
- Always-on servers
- Noise-sensitive environments
- Power efficiency optimization
- Thermal stability

---

## Power & Temperature Impact

| Scenario         | Turbo ON               | Turbo OFF        |
|------------------|------------------------|------------------|
| Peak Power       | Very High (PL2 spikes) | Stable (PL1 only)|
| Max Temperature  | 80–100°C common        | 50–75°C typical  |
| Fan Noise        | High ramping           | Much quieter     |
| Sustained Load   | May throttle           | More stable      |

Actual results depend on CPU generation and cooling.

<details>
<summary><b>Turbo boost Power consumption Examples in watts<b></summary>
   
<br> PL1 = TDP - PL2 = Turbo Boost 

| **Processor**                                                      | **PL1 Power (W)** | **PL2 Power (W)** | **TAU (Seconds)** |
| ------------------------------------------------------------------ | ----------------- | ----------------- | ----------------- |
| **11th Gen**                                                       |                   |                   |                   |
| Core i9-11900K                                                     | 125               | 251               | 56                |
| Core i7-11700K                                                     | 125               | 251               | 56                |
| Core i5-11600K                                                     | 125               | 224               | 56                |
| Core i9-11900                                                      | 65                | 224               | 28/56             |
| Core i7-11700                                                      | 65                | 224               | 28/56             |
| Core i5-11600, Core i5-11500, Core i5-11400                        | 65                | 154               | 28/56             |
| Core i9-11900T                                                     | 35                | 115               | 28                |
| Core i7-11700T                                                     | 35                | 115               | 28                |
| Core i5-11600T                                                     | 35                | 84                | 28                |
| Core i9-10900K                                                     | 125               | 250               | 56                |
| **10th Gen**                                                       |                   |                   |                   |
| Core i7-10700K                                                     | 125               | 229               | 56                |
| Core i5-10600K                                                     | 125               | 182               | 56                |
| Core i9-10900                                                      | 65                | 224               | 28                |
| Core i7-10700                                                      | 65                | 224               | 28                |
| Core i5-10600, Core i5-10500, Core i5-10400                        | 65                | 134               | 28                |
| Core i3-10320, Core i3-10300, Core i3-10100                        | 65                | 90                | 28                |
| Pentium Gold 6500, Pentium Gold 6400, Celeron G5920, Celeron G5900 | 58                | 58                | 28                |
| Core i9-10900T                                                     | 35                | 123               | 28                |
| Core i7-10700T                                                     | 35                | 123               | 28                |
| Core i5-10000T                                                     | 35                | 92                | 28                |
| Core i3-10000T                                                     | 35                | 55                | 28                |
| Pentium Gold G6500T, Pentium Gold G6400T, Celeron 5900T            | 35                | 42                | 28                |

<br> Note: As you can see, this can result in up to 3.5x brief spikes in watt usage, which also drastically increases temps.
</details>

<hr>

### GPU:
<b>NVIDIA (vGPU / AI / Virtualization):</b>

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

### GPU Models to compare them side by side:
i often found myself looking up these details when comparing GPUs to try to find the best option for the price, so i added a table here of most GPUs for quick reference comparisons. 
<br>NOTE: Idle est. may not be accurate, different configurations vary widely. 

## Intel GPU Master Table

| Model                                                                        | VRAM       | FP32         | FP16 | TDP  | Est. Idle | Bandwidth | Virtualization |
| ---------------------------------------------------------------------------- | ---------- | ------------ | ---------- | ---- | --------- | --------- | -------------- |
| [Intel Arc A310](https://www.techpowerup.com/gpu-specs/arc-a310.c3931)       | 4GB GDDR6  | 3.072 TFLOPS | 6.144 TFLOPS | 75W  | 8–15W     | 124 GB/s  | ❌ No SR-IOV    |
| [Intel Arc A380](https://www.techpowerup.com/gpu-specs/arc-a380.c3913)       | 6GB GDDR6  | 4.198 TFLOPS  | 8.397 TFLOPS  | 75W  | 8–15W     | 186 GB/s  | ❌ No SR-IOV    |
| [Intel Arc A580](https://www.techpowerup.com/gpu-specs/arc-a580.c3927)       | 8GB GDDR6  | 12.29 TFLOPS   | 24.58 TFLOPS  | 185W | 15–25W    | 256 GB/s  | ❌ No SR-IOV    |
| [Intel Arc A750](https://www.techpowerup.com/gpu-specs/arc-a750.c3922)       | 8GB GDDR6  | 17.20 TFLOPS | 34.41 TFLOPS  | 225W | 18–30W    | 512 GB/s  | ❌ No SR-IOV    |
| [Intel Arc A770 16GB](https://www.techpowerup.com/gpu-specs/arc-a770.c3914)  | 16GB GDDR6 | 19.66 TFLOPS | 39.32 TFLOPS  | 225W | 18–30W    | 512 GB/s  | ❌ No SR-IOV    |
| [Intel Arc Pro A40](https://www.techpowerup.com/gpu-specs/arc-pro-a40.c3925) | 6GB GDDR6  | 3.482 TFLOPS  | 6.963 TFLOPS  | 50W  | 6–10W     | 192 GB/s  | ✅ SR-IOV       |
| [Intel Arc Pro A50](https://www.techpowerup.com/gpu-specs/arc-pro-a50.c3926) | 6GB GDDR6  | 4.813 TFLOPS  | 9.626 TFLOPS  | 75W  | 8–15W     | 192 GB/s  | ✅ SR-IOV       |
| [Intel Arc Pro A60](https://www.techpowerup.com/gpu-specs/arc-pro-a60.c4160) | 12GB GDDR6 | 8.397 TFLOPS  | 16.79 TFLOPS  | 130W | 10–20W    | 384 GB/s  | ✅ SR-IOV       |
| [Intel Arc B580](https://www.techpowerup.com/gpu-specs/arc-b580.c4244)       | 12GB GDDR6  | 13.67 TFLOPS | 27.34 TFLOPS  | 190W | 15–25W    | 256 GB/s  | ❌ No SR-IOV    |
| [Intel Arc Pro B50](https://www.techpowerup.com/gpu-specs/arc-pro-b50.c4345) | 16GB GDDR6 | 10.65 TFLOPS | 21.30 TFLOPS  | 70W  | 7–15W     | 224 GB/s  | ✅ SR-IOV       |
| [Intel Arc Pro B60](https://www.techpowerup.com/gpu-specs/arc-pro-b60.c4350) | 24GB GDDR6 | 12.29 TFLOPS | 24.58 TFLOPS  | 200W | 15–30W    | 456 GB/s  | ✅ SR-IOV       |

## NVIDIA RTX 10 Series (Pascal)

| Model                                                                             | VRAM  | **FP16**                  | **FP32**                  | **TDP** | **Idle Power** | **Bandwidth** | **Virtualization** |
| --------------------------------------------------------------------------------- | ----- | ------------------------- | ------------------------- | ------- | -------------- | ------------- | ------------------ |
| [GTX 1050](https://www.techpowerup.com/gpu-specs/geforce-gtx-1050.c2875)          | 2 GB  | 29.10 GFLOPS              | 1.862 TFLOPS              | 75 W    | ~8–12 W        | 112 GB/s      | ✅ Unlock           |
| [GTX 1050 Ti](https://www.techpowerup.com/gpu-specs/geforce-gtx-1050-ti.c2885)    | 4 GB  | 33.41 GFLOPS              | 2.138 TFLOPS              | 75 W    | ~8–12 W        | 112 GB/s      | ✅ Unlock           |
| [GTX 1060 3GB](https://www.techpowerup.com/gpu-specs/geforce-gtx-1060-3-gb.c2867) | 3 GB  | 61.49 GFLOPS              |  3.935 TFLOPS             | 120 W   | ~10–18 W       | 192 GB/s      | ✅ Unlock           |
| [GTX 1060 6GB](https://www.techpowerup.com/gpu-specs/geforce-gtx-1060-6-gb.c2862) | 6 GB  | 68.36 GFLOPS              |  4.375 TFLOPS             | 120 W   | ~10–18 W       | 192 GB/s      | ✅ Unlock           |
| [GTX 1070](https://www.techpowerup.com/gpu-specs/geforce-gtx-1070.c2840)          | 8 GB  | 101.0 GFLOPS              | 6.463 TFLOPS              | 150 W   | ~12–20 W       | 256 GB/s      | ✅ Unlock           |
| [GTX 1070 Ti](https://www.techpowerup.com/gpu-specs/geforce-gtx-1070-ti.c3010)    | 8 GB  | 127.9 GFLOPS              | 8.186 TFLOPS              | 180 W   | ~15–25 W       | 256 GB/s      | ✅ Unlock           |
| [GTX 1080](https://www.techpowerup.com/gpu-specs/geforce-gtx-1080.c2839)          | 8 GB  | 139 GFLOPS                | 8.873 TFLOPS              | 180 W   | ~15–25 W       | 320.3 GB/s    | ✅ Unlock           |
| [GTX 1080 Ti](https://www.techpowerup.com/gpu-specs/geforce-gtx-1080-ti.c2877)    | 11 GB | 177.2 GFLOPS              | 11.34 TFLOPS              | 250 W   | ~18–30 W       | 484.4 GB/s    | ✅ Unlock           |

## NVIDIA RTX 20 Series (Turing)

| GPU | CUDA | VRAM | FP32 | FP16 | TDP | Idle | Virtualization |
|-----|------|------|------|------|-----|------|----------------|
| [RTX 2060](https://www.techpowerup.com/gpu-specs/geforce-rtx-2060.c3310) | 1920 | 6GB GDDR6 192-bit | 6.5 TF | 6.5 TF | 160W | ~8W | ✅ Unlock |
| [RTX 2060 Super](https://www.techpowerup.com/gpu-specs/geforce-rtx-2060-super.c3441) | 2176 | 8GB GDDR6 256-bit | 7.2 TF | 7.2 TF | 175W | ~9W | ✅ Unlock |
| [RTX 2070](https://www.techpowerup.com/gpu-specs/geforce-rtx-2070.c3252) | 2304 | 8GB GDDR6 256-bit | 7.5 TF | 7.5 TF | 175W | ~9W | ✅ Unlock |
| [RTX 2070 Super](https://www.techpowerup.com/gpu-specs/geforce-rtx-2070-super.c3440) | 2560 | 8GB GDDR6 256-bit | 9.1 TF | 9.1 TF | 215W | ~9W | ✅ Unlock |
| [RTX 2080](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080.c3224) | 2944 | 8GB GDDR6 256-bit | 10.1 TF | 10.1 TF | 215W | ~10W | ✅ Unlock |
| [RTX 2080 Super](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080-super.c3439) | 3072 | 8GB GDDR6 256-bit | 11.2 TF | 11.2 TF | 250W | ~10W | ✅ Unlock |
| [RTX 2080 Ti](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080-ti.c3305) | 4352 | 11GB GDDR6 352-bit | 13.4 TF | 13.4 TF | 250W | ~11W | ✅ Unlock |

## NVIDIA RTX 30 Series (Ampere)

| **Model**                                                                           | **VRAM** | **FP16**     | **FP32**     | **TDP** | **Idle Power** | **Bandwidth** | **Virtualization** |
| ----------------------------------------------------------------------------------- | -------- | ------------ | ------------ | ------- | -------------- | ------------- | ------------------ |
| [RTX 3060 12GB](https://www.techpowerup.com/gpu-specs/geforce-rtx-3060-12-gb.c3682) | 12 GB    | 12.74 TFLOPS | 12.74 TFLOPS | 170 W   | ~8–12 W        | 360 GB/s      | ❌                  |
| [RTX 3060 Ti](https://www.techpowerup.com/gpu-specs/geforce-rtx-3060-ti.c3681)      | 8 GB     | 16.20 TFLOPS | 16.20 TFLOPS | 200 W   | ~10–15 W       | 448 GB/s      | ❌                  |
| [RTX 3070](https://www.techpowerup.com/gpu-specs/geforce-rtx-3070.c3674)            | 8 GB     | 20.31 TFLOPS | 20.31 TFLOPS | 220 W   | ~9–15 W        | 448 GB/s      | ❌                  |
| [RTX 3080](https://www.techpowerup.com/gpu-specs/geforce-rtx-3080.c3621)            | 10 GB    | 29.77 TFLOPS | 29.77 TFLOPS | 320 W   | ~9–15 W        | 760 GB/s      | ❌                  |
| [RTX 3080 Ti](https://www.techpowerup.com/gpu-specs/geforce-rtx-3080-ti.c3735)      | 12 GB    | 34.10 TFLOPS | 34.10 TFLOPS | 350 W   | ~12–16 W       | 912 GB/s      | ❌                  |
| [RTX 3090](https://www.techpowerup.com/gpu-specs/geforce-rtx-3090.c3622)            | 24 GB    | 35.58 TFLOPS | 35.58 TFLOPS | 350 W   | ~15–20 W       | 936 GB/s      | ❌                  |

## NVIDIA RTX 40 Series (Ada Lovelace)

| GPU | CUDA | VRAM | FP32 | FP16 | TDP | Idle | Virtualization |
|-----|------|------|------|------|-----|------|----------------|
| [RTX 4060](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060.c4107) | 3072 | 8GB GDDR6 128-bit | 15.1 TF | 15.1 TF | 115W | ~7W | ❌ |
| [RTX 4060 Ti 8GB](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060-ti-8-gb.c4106) | 4352 | 8GB GDDR6 128-bit | 22.1 TF | 22.1 TF | 160W | ~8W | ❌ |
| [RTX 4060 Ti 16GB](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060-ti-16-gb.c4155) | 4352 | 16GB GDDR6 128-bit | 22.1 TF | 22.1 TF | 165W | ~8W | ❌ |
| [RTX 4070](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070.c3924) | 5888 | 12GB GDDR6X 192-bit | 29.1 TF | 29.1 TF | 200W | ~10W | ❌ |
| [RTX 4070 Super](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070-super.c4165) | 7168 | 12GB GDDR6X 192-bit | 35.5 TF | 35.5 TF | 220W | ~10W | ❌ |
| [RTX 4070 Ti](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070-ti.c3950) | 7680 | 12GB GDDR6X 192-bit | 40.1 TF | 40.1 TF | 285W | ~11W | ❌ |
| [RTX 4080](https://www.techpowerup.com/gpu-specs/geforce-rtx-4080.c3888) | 9728 | 16GB GDDR6X 256-bit | 48.7 TF | 48.7 TF | 320W | ~13W | ❌ |
| [RTX 4090](https://www.techpowerup.com/gpu-specs/geforce-rtx-4090.c3889) | 16384 | 24GB GDDR6X 384-bit | 82.6 TF | 82.6 TF | 450W | ~16W | ❌ |

## NVIDIA RTX 50 Series (Blackwell)

| GPU | CUDA | VRAM | FP32 | FP16 | TDP | Idle | Virtualization |
|-----|------|------|------|------|-----|------|----------------|
| [RTX 5050](https://www.techpowerup.com/gpu-specs/geforce-rtx-5050.c4220) | 2560   | 8GB GDDR6 128-bit  | 13.17 TFLOPS | 13.17 TFLOPS | 130W  | ~12W | ❌             |
| [RTX 5060](https://www.techpowerup.com/gpu-specs/geforce-rtx-5060.c4219) | 3840  | 8GB GDDR7 128-bit  | 19.18 TFLOPS  | 19.18 TFLOPS | 145W  | ~13W | ❌             |
| [RTX 5070](https://www.techpowerup.com/gpu-specs/geforce-rtx-5070.c4218) | 6144  | 12GB GDDR7 256-bit  | 30.87 TFLOPS | 30.87 TFLOPS | 250W  | ~14W | ❌             |
| [RTX 5080](https://www.techpowerup.com/gpu-specs/geforce-rtx-5080.c4190) | 10752 | 16GB GDDR7 256-bit | 56.28 TFLOPS | 56.28 TFLOPS | 360W | ~15W | ❌ |
| [RTX 5090](https://www.techpowerup.com/gpu-specs/geforce-rtx-5090.c4189) | 21760 | 32GB GDDR7 512-bit | 104.8 TFLOPS | 104.8 TFLOPS | 575W | ~20W | ❌ |

## NVIDIA Quadro / Professional GPUs

| GPU | VRAM | FP16 (half) | FP32 (float) | TDP | Idle Power (typical) | Bandwidth | Virtualization |
|-----|------|-------------|--------------|------|----------------------|-----------|----------------|
| [Quadro P5000](https://www.techpowerup.com/gpu-specs/quadro-p5000.c2864) | 16GB | 138.6 GFLOPS | 8.873 TFLOPS  | 180W | ~15–20W | (256-bit GDDR5X) | ✅ |
| [Quadro P6000](https://www.techpowerup.com/gpu-specs/quadro-p6000.c2865) | 24GB | 197 GFLOPS | 12.63 TFLOPS | 250W | ~20–25W | 432.8 GB/s | ✅ |
| [Quadro GP100](https://www.techpowerup.com/gpu-specs/quadro-gp100.c2994) | 16GB | 20.69 TFLOPS | 10.34 TFLOPS | 235W | ~25–30W | 732.2 GB/s | ✅ |
| [Quadro GV100](https://www.techpowerup.com/gpu-specs/quadro-gv100.c3066) | 32GB HBM2 | 33.32 TFLOPS | 16.66 TFLOPS | 250W | ~25–30W | 868.4 GB/s | ✅ |
| [Quadro RTX 6000](https://www.techpowerup.com/gpu-specs/quadro-rtx-6000.c3307) | 24GB GDDR6 | 32.62 TFLOPS | 16.31 TFLOPS | 260W | ~22–30W | 672.0 GB/s | ✅ |

## NVIDIA RTX A-Series (Professional GPUs)

| GPU                                                                             | VRAM       | FP16 (half)  | FP32 (float) | TDP  | Idle Power (typical) | Bandwidth | Virtualization |
| ------------------------------------------------------------------------------- | ---------- | ------------ | ------------ | ---- | -------------------- | --------- | -------------- |
| [RTX A2000](https://www.techpowerup.com/gpu-specs/rtx-a2000.c3820)              | 6GB GDDR6  | 7.987 TFLOPS | 7.987 TFLOPS | 70W  | ~7–10W               | 288 GB/s  | ✅              |
| [RTX A2000 (12GB)](https://www.techpowerup.com/gpu-specs/rtx-a2000-12-gb.c3853) | 12GB GDDR6 | 7.987 TFLOPS | 7.987 TFLOPS | 70W  | ~7–10W               | 288 GB/s  | ✅              |
| [RTX A4500](https://www.techpowerup.com/gpu-specs/rtx-a4500.c3849)              | 20GB GDDR6 | 23.65 TFLOPS | 23.65 TFLOPS | 200W | ~13–18W              | 640 GB/s  | ✅              |
| [RTX A5000](https://www.techpowerup.com/gpu-specs/rtx-a5000.c3748)              | 24GB GDDR6 | 27.77 TFLOPS | 27.77 TFLOPS | 230W | ~10–20W              | 768 GB/s  | ✅              |
| [RTX A6000](https://www.techpowerup.com/gpu-specs/rtx-a6000.c3686)              | 48GB GDDR6 | 38.71 TFLOPS | 38.71 TFLOPS | 300W | ~8–12W               | 768 GB/s  | ✅              |



## NVIDIA Tesla Series

| GPU | VRAM | FP16 (half) | FP32 (float) | TDP | Idle Power (typical) | Bandwidth | Virtualization |
|-----|------|-------------|--------------|------|----------------------|-----------|----------------|
| [Tesla P4](https://www.techpowerup.com/gpu-specs/tesla-p4.c2879) | 8GB | 89.12 GFLOPS | 5.704 TFLOPS | 75W | ~6–10W (idle proxmox/vgpu case) | 192.3 GB/s | ✅ |
| [Tesla P40](https://www.techpowerup.com/gpu-specs/tesla-p40.c2878) | 24GB | 183.7 GFLOPS | 11.76 TFLOPS | 250W | ~9–12W (reported idle) | 384-bit GDDR5 | ✅ |
| [Tesla P100 PCIe 12GB](https://www.techpowerup.com/gpu-specs/tesla-p100-pcie-12-gb.c2915) | 12GB HBM2 | 19.05 TFLOPS (2:1) | 9.526 TFLOPS | 250W | ~25–27W | 549.1 GB/s | ✅ |
| [Tesla P100 SXM2 16GB](https://www.techpowerup.com/gpu-specs/tesla-p100-sxm2.c3183) | 16GB HBM2 | 21.22 TFLOPS | 10.61 TFLOPS | 300W | ~25–30W | 732.2 GB/s | ✅ |
| [Tesla V100 PCIe 16GB](https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-16-gb.c2957) | 16GB HBM2 | 28.26 TFLOPS | 14.13 TFLOPS | 300W | ~20–30W | 897.0 GB/s | ✅ |
| [Tesla V100 PCIe 32GB](https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-32-gb.c3184) | 32GB HBM2 | ~28.26 TFLOPS | ~14.13 TFLOPS | 300W | ~20–30W | 897.0 GB/s | ✅ |
| [Tesla T4](https://www.techpowerup.com/gpu-specs/tesla-t4.c3316) | 16GB | 65.13 TFLOPS (8:1) | 8.141 TFLOPS | 70W | ~8–12W | 320.0 GB/s | ✅ |
| [Tesla L4](https://www.techpowerup.com/gpu-specs/l4.c4091) | 24GB | 30.29 TFLOPS (1:1) | 30.29 TFLOPS | 72W | ~8–12W | 192.3 GB/s | ✅ |

## AMD Radeon RX 5000 Series (RDNA1)

| GPU | VRAM | FP32 | FP16 | TDP | Idle (Typical) | Bandwidth | Virtualization |
|-----|------|------|------|-----|----------------|-----------|----------------|
| [Radeon RX 5500](https://www.techpowerup.com/gpu-specs/radeon-rx-5500.c3455) | 4GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 110W | ~5–8W | 224 GB/s | ❌ |
| [Radeon RX 5500 XT 4GB](https://www.techpowerup.com/gpu-specs/radeon-rx-5500-xt.c3468) | 4GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 130W | ~6–10W | 224 GB/s | ❌ |
| [Radeon RX 5500 XT 8GB](https://www.techpowerup.com/gpu-specs/radeon-rx-5500-xt-8-gb.c3499) | 8GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 130W | ~6–10W | 224 GB/s | ❌ |
| [Radeon RX 5600 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-5600-xt.c3474) | 6GB GDDR6 192-bit | 7.19 TFLOPS | 14.38 TFLOPS | 150W | ~8–12W | 288 GB/s | ❌ |
| [Radeon RX 5700](https://www.techpowerup.com/gpu-specs/radeon-rx-5700.c3437) | 8GB GDDR6 256-bit | 7.95 TFLOPS | 15.90 TFLOPS | 180W | ~10–15W | 448 GB/s | ❌ |
| [Radeon RX 5700 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-5700-xt.c3339) | 8GB GDDR6 256-bit | 9.75 TFLOPS | 19.50 TFLOPS | 225W | ~12–18W | 448 GB/s | ❌ |

## AMD Radeon RX 6000 Series (RDNA2)

| GPU | VRAM | FP32 | FP16 | TDP | Idle (Typical) | Bandwidth | Virtualization |
|-----|------|------|------|-----|----------------|-----------|----------------|
| [Radeon RX 6500 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6500-xt.c3850) | 4GB GDDR6 64-bit | 5.77 TFLOPS | 11.54 TFLOPS | 107W | ~5–8W | 144 GB/s | ❌ |
| [Radeon RX 6600](https://www.techpowerup.com/gpu-specs/radeon-rx-6600.c3696) | 8GB GDDR6 128-bit | 8.93 TFLOPS | 17.86 TFLOPS | 132W | ~6–10W | 224 GB/s | ❌ |
| [Radeon RX 6600 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6600-xt.c3774) | 8GB GDDR6 128-bit | 10.60 TFLOPS | 21.20 TFLOPS | 160W | ~7–12W | 256 GB/s | ❌ |
| [Radeon RX 6650 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6650-xt.c3898) | 8GB GDDR6 128-bit | 10.79 TFLOPS | 21.58 TFLOPS | 176W | ~7–12W | 280 GB/s | ❌ |
| [Radeon RX 6700](https://www.techpowerup.com/gpu-specs/radeon-rx-6700.c3716) | 10GB GDDR6 160-bit | 10.37 TFLOPS | 20.74 TFLOPS | 175W | ~10–15W | 320 GB/s | ❌ |
| [Radeon RX 6700 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6700-xt.c3695) | 12GB GDDR6 192-bit | 13.21 TFLOPS | 26.42 TFLOPS | 230W | ~12–18W | 384 GB/s | ❌ |
| [Radeon RX 6750 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6750-xt.c3899) | 12GB GDDR6 192-bit | 13.31 TFLOPS | 26.62 TFLOPS | 250W | ~12–18W | 432 GB/s | ❌ |
| [Radeon RX 6800](https://www.techpowerup.com/gpu-specs/radeon-rx-6800.c3713) | 16GB GDDR6 256-bit | 16.17 TFLOPS | 32.34 TFLOPS | 250W | ~15–22W | 512 GB/s | ❌ |
| [Radeon RX 6800 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6800-xt.c3694) | 16GB GDDR6 256-bit | 20.74 TFLOPS | 41.48 TFLOPS | 300W | ~15–25W | 512 GB/s | ❌ |
| [Radeon RX 6900 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6900-xt.c3693) | 16GB GDDR6 256-bit | 23.04 TFLOPS | 46.08 TFLOPS | 300W | ~18–28W | 512 GB/s | ❌ |
| [Radeon RX 6950 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6950-xt.c3897) | 16GB GDDR6 256-bit | 23.65 TFLOPS | 47.30 TFLOPS | 335W | ~18–30W | 576 GB/s | ❌ |

## AMD Radeon RX 7000 Series (RDNA3)

| GPU | VRAM | FP32 | FP16 | TDP | Idle (Typical) | Bandwidth | Virtualization |
|-----|------|------|------|-----|----------------|-----------|----------------|
| [Radeon RX 7600](https://www.techpowerup.com/gpu-specs/radeon-rx-7600.c4153) | 8GB GDDR6 128-bit | 21.75 TFLOPS | 43.50 TFLOPS | 165W | ~7–12W | 288 GB/s | ❌ |
| [Radeon RX 7600 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7600-xt.c4198) | 16GB GDDR6 128-bit | 22.57 TFLOPS | 45.14 TFLOPS | 190W | ~8–14W | 288 GB/s | ❌ |
| [Radeon RX 7700 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7700-xt.c3911) | 12GB GDDR6 192-bit | 35.17 TFLOPS | 70.34 TFLOPS | 245W | ~15–22W | 432 GB/s | ❌ |
| [Radeon RX 7800 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7800-xt.c3839) | 16GB GDDR6 256-bit | 37.32 TFLOPS | 74.64 TFLOPS | 263W | ~18–25W | 624 GB/s | ❌ |
| [Radeon RX 7900 GRE](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-gre.c4156) | 16GB GDDR6 256-bit | 40.35 TFLOPS | 80.70 TFLOPS | 260W | ~18–25W | 576 GB/s | ❌ |
| [Radeon RX 7900 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xt.c3912) | 20GB GDDR6 320-bit | 51.48 TFLOPS | 102.96 TFLOPS | 300W | ~20–30W | 800 GB/s | ❌ |
| [Radeon RX 7900 XTX](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xtx.c3941) | 24GB GDDR6 384-bit | 61.39 TFLOPS | 122.78 TFLOPS | 355W | ~20–35W* | 960 GB/s | ❌ |

## AMD Radeon RX 9000 Series (RDNA4)

| GPU | VRAM | FP16 (half) | FP32 (float) | TDP | Idle Power (typical) | Bandwidth | Virtualization |
|-----|------|-------------|--------------|------|----------------------|-----------|----------------|
| [AMD Radeon RX 9600](https://www.techpowerup.com/gpu-specs/radeon-rx-9060.c4326) | 8GB GDDR6 | ~42.9 TFLOPS | ~21.4 TFLOPS | ~132W | ~10–15W | 288 GB/s | ❌ |
| [AMD Radeon RX 9060 XT 8GB](https://www.techpowerup.com/gpu-specs/radeon-rx-9060-xt-8-gb.c4251) | 8GB GDDR6 | 51.3 TFLOPS | 25.6 TFLOPS | 150W | ~12–18W | 320 GB/s | ❌ |
| [AMD Radeon RX 9060 XT 16GB](https://www.techpowerup.com/gpu-specs/radeon-rx-9060-xt-16-gb.c4293) | 16GB GDDR6 | 51.3 TFLOPS | 25.6 TFLOPS | 160W | ~12–18W | 320 GB/s | ❌ |
| [AMD Radeon RX 9070](https://www.techpowerup.com/gpu-specs/radeon-rx-9070.c4250) | 16GB GDDR6 | 72.25 TFLOPS | 36.13 TFLOPS | 220W | ~18–28W | ~640–896 GB/s | ❌ |
| [AMD Radeon RX 9070 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-9070-xt.c4229) | 16GB GDDR6 | 97.32 TFLOPS | 48.66 TFLOPS  | 260–304W | ~20–30W | 640 GB/s+ | ❌ |


## AMD Pro/Compute GPUs

| GPU | VRAM | FP16 (half) | FP32 (float) | TDP | Idle Power (typical) | Bandwidth | Virtualization |
|-----|------|-------------|--------------|------|----------------------|------------|----------------|
| [Radeon Instinct MI25](https://www.techpowerup.com/gpu-specs/radeon-instinct-mi25.c2983) | 16GB HBM2 | 24.58 TFLOPS | 12.29 TFLOPS | 300W | ~30–40W | 436.2 GB/s | 🟡 |

<hr>

### Suggested OS:

<a href="https://www.proxmox.com/en/" target="_blank">Proxmox</a>

### Proxmox related content:
Additional Resources:
<br><a href="https://community-scripts.github.io/ProxmoxVE/" target="_blank">Proxmox VE Helper scripts</a> - Hundreds of scripts to quickly setup a wide range of projects on proxmox.
<br><a href="https://github.com/MacRimi/ProxMenux" target="_blank">ProxMenux</a> - Seperate Dashboard / CLI menu with more information & management options handy for proxmox management.
<br>VMs:
<br><a href="https://github.com/kholia/OSX-KVM" target="_blank">OSX-KVM</a> - Mac OSX (multiple versions to choose from) On Proxmox. 

### Filesystems:

### [XFS vs EXT4: Which Linux File System Is Better?](https://blog.purestorage.com/purely-educational/xfs-vs-ext4-which-linux-file-system-is-better/)  
Beyond what is covered in the article:

- **XFS**: In my experience, XFS is more reliable for long-term data storage. I’ve lost files to long-term storage on EXT4, particularly media files, so for that purpose, **XFS** is preferred.  
- **EXT4**: For operating system disks (e.g., laptop), EXT4 works well. However, EXT4 has a space reservation system (typically 5%), which means you automatically lose a chunk of disk space as the disk size grows. **XFS**, on the other hand, doesn’t reserve space, so you can fill it more efficiently.

> **Note**: Avoid using XFS on top of XFS in virtual machines (VMs). It doesn’t nest/stack well. Instead, use **EXT4** on top of XFS if you need to stack file systems.

---

### **ZFS - The Zettabyte File System**
[What is ZFS?](https://itsfoss.com/what-is-zfs/)

ZFS is a robust and highly reliable file system with several advanced features:

- **Compression**: Supports 1z4, gzip, zstd, and more.
- **Deduplication**: Requires significant memory and RAID setups for optimal performance.
- **Self-healing RAID**: Uses hashing and is self-healing in RAID configurations.
- **Copy-on-write (CoW) Verification**: Files are verified before being written to disk and every time they are read, with various checksum options.
- **Scalability**: Scales incredibly well, ideal for large datasets.
- **Raw Filesystems**: Allows VM disks to be written directly into the filesystem, functioning like containers.
- **Live VM Copying**: Can copy live virtual machines.
- **Superior Performance Potential**: Can deliver high-performance results when properly configured.
- **Advanced Configurations**: Offers complex options for highly specific use cases.

---

### **Performance & Usage Considerations for ZFS**

ZFS is extremely reliable, especially in RAID environments with at least 2+ disks. However, if performance isn’t critical, it can work well on a single disk, though it may be slower and require more RAM. 

ZFS is made for data centers, and has a steep learning curve, but its extensive features make it a solid choice for advanced users.

---

### **BTRFS as an Alternative to ZFS**
[BTRFS Overview](https://www.maketecheasier.com/what-is-btrfs/)

BTRFS offers some similar features to ZFS, such as hash support and ZSTD compression, but it is generally less reliable. It’s easier to use compared to ZFS, but for certain use cases, it may not be as dependable.

For example, a large number of small file writes can cause BTRFS to crash, leading to potential data loss (e.g., for databases, torrents, or VMs). Although BTRFS is a copy-on-write system, it’s not as robust as ZFS.

---

### **BTRFS Use Case Example**  
In testing, I ran a Ubuntu VM with BTRFS and compressed roughly 5.5GB of OS files down to 2.8GB using ZSTD compression (level 9 specified in the **/etc/fstab** configuration).  

- **ZSTD Compression**:  
  - **Optimal Levels**: Use ZSTD level 3 or higher for meaningful compression. Levels 9-11 increase compression time exponentially with minimal benefits.  
  - **Recommended Levels**: A level of 5-7 provides a good balance between performance and compression ratio.

---

### **Using These Filesystems with Proxmox**

All these filesystems (XFS, ZFS, and BTRFS) can be utilized on **Proxmox**, a homelab virtualization server platform.

<hr>

## Useful Software:

### Awesome Lists:

- [Curated List of Awesome Lists](https://project-awesome.org/) - A collection of curated "awesome" lists covering a wide variety of topics, providing valuable resources and tools for almost every field of interest.
- [Awesome Programs and Tweaks for Windows, macOS, and Linux](https://github.com/alfaaarex/awesome-tweaks) - A curated collection of programs and tweaks to enhance the functionality, performance, and usability of Windows, macOS, and Linux systems.
- [Awesome List of Windows Software](https://github.com/0PandaDEV/awesome-windows) - A curated list of useful and essential software for Windows users, covering a wide range of categories and needs.
- [Awesome List of Linux Software](https://github.com/luong-komorebi/Awesome-Linux-Software) - A comprehensive list of open-source software and tools for Linux users, including productivity, development, and system management applications.
- [Awesome List of macOS Software](https://github.com/iCHAIT/awesome-macOS) - A curated collection of software and tools for macOS, ranging from productivity applications to development utilities and system enhancements.
- [Awesome Privacy](https://github.com/pluja/awesome-privacy) - A curated collection of privacy-focused software and tools designed to enhance your online and offline privacy and security.
- [Awesome Piracy](https://github.com/genesis-kbm/awesome-piracy-fixed) - A curated list of resources and tools related to piracy, including websites, software, and services for accessing pirated content.

### RDP:
- [Apollo Sunshine fork](https://github.com/ClassicOldSong/Apollo)  
- [Original Sunshine](https://github.com/LizardByte/Sunshine)  
- [Moonlight](https://github.com/moonlight-stream)  
- Windows: [BetterRDP for Windows](https://github.com/Upinel/BetterRDP) - Enables 60fps and GPU acceleration on RDP connections, creating a seamless and native-like experience for intensive or latency-dependent software, including games.

### Gaming:
- Windows: [RdpGamepad - a Remote Desktop Plugin for Xbox Gamepads](https://github.com/microsoft/RdpGamepad) - Use Xbox 360/One controllers over RDP/Moonlight/Sunshine.

### File Management:
- Windows: [SSHFS-Win Manager](https://github.com/evsar3/sshfs-win-manager) - A GUI for SSHFS on Windows.  
- Linux: [SSHFS](https://github.com/libfuse/sshfs).

### File Sharing:
- [croc](https://github.com/schollz/croc) - Easily and securely send files between computers.

### File Compression:

- [7-Zip](https://www.7-zip.org/) - A popular open-source file compression tool that supports various archive formats and offers high compression ratios.
- [7-Zip ZSTD](https://github.com/mcmilk/7-Zip-zstd) - A fork of 7-Zip that adds support for the Zstandard (ZSTD) compression algorithm, offering faster speeds and higher compression ratios.
- [Compactor](https://github.com/Freaky/Compactor) - A tool for compressing files and directories, designed for efficiency and easy use with high-quality compression techniques.
- [CompactGUI](https://github.com/IridiumIO/CompactGUI) - A graphical user interface for the Compact tool, which allows users to compress files and folders using the Windows built-in compression features.

### Caching:
- Windows: [Primo Cache](https://www.romexsoftware.com/en-us/primo-cache/).

### Firewall/Networking:
- Linux: [OpenSnitch](https://github.com/evilsocket/opensnitch) - Network monitoring and rule-based control.  
- Windows: [SimpleWall](https://github.com/henrypp/simplewall) - Windows firewall management and rules.  
- Mac: [LittleSnitch](https://www.obdev.at/products/littlesnitch/index.html) - Network monitoring and control.  
- Win/Linux: [Safing Portmaster](https://safing.io/download/).  
- Windows: [NetLimiter](https://www.netlimiter.com/) - Per-application bandwidth limits.

### Host Power Management:
- Linux: [PowerTop](https://github.com/fenrus75/powertop) - Tweak host for power savings.

### Media Conversion:

- [Hybrid](https://www.selur.de/) - A multi-purpose video conversion tool that integrates various encoders and applications, allowing easy media conversion from various formats.
- [HandBrake](https://handbrake.fr/) - A widely-used open-source video transcoder that supports GPU acceleration for faster encoding and includes support for modern codecs like AV1.

### Documents:

- [Recoll](https://www.recoll.org/index.html) - A powerful, open-source desktop search tool that can index and search the contents of various document formats. It supports a wide range of file types and is great for organizing and retrieving personal documents locally.

### Windows Tweaks & Privacy:

- [Windows 10/11 Optimization & Customization Guide](https://github.com/just-maik/win-opti-resources) - A comprehensive guide that helps optimize and customize Windows 10/11 for improved performance, privacy, and overall system experience.
- [Microsoft Edge Removal](https://github.com/ShadowWhisperer/Remove-MS-Edge) - A tool to fully remove Microsoft Edge from Windows, ensuring it is completely deleted and no longer part of your system.
- [OneDrive-Uninstaller](https://github.com/ionuttbara/one-drive-uninstaller) - A tool for completely uninstalling OneDrive from your system, preventing it from syncing and taking up system resources.
- [Dism++](https://github.com/Chuyu-Team/Dism-Multi-language) - A powerful system tool for managing Windows image files, providing options for system cleanup, privacy tweaks, and optimizations.
- [Blackbird](https://www.getblackbird.net/) - A privacy-focused tool that disables tracking, telemetry, and other unwanted data collection by Windows, offering enhanced privacy on your system.
- [10AntiSpy](https://www.majorgeeks.com/files/details/10antispy.html) - A privacy-focused tool for disabling unwanted Windows 10 features such as telemetry, Cortana, and other data collection mechanisms.
- [UWT4](https://www.majorgeeks.com/files/details/ultimate_windows_tweaker_for_windows_10.html) - A comprehensive tweak tool for Windows 10 that allows you to customize various system settings and privacy options, improving performance and security.
- [Win10BloatRemover](https://github.com/Fs00/Win10BloatRemover) - A tool that helps you remove bloatware and unwanted apps from Windows 10, freeing up space and improving system performance.
- [Intelligent Standby List Cleaner](https://www.majorgeeks.com/files/details/intelligent_standby_list_cleaner.html) - A tool to reduce system stuttering and improve performance by clearing the standby memory list, optimizing RAM usage.
- [Destroy Windows 10 Spying](https://www.majorgeeks.com/files/details/destroy_windows_10_spying.html) - A privacy tool designed to disable telemetry, tracking, and data collection features in Windows 10 for improved privacy and control.

### Windows 7:

- [Windows 7 ESU Patching](https://hackandpwn.com/windows-7-esu-patching/) - A guide for patching Windows 7 Extended Security Updates (ESU) to keep receiving updates and security patches after official support ends.
- [Windows 7 Service Pack 2](https://github.com/marie-systems/win7-sp2/tree/main) - A community-driven project to create an unofficial Windows 7 Service Pack 2, adding new features, bug fixes, and improvements to Windows 7.
- [Windows 7 SP4 Unofficial](https://github.com/LemonSqueezers/W7SP4) - An unofficial Service Pack 4 for Windows 7, designed to enhance the system with additional updates and fixes after the official support ended.
- [Windows-7 on Modern Hardware](https://github.com/wortkraecker/Windows-7-on-modern-hardware) - A guide for installing and running Windows 7 on modern hardware, with advice on drivers, patches, and compatibility tweaks.
- [Windows 7 Fan-Made Survival Guide](https://github.com/kuba2k2/i-use-win7-btw) - A fan-made survival guide for using Windows 7 in the modern era, offering tips, tweaks, and tools to keep Windows 7 functional and secure.

### Linux Filesystems on Windows:

- [WinBtrfs](https://github.com/maharmstone/btrfs) - A Windows driver for the Btrfs filesystem, allowing access to Btrfs partitions and data from a Windows environment.
- [OpenZFS on Windows](https://github.com/openzfsonwindows/openzfs) - A project to bring OpenZFS support to Windows, enabling ZFS filesystems to be used on Windows systems.
- [EXT4 for Win](https://www.paragon-software.com/home/linuxfs-windows/) - A driver for accessing EXT4 partitions on Windows, offering full read/write support for EXT4-formatted drives.

**Warning:**
These drivers are experimental and may not be stable. There is a risk of data corruption, crashes, or other issues when using Linux filesystems on Windows. It is highly recommended to use these tools only with backup copies of your important data, and avoid using them for critical or production environments.

<hr>

### SelfHosted:
- [Awesome-Selfhosted](https://github.com/awesome-selfhosted/awesome-selfhosted).

### Audiobooks & Podcasts:

- [Audiobookshelf](https://github.com/advplyr/audiobookshelf) - An open-source self-hosted solution for managing and listening to audiobooks. It offers a clean interface and supports syncing across devices.

#### Audiobookshelf Apps:

- **Android App**: [Audiobookshelf Android App](https://github.com/advplyr/audiobookshelf-app) - An official Android app for accessing your Audiobookshelf library, providing seamless audiobook management and playback.
- **iOS Apps**:
    - [Audiobooth](https://github.com/AudioBooth/AudioBooth) - An iOS app for listening to audiobooks from Audiobookshelf. **Note**: Currently does not support podcasts.
    - [Plappa](https://plappa.me/) - A podcast app that integrates with Audiobookshelf, providing support for podcasts as well. **Note**: Can be glitchy and has heavy battery drain issues when managing large libraries, but podcasts work at least.

### AI:

- Text: [Ollama](https://github.com/ollama/ollama) - A tool to run LLMs (Large Language Models) on your own machine, enabling private and customizable AI instances.
- Images: [EasyDiffusion](https://github.com/easydiffusion/easydiffusion) - A user-friendly interface for running Stable Diffusion locally to generate high-quality images.
- Images: [Forge-WebUI](https://github.com/lllyasviel/stable-diffusion-webui-forge) - A web-based interface for managing and controlling AI model deployments on your own server.
- multi: [Koboldcpp](https://github.com/LostRuins/koboldcpp) - KoboldCpp is an easy-to-use AI text-generation software for GGML and GGUF models, inspired by the original KoboldAI. 
- TTS: [Kokoro FastAPI](https://github.com/remsky/Kokoro-FastAPI) - A Text-to-Speech service built with FastAPI, allowing fast and efficient text-to-speech conversion using AI models.
- DeepResearch: [Local Deep Research](https://github.com/LearningCircuit/local-deep-research) - Local Deep Research achieves ~95% on SimpleQA benchmark (tested with GPT-4.1-mini). Supports local and cloud LLMs (Ollama, Google, Anthropic, ...). Searches 10+ sources - arXiv, PubMed, web, and your private documents. Everything Local & Encrypted. 

### Media Streaming:

- [Jellyfin](https://jellyfin.org/) - An open-source media server for managing and streaming your media content to various devices.
- [Plex](https://www.plex.tv/) - A media server platform that allows you to stream and organize your media collection from your own server.
- [Emby](https://emby.media/) - Another media server platform, offering advanced features for content management and streaming.
- [seerr](https://github.com/seerr-team/seerr) - free and open source software application for managing requests for your media library. It integrates with the media server of your choice: Jellyfin, Plex, and Emby. In addition, it integrates with your existing services, such as Sonarr, Radarr.
- [Radarr](https://github.com/Radarr/Radarr) - An automatic movie collection manager that works with your media server for a seamless experience.
- [Sonarr](https://github.com/Sonarr/Sonarr) - A TV series manager for downloading, organizing, and streaming your favorite shows automatically.
- [Tautulli](https://github.com/Tautulli/Tautulli) - A monitoring tool for your Plex server, providing detailed analytics and statistics on your media server's usage.

### Documents:

- [Ubooquity](https://vaemendis.net/ubooquity/) - A lightweight and easy-to-use home server for managing and streaming eBooks and comics. Ideal for personal digital libraries.
- [OpenReader-WebUI](https://github.com/richardr1126/OpenReader-WebUI) - Read documents in realtime with high-quality TTS; or extract audiobooks. Use your own Kokoro-FastAPI, Deepinfa API, or Open AI API endpoint. .

### Media Conversion:

- [Tdarr](https://home.tdarr.io/) - A distributed media transcoding system designed to automate and optimize the conversion of your media collection, running on your own server.

### Metasearch Engines:

- [SearXNG](https://github.com/searxng/searxng) - SearXNG is a free internet metasearch engine which aggregates results from various search services and databases. Users are neither tracked nor profiled.

### Virus Scanners:

- [Malice](https://github.com/maliceio/malice) - Malice's mission is to be a free open source version of VirusTotal that anyone can use at any scale from an independent researcher to a fortune 500 company. (officially archived but still worth a mention.) 


