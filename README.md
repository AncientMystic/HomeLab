# HomeLab
HomeLab CheatSheet &amp; AwesomeList
<br> Created for the [HomeLab Group](https://smp6.simplex.im/g#P45YjyWy-__e3p3OqoRvU_4sjcSorUz0v8hCtWEPRtk) on Simplex Chat [![Simplex Chat](https://avatars.githubusercontent.com/u/59927747?s=48&v=4)](https://simplex.chat/)
<br>
<br> The goal of this repo is to become your map to help you navigate the HomeLabbing experience. 
<br> This page will be updated randomly with new information, so stay tuned. (contributions welcome!)
<br>
<br> Note: many of the hardware suggestions here are mostly the best items in their class for the lowest prices. 
<br> Hardware tables have average used prices from ebay.com as of 2/17/2026 
<br>
<br>ToDo: 
- Update table of contents... :white_check_mark:
- Add CPU Tables 
- Add more hardware information including more Nic models / HBA models / Enterprise drive models and information. 
- Add more general filesystem information / ZFS information / tips with more links to obscure useful information that will help manage ZFS better.  
- Add more software/Self hosting options and guide links. 
- Add more proxmox related information and helpful guides, including those related to GPU passthrough, LXCs, etc 
# Table of Contents
- [HomeLab](#homelab)
  - [Optimal Minimal Setup Device: Lenovo Tiny PCs](#optimal-minimal-setup-device-lenovo-tiny-pcs)
    - [Hardware Configuration Options](#hardware-configuration-options)
    - [Popular Uses for the PCIe Slot](#popular-uses-for-the-pcie-slot)
    - [Power and Performance](#power-and-performance)
    - [Why Lenovo Tiny PCs](#why-lenovo-tiny-pcs)
    - [SFF Suggestion](#sff-suggestion)
    - [NIC](#nic)
    - [SAS / HBA cards](#sas--hba-cards)
    - [Enterprise SATA/SAS HDDs](#enterprise-satasas-hdds)
    - [SSD/Nvme Drives](#ssdnvme-drives)

- [Enterprise NVMe / M.2 Drives with Endurance](#enterprise-nvme--m2-drives-with-endurance)
- [Consumer NVMe / M.2 Drives](#consumer-nvme--m2-drives)
  - [Consumer vs. Enterprise Price Comparison](#consumer-vs-enterprise-price-comparison)
    - [CPU](#cpu)
    - [Disable Turbo Boost](#disable-turbo-boost)

- [Turbo Boost – Power, Heat & How to Disable It](#turbo-boost--power-heat--how-to-disable-it)
  - [Disabling Turbo Boost in BIOS (Recommended Method)](#1-disabling-turbo-boost-in-bios-recommended-method)
    - [Steps](#steps)
  - [Disabling Turbo Boost on Linux](#2-disabling-turbo-boost-on-linux)
    - [Method A — Using rc.local](#method-a--using-rclocal)
    - [Method B — Using intel-noturbo](#method-b--using-intel-noturbo)
  - [Disabling Turbo Boost on Windows](#3-disabling-turbo-boost-on-windows)
  - [When Should You Disable Turbo](#when-should-you-disable-turbo)
    - [Turbo OFF is useful for](#turbo-off-is-useful-for)
  - [Power & Temperature Impact](#power--temperature-impact)
    - [GPU](#gpu)
    - [GPU Models to compare them side by side](#gpu-models-to-compare-them-side-by-side)

- [Intel GPU Master Table](#intel-gpu-master-table)
- [NVIDIA RTX 10 Series (Pascal)](#nvidia-rtx-10-series-pascal)
- [NVIDIA RTX 20 Series (Turing)](#nvidia-rtx-20-series-turing)
- [NVIDIA RTX 30 Series (Ampere)](#nvidia-rtx-30-series-ampere)
- [NVIDIA RTX 40 Series (Ada Lovelace)](#nvidia-rtx-40-series-ada-lovelace)
- [NVIDIA RTX 50 Series (Blackwell)](#nvidia-rtx-50-series-blackwell)
- [NVIDIA Quadro / Professional GPUs](#nvidia-quadro--professional-gpus)
- [NVIDIA RTX A-Series (Professional GPUs)](#nvidia-rtx-a-series-professional-gpus)
- [NVIDIA Tesla Series](#nvidia-tesla-series)
- [AMD Radeon RX 5000 Series (RDNA1)](#amd-radeon-rx-5000-series-rdna1)
- [AMD Radeon RX 6000 Series (RDNA2)](#amd-radeon-rx-6000-series-rdna2)
- [AMD Radeon RX 7000 Series (RDNA3)](#amd-radeon-rx-7000-series-rdna3)
- [AMD Radeon RX 9000 Series (RDNA4)](#amd-radeon-rx-9000-series-rdna4)
- [AMD Pro/Compute GPUs](#amd-procompute-gpus)

  - [Suggested OS](#suggested-os)
  - [Proxmox related content](#proxmox-related-content)
  - [Filesystems](#filesystems)
  - [XFS vs EXT4: Which Linux File System Is Better?](#xfs-vs-ext4-which-linux-file-system-is-better)
  - [ZFS - The Zettabyte File System](#zfs---the-zettabyte-file-system)
  - [Performance & Usage Considerations for ZFS](#performance--usage-considerations-for-zfs)
  - [BTRFS as an Alternative to ZFS](#btrfs-as-an-alternative-to-zfs)
  - [BTRFS Use Case Example](#btrfs-use-case-example)
  - [Using These Filesystems with Proxmox](#using-these-filesystems-with-proxmox)

- [Useful Software](#useful-software)
  - [Awesome Lists](#awesome-lists)
  - [RDP](#rdp)
  - [Gaming](#gaming)
  - [File Management](#file-management)
  - [File Sharing](#file-sharing)
  - [File Compression](#file-compression)
  - [Caching](#caching)
  - [Firewall/Networking](#firewallnetworking)
  - [Host Power Management](#host-power-management)
  - [Media Conversion](#media-conversion)
  - [Documents](#documents)
  - [Windows Tweaks & Privacy](#windows-tweaks--privacy)
  - [Windows 7](#windows-7)
  - [Linux Filesystems on Windows](#linux-filesystems-on-windows)
  - [SelfHosted](#selfhosted)
  - [Audiobooks & Podcasts](#audiobooks--podcasts)
    - [Audiobookshelf Apps](#audiobookshelf-apps)
  - [AI](#ai)
  - [Media Streaming](#media-streaming)
  - [Documents (Duplicate Section)](#documents--1)
  - [Media Conversion (Duplicate Section)](#media-conversion--1)
  - [Metasearch Engines](#metasearch-engines)
  - [Virus Scanners](#virus-scanners)

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

*Clarification*: measured system idle depends on CPU model, storage devices, NICs, and OS power settings — expect higher real-world idle (typ. 8–20W for common configs). Use a real watt-meter to confirm.

These devices are small, powerful, and make perfect all-in-one mini servers for various use cases. The **Intel** versions even allow you to share the **iGPU** with **Proxmox** for multiple virtual machines.

---

### Why Lenovo Tiny PCs?

Other mini PCs and SFF PCs can be worthwhile, but personally, I find the Lenovo Tiny PCs to be the most optimal, cost-effective options for home labs and other small-scale setups.

| Model                                                                                                                                                             | CPU                                                                                                                                                                                                                                                                                                  | Cores / Threads    | Passmark CPU Bench                                                                                                                                                   | RAM Max | Drives / NVMe Slots | PCIe Slot              | iGPU          | Quick Sync | Idle Power* | Power (TDP) | Year | Best Use Case                                      | **Avg Used eBay.com Price (≈)**                                                                                           |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------- | ------------------- | ---------------------- | ------------- | ---------- | ----------- | ----------- | ---- | -------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **ThinkCentre M715q Gen2**                                                                                                                                        | [Ryzen 5 2400GE](https://www.hacktiny.com/wp-content/uploads/2019/09/M920x-Tiny.pdf)                                                                                                                                                                                                                 | 4C / 8T            | [7192](https://www.cpubenchmark.net/cpu.php?cpu=AMD+Ryzen+5+2400GE)                                                                                                  | 32GB    | 1x 2.5" / 1x M.2    | None                   | Vega 11       | N/A        | ~7–10W      | 35W         | 2018 | Budget NAS, light Proxmox                          | **~$80 – $140** – common used M715q listings on eBay.com include Ryzen 5 / Ryzen Pro units around this range. ([eBay][1]) |
| **ThinkCentre M720Q**                                                                                                                                             | [i5-8400T](https://www.intel.com/content/www/us/en/products/sku/129940/intel-core-i58400t-processor-9m-cache-up-to-3-30-ghz/specifications.html) / [i7-8700T](https://www.intel.com/content/www/us/en/products/sku/129948/intel-core-i78700t-processor-12m-cache-up-to-4-00-ghz/specifications.html) | 6C / 6T – 6C / 12T | [7419](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-8400T+%40+1.70GHz) / [10225](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-8700T+%40+2.40GHz) | 32GB    | 1x 2.5" / 1x M.2    | 1x PCIe 3.0 x8 (riser) | Intel UHD 630 | Gen9.5     | ~8–12W      | 35W         | 2018 | NAS, Network appliance, media server, Proxmox host | **~$120 – $200** – based on midspec ThinkCentre Tiny used listings (i5/i7 options). ([eBay][1])                           |
| **ThinkCentre M920q**                                                                                                                                             | [i5-8400T](https://www.intel.com/content/www/us/en/products/sku/129940/intel-core-i58400t-processor-9m-cache-up-to-3-30-ghz/specifications.html) / [i7-8700T](https://www.intel.com/content/www/us/en/products/sku/129948/intel-core-i78700t-processor-12m-cache-up-to-4-00-ghz/specifications.html) | 6C / 6T – 6C / 12T | [7419](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-8400T+%40+1.70GHz) / [10225](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-8700T+%40+2.40GHz) | 32GB    | 1x 2.5" / 1x M.2    | 1x PCIe 3.0 x8 (riser) | Intel UHD 630 | Gen9.5     | ~8–12W      | 35W         | 2018 | Same as M720Q + vPro enterprise features           | **~$140 – $230** – slightly higher than M720Q used listings. ([eBay][1])                                                  |
| **[ThinkCentre M920x](https://www.hacktiny.com/wp-content/uploads/2019/09/M920x-Tiny.pdf)**                                                                       | [i5-9400T](https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html) / [i7-9700T](https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html) | 6C / 6T – 8C / 8T  | [8148](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz) / [10553](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz) | 32GB    | 2x M.2              | 1x PCIe 3.0 x8         | Intel UHD 630 | Gen9.5     | ~9–13W      | 35W         | 2019 | Dual NVMe NAS, serious homelab                     | **~$180 – $300** – typical for M920x used units with 2x NVMe capability. ([eBay][1])                                      |
| **[ThinkCentre P330](https://thinkstation-specs.com/wp-content/uploads/2019/09/P330-Tiny-Lenovo-ThinkStation.pdf)**                                               | [i5-9400T](https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html) / [i7-9700T](https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html) | 6C / 6T – 8C / 8T  | [8148](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz) / [10553](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz) | 64GB    | 2x M.2              | 1x PCIe 3.0 x8         | Intel UHD 630 | Gen9.5     | ~9–13W      | 35W         | 2019 | Best 9th gen Tiny for virtualization               | **~$220 – $350** – eBay listings for P330 Tiny machines cluster around this bracket. ([eBay][1])                          |
| **[ThinkCentre P340](https://www.lenovo.com/content/dam/lenovo/pcsd/north-america/en/solutions/workstations/datasheets/na-datasheet-thinkstation-p340-tiny.pdf)** | [i5-9400T](https://www.intel.com/content/www/us/en/products/sku/134893/intel-core-i59400t-processor-9m-cache-up-to-3-40-ghz/specifications.html) / [i7-9700T](https://www.intel.com/content/www/us/en/products/sku/191048/intel-core-i79700t-processor-12m-cache-up-to-4-30-ghz/specifications.html) | 6C / 6T – 8C / 8T  | [8148](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i5-9400T+%40+1.80GHz) / [10553](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-9700T+%40+2.00GHz) | 64GB    | 2x M.2              | 1x PCIe 3.0 x8         | Intel UHD 630 | Gen9.5     | ~8–11W      | 35W         | 2020 | Improved efficiency, better thermals               | **~$250 – $400** – typical used pricing for P340 Tiny models. ([eBay][1])                                                 |
| **[ThinkCentre P350](https://news.lenovo.com/wp-content/uploads/2021/07/ThinkStationP350TinyDatasheet-Final.pdf)**                                                | [i7-11700T](https://www.intel.com/content/www/us/en/products/sku/212251/intel-core-i711700t-processor-16m-cache-up-to-4-60-ghz/specifications.html)                                                                                                                                                  | 8C / 16T           | [15363](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-11700T+%40+1.40GHz)                                                                                   | 64GB    | 2x M.2              | 1x PCIe 4.0 capable    | Intel UHD 750 | Gen12      | ~7–10W      | 35W         | 2021 | Best for Plex, heavy VM host                       | **~$350 – $550+** – eBay.com used/refurbished listings for P350 Tiny (e.g., i5 and i7 units ~US $375–$400+). ([eBay][2])  |

[1]: https://www.ebay.com/shop/m715q?_nkw=m715q&utm_source=chatgpt.com "M715q | eBay"
[2]: https://www.ebay.com/itm/167813873476?utm_source=chatgpt.com "Lenovo ThinkStation P350 Tiny Core i5 11500T 1.50GHz 16.0GB DDR4 512GB M.2 PC | eBay"




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

| Model                                                                                                                 | CPU                                                                                                                                           | Passmark CPU Bench                                                              | RAM Max | Drives/NVMe Slots         | PCIe Slot   | iGPU          | Power (TDP) | Best Use Case                              | Rating | **Avg Used eBay Price (USD)** |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------- | ------------------------- | ----------- | ------------- | ----------- | ------------------------------------------ | ------ | ----------------------------- |
| [HP z240 SFF](https://www.pcmag.com/reviews/hp-z240-sff-workstation?test_uuid=04IpBmWGZleS0I0J3epvMrC&test_variant=A) | [i7-6700](https://www.intel.com/content/www/us/en/products/sku/88196/intel-core-i76700-processor-8m-cache-up-to-4-00-ghz/specifications.html) | [8037](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i7-6700+%40+3.40GHz) | 64GB    | 1x 2.5” + 2x 3.5” + 1xM.2 | 2x PCIe x16 | Intel HD 530  | ~65W        | Proxmox host, AI/ML, multi-GPU dev         | 7.5/10 | **$90 – $160**                |
| [Dell Optiplex 3020](https://www.hardware-corner.net/desktop-models/Dell-OptiPlex-3020-SFF/)                          | [i3-4150](https://www.intel.com/content/www/us/en/products/sku/77486/intel-core-i34150-processor-3m-cache-3-50-ghz/specifications.html)       | [3400](https://www.cpubenchmark.net/cpu.php?cpu=Intel+Core+i3-4150+%40+3.50GHz) | 16GB    | 1x 3.5”                   | 1x PCIe x16 | Intel HD 4400 | ~54W        | light server, media server, backup server. | 4.5/10 | **$40 – $90**                 |


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

| **Drive Model**                                 | **Form Factor** | **Interface**   | **Capacity Options**              | **Workload Rating (TB/yr)** | **Watts (Idle/Active)**   | **Avg Used eBay.com Price (≈)**                                                                                                                                                                                          |
| ----------------------------------------------- | --------------- | --------------- | --------------------------------- | --------------------------- | ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **HGST Ultrastar He10 / HC310**                 | 3.5"            | SATA / SAS 12Gb | 10TB                              | 550 TB/yr                   | ~5.8W / ~9.5W             | **~$90 – $240** – used 10TB HGST Ultrastar He10/SAS/SATA enterprise HDDs commonly sell around ~$90–$240 USD on eBay.com depending on condition and interface. (e.g., ~$95 sold listing; ~$138–$255+ active). ([eBay][1]) |
| **HGST Ultrastar He12 / HC320**                 | 3.5"            | SATA / SAS 12Gb | 12TB                              | 550 TB/yr                   | ~6.0W / ~9.8W             | **~$100 – $270+** – 12TB enterprise HGST/SAS drives often trade in this bracket on eBay.com, with prices influenced by condition and seller. (estimated from 10TB / similar listings). ([eBay][2])                       |
| **HGST Ultrastar He14 / HC330**                 | 3.5"            | SATA / SAS 12Gb | 14TB                              | 550 TB/yr                   | ~6.2W / ~10W              | **~$120 – $300+** – Larger enterprise drives like 14TB models on eBay.com see listings in this range, though individual prices vary with health/state and SAS vs SATA. ([eBay][2])                                       |
| **HGST Ultrastar He16 / HC340**                 | 3.5"            | SATA / SAS 12Gb | 16TB                              | 550 TB/yr                   | ~6.4W / ~10.2W            | **~$140 – $330+** – 16TB enterprise drives (HGST/SAS/SATA) often appear near ~$140–$330+ on eBay.com. ([eBay][3])                                                                                                        |
| **HGST Ultrastar He18 / HC350**                 | 3.5"            | SATA / SAS 12Gb | 18TB                              | 550 TB/yr                   | ~6.5W / ~10.4W            | **~$150 – $350+** – Used 18TB enterprise HGST/SAS drives typically trade near this range. Listings vary by condition and seller. ([eBay][4])                                                                          |
| **WD Ultrastar DC HC500 (HGST Legacy)**         | 3.5"            | SATA / SAS 12Gb | 8TB, 10TB                         | 550 TB/yr                   | ~5.6W / ~9.2W             | **~$70 – $220** – Used WD/HGST 8–10TB enterprise drives on US eBay.com commonly fall in this range depending on capacity and condition. ([eBay][2])                                                                      |
| **WD Ultrastar DC HC550**                       | 3.5"            | SATA / SAS 12Gb | 14TB, 16TB, 18TB                  | 550 TB/yr                   | ~5.8W / ~9.5W             | **~$120 – $330+** – Enterprise DC HC550 drives often list around ~$120–$330+ on eBay.com based on large capacity used listings. ([eBay][2])                                                                              |
| **WD Ultrastar DC HC560**                       | 3.5"            | SATA / SAS 12Gb | 20TB, 22TB                        | 550 TB/yr                   | ~6.0W / ~9.8W             | **~$200 – $380+** – Larger 20–22TB enterprise WD DC HC560 used drives generally trade in this approximate price bracket on US eBay.com. ([eBay][4])                                                                   |
| **WD Ultrastar DC SA620 (SATA SSD/HDD Hybrid)** | 2.5"            | SATA 6Gb/s      | 960GB — 7.68TB                    | *N/A (SSHD)*                | ~2.9W / ~5.5W             | **~$40 – $150** – Used SATA hybrid drives (SSHD) of similar capacities on eBay.com often list in the ~$40–$150 USD range. ([eBay][5])                                                                                    |
| **WD Gold Enterprise HDDs**                     | 3.5"            | SATA 6Gb/s      | 1TB — 18TB                        | 550 TB/yr                   | 5W — 10W (varies by size) | **~$50 – $330+** – Used WD Gold HDD enterprise drives vary by capacity: smaller (~1–4TB) often ~$50–$120, larger (~12–18TB) near ~$200–$330+ on eBay.com. ([eBay][5])                                                    |
| **Seagate Exos X18**                            | 3.5"            | SATA 6Gb/s      | 10TB, 12TB, 14TB, 16TB, 18TB      | 550 TB/yr                   | 5.3W / 9.4W               | **~$120 – $340+** – Used Seagate Exos X18 enterprise drives typically appear around ~$120–$340+ USD on eBay.com depending on capacity and condition. ([eBay][5])                                                         |
| **Seagate Exos X20**                            | 3.5"            | SATA 6Gb/s      | 16TB, 18TB, 20TB                  | 550 TB/yr                   | 5.4W / 9.4W               | **~$180 – $400+** – Larger Exos X20 drives on eBay.com often trade for roughly ~$180–$400+ used, varying by model and health. ([eBay][5])                                                                                |
| **Seagate Exos 7E10**                           | 3.5"            | SAS 12Gb/s      | 1TB, 2TB, 4TB, 8TB                | 550 TB/yr                   | 7.6W / 11.5W              | **~$30 – $180** – Used smaller Exos enterprise drives (~1–8TB) on US eBay.com often list roughly ~$30–$180 depending on capacity and condition. ([eBay][5])                                                              |
| **Toshiba MG09 Series**                         | 3.5"            | SATA / SAS      | 14TB, 16TB, 18TB                  | 550 TB/yr                   | 4.2W / 8.3W               | **~$130 – $300+** – Used Toshiba MG09 enterprise drives typically show prices around ~$130–$300+ USD on eBay.com. ([eBay][5])                                                                                            |
| **Toshiba MG10 Series**                         | 3.5"            | SATA / SAS      | 20TB, 22TB                        | 550 TB/yr                   | 4.4W / 8.6W               | **~$200 – $380+** – Used Toshiba MG10 (20–22TB) enterprise drives eBay.com listings often in the ~$200–$380+ range. ([eBay][5])                                                                                          |
| **Seagate Exos 10E2400 (2.4TB)**                | 2.5"            | SAS 12Gb/s      | 600GB, 900GB, 1.2TB, 1.8TB, 2.4TB | 550 TB/yr                   | 3.8W / 6.9W               | **~$30 – $120** – Used 2.5" SAS enterprise drives (e.g., ~600GB–2.4TB) on eBay.com generally fall in the ~$30–$120 range. ([eBay][5])                                                                                    |
| **Western Digital Ultrastar 10K600**            | 2.5"            | SAS 12Gb/s      | 600GB, 900GB, 1.2TB               | 550 TB/yr                   | 3.6W / 6.5W               | **~$30 – $120** – Smaller SAS enterprise HDDs (10K RPM) used on eBay.com often list around ~$30–$120 USD depending on capacity. ([eBay][5])                                                                              |

[1]: https://www.ebay.com/itm/257100620905?hash=item3bdc642469%3Ag%3AUl8AAeSwM6BotJcQ&itmmeta=01K4SSDQY8QT5N5JHGJY356CD3&itmprp=enc%3AAQAKAAAA4MHg7L1Zz0LA5DYYmRTS30lnm1OX9xbE1yK%2FDB1WTBH4x%2BuJB8YX32Rdw5Ql%2BB3M3%2BRIY6q6tkv2ROAxTPOYO49p7uzdhTJURAgZwf5GEBgpcuAuZj0aKwBaqmIuLluc5FaFoP3r9sX%2Bn0kGGV6xPXCaY81gfc00Fqd9CaDb8gtI296okYHV3uT%2FopXrSvB0LEvMP2Ood4yHb4efwfWaE9IQW28BzCvsM8OpeO17uqteajkWKm0iKSEwUTsOZWvTm4%2FxNrEmZzIBDT%2Fry7o3SalRKXZGbyvodgwyTelpvRos%7Ctkp%3ABk9SR6T_trmmZg&utm_source=chatgpt.com "Western digital HGST Ultrastar He10 10TB Enterprise HDD ..."
[2]: https://www.ebay.com/b/HGST-Internal-Hard-Disk-Drives-10-TB-Storage-Capacity/56083/bn_71160838?utm_source=chatgpt.com "HGST Internal Hard Disk Drives 10 TB Storage Capacity for sale | eBay"
[3]: https://www.ebay.com/shop/16tb-hard-drive?_nkw=16tb+hard+drive&utm_source=chatgpt.com "16TB Hard Drive"
[4]: https://www.ebay.com/sch/i.html?_nkw=18tb+hard+drive "18TB Hard Drive"
[5]: https://www.ebay.com/p/12062799086?utm_source=chatgpt.com "Internal Hard Disk Drives for Sale - eBay"


NOTES: in my opinion, HGST have the Lowest failure rates along side Western Digital. 
<br> Seagate / Toshiba models tend to have higher failure rates depending on models. but they are often cheaper, sometimes by a fair amount. 
<br> Seagates depending on the model can be the worst drives to purchase, so unless you want to research the specific model you are buying, you probably want HGST/WD. 
<br> Samsung HDDs also have fairly high failure rates. SSDs are good but HDDs are hit and miss. 
<details>
<summary><b>BackBlaze Hard Drive Failure Data By Year</b></summary>

**2024:**
# Backblaze Hard Drive Failure Rates for 2024
Reporting period: 1/1/2024 – 12/31/2024 inclusive  
Drive models with drive count > 250 as of 12/31/2024 and drive days > 50,000 in 2024.

| MFG     | Model             | Size (TB) | Drive Count | Avg Age (months) | Drive Days  | Drive Failures | AFR   |
|---------|------------------|----------:|------------:|-----------------:|------------:|---------------:|------:|
| HGST    | HMS5C4040ALE640  | 4  | 263   | 95.5 | 327,114   | 4   | 0.45% |
| HGST    | HMS5C4040BLE640  | 4  | 4,120 | 95.9 | 3,078,618 | 18  | 0.21% |
| HGST    | HUH728080ALE600  | 8  | 1,084 | 79.8 | 400,697   | 18  | 1.64% |
| HGST    | HUH721212ALE600  | 12 | 2,606 | 61.8 | 949,117   | 32  | 1.23% |
| HGST    | HUH721212ALE604  | 12 | 13,313| 43.3 | 4,786,933 | 435 | 3.32% |
| HGST    | HUH721212ALN604  | 12 | 10,191| 66.5 | 3,814,797 | 590 | 5.65% |
| Seagate | ST8000DM002      | 8  | 9,078 | 98.6 | 3,355,725 | 162 | 1.76% |
| Seagate | ST8000NM0055     | 8  | 13,534| 87.0 | 5,020,845 | 356 | 2.59% |
| Seagate | ST10000NM0086    | 10 | 1,034 | 84.4 | 391,133   | 58  | 5.41% |
| Seagate | ST12000NM0007    | 12 | 1,038 | 61.3 | 400,953   | 125 | 11.38% |
| Seagate | ST12000NM0008    | 12 | 19,134| 56.2 | 7,060,183 | 502 | 2.60% |
| Seagate | ST12000NM000J    | 12 | 723   | 8.5  | 172,556   | 16  | 3.38% |
| Seagate | ST12000NM001G    | 12 | 13,184| 46.8 | 4,814,820 | 166 | 1.26% |
| Seagate | ST14000NM001G    | 14 | 10,589| 46.3 | 3,863,921 | 175 | 1.65% |
| Seagate | ST14000NM0138    | 14 | 1,321 | 48.9 | 498,291   | 73  | 5.35% |
| Seagate | ST16000NM001G    | 16 | 33,600| 28.6 | 11,737,654| 226 | 0.70% |
| Seagate | ST16000NM002J    | 16 | 461   | 25.8 | 168,170   | 1   | 0.22% |
| Toshiba | MG07ACA14TA      | 14 | 37,703| 49.7 | 13,729,393| 414 | 1.10% |
| Toshiba | MG07ACA14TEY     | 14 | 742   | 36.4 | 230,649   | 10  | 1.58% |
| Toshiba | MG08ACA16TA      | 16 | 40,185| 19.1 | 14,089,908| 484 | 1.25% |
| Toshiba | MG08ACA16TE      | 16 | 5,912 | 38.4 | 2,173,570 | 68  | 1.14% |
| Toshiba | MG08ACA16TEY     | 16 | 5,163 | 36.9 | 1,889,434 | 82  | 1.58% |
| Toshiba | MG10ACA20TE      | 20 | 5,943 | 3.8  | 631,665   | 15  | 0.87% |
| WDC     | WUH721414ALE6L4  | 14 | 8,542 | 47.8 | 3,110,146 | 72  | 0.84% |
| WDC     | WUH721816ALE6L0  | 16 | 3,016 | 36.2 | 1,103,215 | 37  | 1.22% |
| WDC     | WUH721816ALE6L4  | 16 | 26,475| 21.1 | 9,365,201 | 94  | 0.37% |
| WDC     | WUH722222ALE6L4  | 22 | 30,000| 5.8  | 4,741,582 | 139 | 1.07% |

| **TOTALS** |  |  | **298,954** |  | **101,906,290** | **4,372** | **1.57%** |
  
**2023:**
# Backblaze Hard Drive Failure Rates for 2023
Reporting period: 1/1/2023 – 12/31/2023 inclusive

| MFG     | Model             | Drive Size | Drive Count | Avg Age (months) | Drive Days  | Drive Failures | AFR   |
|---------|------------------|------------|------------:|-----------------:|------------:|---------------:|------:|
| HGST    | HMS5C4040ALE640  | 4TB  | 1,950  | 85.5 | 1,182,145 | 12  | 0.37% |
| HGST    | HMS5C4040BLE640  | 4TB  | 10,260 | 86.0 | 4,219,579 | 44  | 0.38% |
| HGST    | HUH728080ALE600  | 8TB  | 1,103  | 68.0 | 401,471   | 27  | 2.45% |
| HGST    | HUH728080ALE604  | 8TB  | 89     | 77.6 | 33,059    | 5   | 5.52% |
| HGST    | HUH721212ALE600  | 12TB | 2,606  | 50.5 | 938,602   | 21  | 0.82% |
| HGST    | HUH721212ALE604  | 12TB | 13,144 | 33.1 | 4,780,695 | 125 | 0.95% |
| HGST    | HUH721212ALN604  | 12TB | 10,532 | 56.0 | 3,829,510 | 387 | 3.69% |
| Seagate | ST4000DM000      | 4TB  | 11,391 | 96.6 | 6,149,245 | 560 | 3.32% |
| Seagate | ST6000DX000      | 6TB  | 882    | 104.0| 322,461   | 6   | 0.68% |
| Seagate | ST8000DM002      | 8TB  | 9,250  | 86.7 | 3,408,498 | 267 | 2.86% |
| Seagate | ST8000NM000A     | 8TB  | 204    | 14.1 | 52,876    | 0   | 0.00% |
| Seagate | ST8000NM0055     | 8TB  | 13,914 | 74.9 | 5,144,580 | 543 | 3.85% |
| Seagate | ST10000NM0086    | 10TB | 1,097  | 72.5 | 410,970   | 74  | 6.57% |
| Seagate | ST12000NM0007    | 12TB | 1,162  | 49.6 | 440,056   | 96  | 7.96% |
| Seagate | ST12000NM0008    | 12TB | 19,449 | 44.7 | 7,128,136 | 573 | 2.93% |
| Seagate | ST12000NM000J    | 12TB | 195    | 2.7  | 15,811    | 1   | 2.31% |
| Seagate | ST12000NM001G    | 12TB | 13,108 | 35.5 | 4,700,930 | 153 | 1.19% |
| Seagate | ST14000NM000J    | 14TB | 77     | 2.6  | 4,986     | 2   | 14.64% |
| Seagate | ST14000NM0018    | 14TB | 66     | 17.1 | 16,492    | 6   | 13.28% |
| Seagate | ST14000NM001G    | 14TB | 10,693 | 34.4 | 3,905,366 | 193 | 1.80% |
| Seagate | ST14000NM0138    | 14TB | 1,400  | 36.9 | 528,390   | 116 | 8.01% |
| Seagate | ST16000NM001G    | 16TB | 27,433 | 21.2 | 9,160,212 | 176 | 0.70% |
| Seagate | ST16000NM002J    | 16TB | 463    | 13.7 | 123,261   | 2   | 0.59% |
| Seagate | ST18000NM000J    | 18TB | 60     | 36.7 | 21,630    | 3   | 5.06% |
| Toshiba | MD04ABA400V      | 4TB  | 93     | 103.4| 34,042    | 1   | 1.07% |
| Toshiba | HDWF180          | 8TB  | 60     | 24.8 | 18,889    | 5   | 9.66% |
| Toshiba | MG07ACA14TA      | 14TB | 37,913 | 37.8 | 13,827,478| 426 | 1.12% |
| Toshiba | MG07ACA14TEY     | 14TB | 649    | 27.6 | 219,865   | 8   | 1.33% |
| Toshiba | MG08ACA16TA      | 16TB | 33,750 | 9.0  | 4,995,010 | 149 | 1.09% |
| Toshiba | MG08ACA16TE      | 16TB | 5,960  | 26.5 | 2,140,932 | 56  | 0.95% |
| Toshiba | MG08ACA16TEY     | 16TB | 5,230  | 24.9 | 1,894,368 | 58  | 1.12% |
| WDC     | WUH721414ALE6L4  | 14TB | 8,471  | 36.5 | 3,066,209 | 36  | 0.43% |
| WDC     | WUH721816ALE6L0  | 16TB | 3,053  | 24.2 | 996,710   | 9   | 0.33% |
| WDC     | WUH721816ALE6L4  | 16TB | 21,607 | 11.6 | 5,707,555 | 47  | 0.30% |
| WDC     | WUH722222ALE6L4  | 22TB | 2,442  | 2.4  | 126,956   | 2   | 0.58% |

| **TOTAL (35 models)** |  |  | **269,756** |  | **89,946,975** | **4,189** | **1.70%** |

**2022:**
# Backblaze Hard Drive Failure Rates for 2022
Reporting period: 1/1/2022 – 12/31/2022 inclusive

| MFG     | Model             | Drive Size | Drive Count | Avg Age (months) | Drive Days | Drive Failures | AFR   |
|---------|------------------|------------|------------:|-----------------:|-----------:|---------------:|------:|
| HGST    | HMS5C4040ALE640  | 4TB  | 3,723  | 77.1 | 1,322,966 | 23  | 0.63% |
| HGST    | HMS5C4040BLE640  | 4TB  | 12,730 | 74.1 | 4,641,631 | 52  | 0.41% |
| HGST    | HUH728080ALE600  | 8TB  | 1,117  | 56.6 | 408,895   | 16  | 1.43% |
| HGST    | HUH728080ALE604  | 8TB  | 94     | 65.5 | 27,684    | 4   | 5.27% |
| HGST    | HUH721212ALE600  | 12TB | 2,606  | 38.9 | 948,201   | 7   | 0.27% |
| HGST    | HUH721212ALE604  | 12TB | 13,165 | 21.3 | 4,789,187 | 73  | 0.56% |
| HGST    | HUH721212ALN604  | 12TB | 10,769 | 44.8 | 3,930,437 | 80  | 0.74% |
| Seagate | ST4000DM000      | 4TB  | 18,246 | 85.9 | 6,699,353 | 633 | 3.45% |
| Seagate | ST6000DX000      | 6TB  | 886    | 92.5 | 323,387   | 6   | 0.68% |
| Seagate | ST8000DM002      | 8TB  | 9,523  | 74.6 | 3,505,962 | 189 | 1.97% |
| Seagate | ST8000NM000A     | 8TB  | 79     | 14.2 | 22,839    | 0   | 0.00% |
| Seagate | ST8000NM0055     | 8TB  | 14,417 | 63.2 | 5,230,097 | 347 | 2.42% |
| Seagate | ST10000NM0086    | 10TB | 1,174  | 60.7 | 430,092   | 44  | 3.73% |
| Seagate | ST12000NM0007    | 12TB | 1,262  | 37.7 | 469,211   | 61  | 4.75% |
| Seagate | ST12000NM0008    | 12TB | 19,821 | 33.1 | 7,291,905 | 404 | 2.02% |
| Seagate | ST12000NM001G    | 12TB | 12,623 | 24.9 | 4,515,095 | 116 | 0.94% |
| Seagate | ST14000NM001G    | 14TB | 10,751 | 22.8 | 3,912,395 | 126 | 1.18% |
| Seagate | ST14000NM0138    | 14TB | 1,519  | 24.8 | 570,042   | 89  | 5.70% |
| Seagate | ST16000NM001G    | 16TB | 20,393 | 13.6 | 6,057,376 | 142 | 0.86% |
| Seagate | ST16000NM002J    | 16TB | 310    | 6.6  | 50,625    | 2   | 1.44% |
| Toshiba | MD04ABA400V      | 4TB  | 94     | 91.3 | 35,031    | 3   | 3.13% |
| Toshiba | MG07ACA14TA      | 14TB | 38,182 | 26.0 | 13,921,635| 385 | 1.01% |
| Toshiba | MG07ACA14TEY     | 14TB | 552    | 20.7 | 184,247   | 8   | 1.58% |
| Toshiba | MG08ACA16TA      | 16TB | 3,751  | 6.9  | 625,329   | 10  | 0.58% |
| Toshiba | MG08ACA16TE      | 16TB | 5,936  | 14.7 | 2,167,676 | 93  | 1.57% |
| Toshiba | MG08ACA16TEY     | 16TB | 5,286  | 12.9 | 1,362,038 | 24  | 0.64% |
| WDC     | WUH721414ALE6L4  | 14TB | 8,410  | 24.8 | 3,065,102 | 10  | 0.12% |
| WDC     | WUH721816ALE6L0  | 16TB | 2,701  | 14.9 | 938,328   | 3   | 0.12% |
| WDC     | WUH721816ALE6L4  | 16TB | 10,801 | 4.6  | 1,313,668 | 13  | 0.36% |

| **TOTAL (29 models)** |  |  | **230,921** |  | **78,760,434** | **2,963** | **1.37%** |

<details>
<summary><b>Data Summary:</b></summary>
  
 ## 📊 Backblaze Drive Reliability Summary (2022–2024)

This summary is based strictly on the 2022, 2023, and 2024 AFR data provided above.

---

## 🔎 Brand-Level Overview

### 🟢 WDC (Western Digital)
- Most consistent low failure rates across all three years
- Rarely exceeds 1.2% AFR
- Strong reliability trend overall

### 🟢 Toshiba
- Generally stable AFR (~1.0–1.5%)
- Few extreme outliers
- Consistent mid-range reliability

### 🟡 HGST
- Excellent reliability in 4TB models
- Some 12TB models show elevated AFR in 2023–2024
- Wider spread between best and worst models

### 🔴 Seagate
- Largest variability across models
- Several high AFR spikes (5–11%+)
- Also includes some very reliable 16TB models

---

# 🏆 Best Performing Models (Lowest AFR Observed)

### ⭐ Absolute Lowest AFR
- **Seagate ST8000NM000A (2022, 2023)** – 0.00%  
  > Note: Very small sample size.

---

### ⭐ Consistently Excellent Models (<0.40% observed)

- **WDC WUH721414ALE6L4**
  - 2022: 0.12%
  - 2023: 0.43%
  - 2024: 0.84%

- **WDC WUH721816ALE6L4**
  - 2022: 0.36%
  - 2023: 0.30%
  - 2024: 0.37%

- **HGST HMS5C4040BLE640**
  - 2022: 0.41%
  - 2023: 0.38%
  - 2024: 0.21%

- **Seagate ST16000NM001G**
  - 2022: 0.86%
  - 2023: 0.70%
  - 2024: 0.70%

---

## 🔥 Worst Performing Models (Highest AFR Observed)

### 🚨 Highest Single-Year AFR

- **Seagate ST14000NM000J (2023)** – 14.64%
- **Seagate ST14000NM0018 (2023)** – 13.28%
- **Seagate ST12000NM0007 (2024)** – 11.38%
- **Toshiba HDWF180 (2023)** – 9.66%
- **Seagate ST14000NM0138 (2023)** – 8.01%
- **Seagate ST12000NM0007 (2023)** – 7.96%

---

### ⚠ Consistently High AFR Across Multiple Years

- **Seagate ST10000NM0086**
  - 2023: 6.57%
  - 2024: 5.41%

- **HGST HUH721212ALN604**
  - 2023: 3.69%
  - 2024: 5.65%

---

# 📌 Overall Conclusions

### 🥇 Most Reliable Brand (Overall Trend)
**WDC** — lowest and most stable AFR across all years.

### 🥈 Strong Overall Consistency
**Toshiba** — stable, moderate AFR with few severe spikes.

### ⚖ Mixed Performance
**HGST** — excellent 4TB reliability, but some 12TB models show higher failure rates.

### 🔴 Highest Variability
**Seagate** — wide performance spread; some models highly reliable, others with significant AFR spikes.

---

> ⚠ Note: AFR values are based on Backblaze fleet data and are influenced by drive count, age, and operational environment.

</details>
</details>
<hr>

### SSD/Nvme Drives:

# Enterprise NVMe / M.2 Drives with Endurance

| **Drive Model**                              | **Form Factor**  | **Interface** | **Endurance (TBW/PBW)**     | **Watts (Idle/Active)** | **Avg Used eBay.com Price (≈)**                                                    |
| -------------------------------------------- | ---------------- | ------------- | --------------------------- | ----------------------- | ---------------------------------------------------------------------------------- |
| **Intel Optane M10 (16GB)**                  | M.2 2280         | PCIe 3.0 x2   | 365 TBW                     | 0.08W/2W                | **~$5 – $15** (small Optane modules frequently listed cheap) ([Reddit][1])         |
| **Intel Optane M10 (32GB)**                  | M.2 2280         | PCIe 3.0 x2   | 182.5 TBW                   | 1W/3.5W                 | **~$20 – $35** (new/used available) ([eBay][2])                                    |
| **Intel Optane SSD 905P (480GB)**            | M.2/U.2/HHHL     | PCIe 3.0 x4   | 17.52 PB                    | 6W/16.4W                | **~$350 – $450** (used 480GB approx) ([eBay][3])                                   |
| **Intel Optane SSD 905P (960GB)**            | U.2/HHHL         | PCIe 3.0 x4   | 17.52 PB                    | 6W/16.4W                | **~$600 – $900** (used 960GB listings) ([eBay][4])                                 |
| **Samsung PM9A3 (960GB, 1920GB, 3840GB)**    | M.2 22110        | PCIe 4.0 x4   | 1.7 PBW / 3.5 PBW / 7.0 PBW | 3.5W/8W Avg             | **N/A** (rare to no used eBay listings)                                            |
| **Seagate Nytro 5000 (1.6TB, 3.2TB, 6.4TB)** | M.2 22110        | PCIe 3.0 x4   | 3.2 PBW                     | 9W Avg/12.5W Max        | **N/A** (rare to no eBay used data)                                                |
| **Intel DC P5800X (400GB,800GB,1.6TB)**      | U.2              | PCIe 4.0 x4   | 73–292 PBW                  | 4.2W/18W                | **~$900 – $1,200+** (varies hugely; some reports of ~$1,200-$2,000+) ([Reddit][1]) |
| **ADATA XPG SX8200 Pro (256GB–2TB)**         | M.2 2280         | PCIe 3.0 x4   | 160–640 TBW                 | 0.05W/1.9W/4.1W Max     | **~$70 – $110** (rough average for 1TB) *(typical eBay used SSD pricing)*          |
| **Intel DC P3700 400GB**                     | PCIe Add-in Card | PCIe 3.0 x4   | 7.3 PBW                     | 4W/9W/12W               | **~$50 – $90** (used PCIe P3700 cards) *(typical older enterprise SSD prices)*     |
| **Intel Optane P4801X 100GB**                | M.2 2280         | PCIe 3.0 x4   | 10.9 PBW                    | 3W/7W                   | **~$150 – $300** *(occasional US eBay used listings)*                              |

[1]: https://www.reddit.com/r/DataHoarder/comments/1nferxo/i_finally_got_my_grail_intel_optane_p5800x_16t/?utm_source=chatgpt.com "I finally got my grail. Intel Optane P5800X 1.6T. This is gonna be a family heirloom"
[2]: https://il.ebay.com/b/Intel-PCI-Express-Solid-State-Drives/175669/bn_25407512?utm_source=chatgpt.com "Intel PCI Express Solid State Drives for sale | eBay"
[3]: https://www.ebay.com/itm/236331332040?utm_source=chatgpt.com "compatible Intel/HP OPTANE SSD 9 OPTANE 905P ... - eBay"
[4]: https://www.ebay.com/itm/396371709317?utm_source=chatgpt.com "USED-Intel Optane 905P Series 960GB PCIe3.0 NVMe ..."


# Consumer NVMe / M.2 Drives
| **Drive Model**         | **Form Factor** | **Interface** | **Endurance (TBW)** | **Quality**              | **Avg Used eBay.com Price (≈)**                                                                   |
| ----------------------- | --------------- | ------------- | ------------------- | ------------------------ | ------------------------------------------------------------------------------------------------- |
| **Crucial P3 1TB**      | M.2 2280        | PCIe 3.0 x4   | 220 TB              | Cheap QLC Consumer       | **~$25 – $50** (pre-owned listings range from ~$20–$95) ([eBay][1])                               |
| **Samsung 980 1TB**     | M.2 2280        | PCIe 3.0 x4   | 600 TB              | Normal TLC Consumer      | **~$70 – $110** (used prices commonly ~$80–$120 on eBay) ([eBay][2])                              |
| **Samsung 980 Pro 1TB** | M.2 2280        | PCIe 4.0 x4   | 600 TB              | Modern TLC Prosumer      | **~$110 – $140** (used avg visible ~ $125) ([eBay][2])                                            |
| **Samsung 970 Pro 1TB** | M.2 2280        | PCIe 3.0 x4   | 1,200 TB            | End-of-Life MLC Prosumer | **~$180 – $260** (older enterprise SSD, used listings less frequent but often ~$200+) ([eBay][2]) |

[1]: https://www.ebay.com/shop/crucial-p3?_nkw=crucial+p3&utm_source=chatgpt.com "Crucial P3"
[2]: https://www.ebay.com/b/Samsung-1-TB-PCI-Express-Solid-State-Drives/175669/bn_77238159?utm_source=chatgpt.com "Samsung 1 TB PCI Express Solid State Drives for sale | eBay"



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
<br>⚠️ Legal Note: using third-party vGPU “unlocks” technically can violate NVIDIA licensing/EULA and carry possible legal/operational risk. production users should use official NVIDIA vGPU licensing, Unlocks should only be used on your own personal hardware for private non-commercial use cases. 
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

| **Model**                                                                        | **VRAM**   | **FP32**     | **FP16**     | **TDP** | **Est. Idle** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                         |
| -------------------------------------------------------------------------------- | ---------- | ------------ | ------------ | ------- | ------------- | ------------- | ------------------ | ------------------------------------------------------- |
| [**Intel Arc A310**](https://www.techpowerup.com/gpu-specs/arc-a310.c3931)       | 4GB GDDR6  | 3.072 TFLOPS | 6.144 TFLOPS | 75 W    | 8–15 W        | 124 GB/s      | ❌ No SR-IOV        | **~$160 – $200** (used & some new listings) ([eBay][1]) |
| [**Intel Arc A380**](https://www.techpowerup.com/gpu-specs/arc-a380.c3913)       | 6GB GDDR6  | 4.198 TFLOPS | 8.397 TFLOPS | 75 W    | 8–15 W        | 186 GB/s      | ❌ No SR-IOV        | **~$160 – $240** (common eBay US range) ([eBay][2])     |
| [**Intel Arc A580**](https://www.techpowerup.com/gpu-specs/arc-a580.c3927)       | 8GB GDDR6  | 12.29 TFLOPS | 24.58 TFLOPS | 185 W   | 15–25 W       | 256 GB/s      | ❌ No SR-IOV        | **~$200 – $300** (used listings vary) ([eBay][1])       |
| [**Intel Arc A750**](https://www.techpowerup.com/gpu-specs/arc-a750.c3922)       | 8GB GDDR6  | 17.20 TFLOPS | 34.41 TFLOPS | 225 W   | 18–30 W       | 512 GB/s      | ❌ No SR-IOV        | **~$160 – $220** (used average) ([eBay][1])             |
| [**Intel Arc A770 16GB**](https://www.techpowerup.com/gpu-specs/arc-a770.c3914)  | 16GB GDDR6 | 19.66 TFLOPS | 39.32 TFLOPS | 225 W   | 18–30 W       | 512 GB/s      | ❌ No SR-IOV        | **~$250 – $350** (used & new) ([eBay][1])               |
| [**Intel Arc Pro A40**](https://www.techpowerup.com/gpu-specs/arc-pro-a40.c3925) | 6GB GDDR6  | 3.482 TFLOPS | 6.963 TFLOPS | 50 W    | 6–10 W        | 192 GB/s      | ✅ SR-IOV           | **~$220 – $280** (rare used eBay sales) ([eBay][1])     |
| [**Intel Arc Pro A50**](https://www.techpowerup.com/gpu-specs/arc-pro-a50.c3926) | 6GB GDDR6  | 4.813 TFLOPS | 9.626 TFLOPS | 75 W    | 8–15 W        | 192 GB/s      | ✅ SR-IOV           | **~$250 – $320** (used listings) ([eBay][1])            |
| [**Intel Arc Pro A60**](https://www.techpowerup.com/gpu-specs/arc-pro-a60.c4160) | 12GB GDDR6 | 8.397 TFLOPS | 16.79 TFLOPS | 130 W   | 10–20 W       | 384 GB/s      | ✅ SR-IOV           | **~$350 – $500** (scarcer on eBay) ([eBay][1])          |
| [**Intel Arc B580**](https://www.techpowerup.com/gpu-specs/arc-b580.c4244)       | 12GB GDDR6 | 13.67 TFLOPS | 27.34 TFLOPS | 190 W   | 15–25 W       | 256 GB/s      | ❌ No SR-IOV        | **~$230 – $300** (used & some new pricing) ([eBay][1])  |
| [**Intel Arc Pro B50**](https://www.techpowerup.com/gpu-specs/arc-pro-b50.c4345) | 16GB GDDR6 | 10.65 TFLOPS | 21.30 TFLOPS | 70 W    | 7–15 W        | 224 GB/s      | ✅ SR-IOV           | **~$350 – $450** (limited used) ([eBay][1])             |
| [**Intel Arc Pro B60**](https://www.techpowerup.com/gpu-specs/arc-pro-b60.c4350) | 24GB GDDR6 | 12.29 TFLOPS | 24.58 TFLOPS | 200 W   | 15–30 W       | 456 GB/s      | ✅ SR-IOV           | **~$500 – $800** (very limited) ([eBay][1])             |

[1]: https://cr.ebay.com/b/Intel-Computer-Graphics-Cards/27386/bn_7113457456?utm_source=chatgpt.com "Intel Computer Graphics Cards for sale - eBay"
[2]: https://www.ebay.com/shop/intel-a310?_nkw=intel+a310&utm_source=chatgpt.com "Intel A310 | eBay"




## NVIDIA RTX 10 Series (Pascal)

| **Model**                                                                             | **VRAM** | **FP16**     | **FP32**     | **TDP** | **Idle Power** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                  |
| ------------------------------------------------------------------------------------- | -------- | ------------ | ------------ | ------- | -------------- | ------------- | ------------------ | -------------------------------------------------------------------------------- |
| [**GTX 1050**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1050.c2875)          | 2 GB     | 29.10 GFLOPS | 1.862 TFLOPS | 75 W    | ~8–12 W        | 112 GB/s      | ✅ Unlock           | **~$50 – $80** (many used ~75 USD listed) ([eBay][1])                            |
| [**GTX 1050 Ti**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1050-ti.c2885)    | 4 GB     | 33.41 GFLOPS | 2.138 TFLOPS | 75 W    | ~8–12 W        | 112 GB/s      | ✅ Unlock           | **~$60 – $95** (common used range) ([eBay][1])                                   |
| [**GTX 1060 3GB**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1060-3-gb.c2867) | 3 GB     | 61.49 GFLOPS | 3.935 TFLOPS | 120 W   | ~10–18 W       | 192 GB/s      | ✅ Unlock           | **~$70 – $110** (used teen-range sale reports & community pricing) ([Reddit][2]) |
| [**GTX 1060 6GB**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1060-6-gb.c2862) | 6 GB     | 68.36 GFLOPS | 4.375 TFLOPS | 120 W   | ~10–18 W       | 192 GB/s      | ✅ Unlock           | **~$80 – $120** (common actual eBay used prices) ([Reddit][3])                   |
| [**GTX 1070**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1070.c2840)          | 8 GB     | 101.0 GFLOPS | 6.463 TFLOPS | 150 W   | ~12–20 W       | 256 GB/s      | ✅ Unlock           | **~$90 – $140** (community eBay pricing) ([Reddit][4])                           |
| [**GTX 1070 Ti**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1070-ti.c3010)    | 8 GB     | 127.9 GFLOPS | 8.186 TFLOPS | 180 W   | ~15–25 W       | 256 GB/s      | ✅ Unlock           | **~$110 – $180** (user report and typical used sale) ([Reddit][5])               |
| [**GTX 1080**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1080.c2839)          | 8 GB     | 139 GFLOPS   | 8.873 TFLOPS | 180 W   | ~15–25 W       | 320.3 GB/s    | ✅ Unlock           | **~$110 – $160** (recent used prices seen) ([Reddit][3])                         |
| [**GTX 1080 Ti**](https://www.techpowerup.com/gpu-specs/geforce-gtx-1080-ti.c2877)    | 11 GB    | 177.2 GFLOPS | 11.34 TFLOPS | 250 W   | ~18–30 W       | 484.4 GB/s    | ✅ Unlock           | **~$140 – $220** (many used listings around $150-$200) ([eBay][6])               |

[1]: https://www.ebay.com/shop/nvidia-geforce-gtx-1050-ti?_nkw=nvidia+geforce+gtx+1050+ti&utm_source=chatgpt.com "Nvidia Geforce GTX 1050 Ti"
[2]: https://www.reddit.com/r/HardwareSwapUK/comments/158gf0l?utm_source=chatgpt.com "[BG] GTX 1060 3GB/10 Series GPU [H] £40"
[3]: https://www.reddit.com/r/hardwareswap/comments/1hegwse?utm_source=chatgpt.com "[USA-IL] [H] MSI GTX 1080 DUKE 8GB, MSI GTX 1060 GAMING X 6GB, EVGA GTX 1050 Ti SSC GAMING 4GB [W] Cash or PayPal"
[4]: https://www.reddit.com/r/PcBuild/comments/1h43499?utm_source=chatgpt.com "Used gtx graphics cards prices"
[5]: https://www.reddit.com/r/nvidia/comments/hz23nr?utm_source=chatgpt.com "Is 250$ a good price for a barely used GTX 1070 Ti?"
[6]: https://www.ebay.com/b/NVIDIA-GeForce-GTX-1080-Ti-NVIDIA-Computer-Graphics-Cards/27386/bn_7116464572?utm_source=chatgpt.com "NVIDIA GeForce GTX 1080 Ti - eBay"


## NVIDIA RTX 20 Series (Turing)

| **GPU**                                                                                  | **CUDA** | **VRAM**    | **FP32** | **FP16** | **TDP** | **Idle** | **Virtualization** | **Avg Used eBay.com Price (≈)**        |
| ---------------------------------------------------------------------------------------- | -------- | ----------- | -------- | -------- | ------- | -------- | ------------------ | -------------------------------------- |
| [**RTX 2060**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2060.c3310)             | 1920     | 6 GB GDDR6  | 6.5 TF   | 6.5 TF   | 160 W   | ~8 W     | ✅ Unlock           | **~$170 – $200** ([Tom's Hardware][1]) |
| [**RTX 2060 Super**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2060-super.c3441) | 2176     | 8 GB GDDR6  | 7.2 TF   | 7.2 TF   | 175 W   | ~9 W     | ✅ Unlock           | **~$180 – $230** ([Tom's Hardware][1]) |
| [**RTX 2070**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2070.c3252)             | 2304     | 8 GB GDDR6  | 7.5 TF   | 7.5 TF   | 175 W   | ~9 W     | ✅ Unlock           | **~$200 – $250** ([Tom's Hardware][1]) |
| [**RTX 2070 Super**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2070-super.c3440) | 2560     | 8 GB GDDR6  | 9.1 TF   | 9.1 TF   | 215 W   | ~9 W     | ✅ Unlock           | **~$220 – $270** ([Tom's Hardware][1]) |
| [**RTX 2080**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080.c3224)             | 2944     | 8 GB GDDR6  | 10.1 TF  | 10.1 TF  | 215 W   | ~10 W    | ✅ Unlock           | **~$240 – $300** ([Tom's Hardware][1]) |
| [**RTX 2080 Super**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080-super.c3439) | 3072     | 8 GB GDDR6  | 11.2 TF  | 11.2 TF  | 250 W   | ~10 W    | ✅ Unlock           | **~$250 – $320** ([Tom's Hardware][1]) |
| [**RTX 2080 Ti**](https://www.techpowerup.com/gpu-specs/geforce-rtx-2080-ti.c3305)       | 4352     | 11 GB GDDR6 | 13.4 TF  | 13.4 TF  | 250 W   | ~11 W    | ✅ Unlock           | **~$300 – $380** ([Tom's Hardware][1]) |

[1]: https://www.tomshardware.com/news/gpus-historical-ebay-pricing/8?utm_source=chatgpt.com "March 2023 eBay GPU Prices - eBay Historical GPU Prices 2023: November 2023 Update - Page 8 | Tom's Hardware"



## NVIDIA RTX 30 Series (Ampere)
| **Model**                                                                               | **VRAM** | **FP32**     | **FP16**     | **TDP** | **Est. Idle** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                             |
| --------------------------------------------------------------------------------------- | -------- | ------------ | ------------ | ------- | ------------- | ------------- | ------------------ | --------------------------------------------------------------------------- |
| [**RTX 3060 12GB**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3060-12-gb.c3682) | 12 GB    | 12.74 TFLOPS | 12.74 TFLOPS | 170 W   | ~8–12 W       | 360 GB/s      | ❌                  | **~$200 – $280** (eBay used listings around $220–$280) ([eBay][1])     |
| [**RTX 3060 Ti**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3060-ti.c3681)      | 8 GB     | 16.20 TFLOPS | 16.20 TFLOPS | 200 W   | ~10–15 W      | 448 GB/s      | ❌                  | **~$220 – $300** (pre-owned listings & reports ~$220–$290) ([eBay][1]) |
| [**RTX 3070**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3070.c3674)            | 8 GB     | 20.31 TFLOPS | 20.31 TFLOPS | 220 W   | ~9–15 W       | 448 GB/s      | ❌                  | **~$240 – $300** (community price reports for used) ([Reddit][2])      |
| [**RTX 3080**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3080.c3621)            | 10 GB    | 29.77 TFLOPS | 29.77 TFLOPS | 320 W   | ~9–15 W       | 760 GB/s      | ❌                  | **~$320 – $500** (used prices reported ~$320–$500) ([Reddit][3])       |
| [**RTX 3080 Ti**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3080-ti.c3735)      | 12 GB    | 34.10 TFLOPS | 34.10 TFLOPS | 350 W   | ~12–16 W      | 912 GB/s      | ❌                  | **~$450 – $650+** (reports ~$450+) ([Reddit][2])                |
| [**RTX 3090**](https://www.techpowerup.com/gpu-specs/geforce-rtx-3090.c3622)            | 24 GB    | 35.58 TFLOPS | 35.58 TFLOPS | 350 W   | ~15–20 W      | 936 GB/s      | ❌                  | **~$600 – $800+** (pricing trend ~$600+) ([Reddit][2])            |

[1]: https://www.ebay.com/shop/used-3060?_nkw=used+3060&utm_source=chatgpt.com "Used 3060 | eBay"
[2]: https://www.reddit.com/r/pcmasterrace/comments/1npm2x7?utm_source=chatgpt.com "Just got a Xfx Mercury 9070 XT for $500..did I steal this? Lol"
[3]: https://www.reddit.com/r/buildapc/comments/1ha9m61?utm_source=chatgpt.com "Ebay RTX3080 and 3090's going for under or at 200?? (Pricing all over the place)"


## NVIDIA RTX 40 Series (Ada Lovelace)

| **GPU**                                                                                       | **CUDA** | **VRAM**             | **FP32** | **FP16** | **TDP** | **Idle** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                      |
| --------------------------------------------------------------------------------------------- | -------- | -------------------- | -------- | -------- | ------- | -------- | ------------------ | -------------------------------------------------------------------- |
| [**RTX 4060**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060.c4107)                  | 3072     | 8 GB GDDR6 128-bit   | 15.1 TF  | 15.1 TF  | 115 W   | ~7 W     | ❌                  | **~$220 – $300** (active used listings ~$230–$300) ([eBay][1])       |
| [**RTX 4060 Ti 8GB**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060-ti-8-gb.c4106)   | 4352     | 8 GB GDDR6 128-bit   | 22.1 TF  | 22.1 TF  | 160 W   | ~8 W     | ❌                  | **~$250 – $350** (used/Refurb shows ~$250–$350) ([eBay][2])          |
| [**RTX 4060 Ti 16GB**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4060-ti-16-gb.c4155) | 4352     | 16 GB GDDR6 128-bit  | 22.1 TF  | 22.1 TF  | 165 W   | ~8 W     | ❌                  | **~$280 – $380** (used 16 GB variants ~$280+) ([eBay][2])            |
| [**RTX 4070**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070.c3924)                  | 5888     | 12 GB GDDR6X 192-bit | 29.1 TF  | 29.1 TF  | 200 W   | ~10 W    | ❌                  | **~$350 – $500+** (used pricing broader range on eBay) ([eBay][3])   |
| [**RTX 4070 Super**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070-super.c4165)      | 7168     | 12 GB GDDR6X 192-bit | 35.5 TF  | 35.5 TF  | 220 W   | ~10 W    | ❌                  | **~$400 – $550+** (used listings suggest ~$400+ typical) ([eBay][3]) |
| [**RTX 4070 Ti**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4070-ti.c3950)            | 7680     | 12 GB GDDR6X 192-bit | 40.1 TF  | 40.1 TF  | 285 W   | ~11 W    | ❌                  | **~$450 – $650+** (commonly listed used) ([eBay][3])                 |
| [**RTX 4080**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4080.c3888)                  | 9728     | 16 GB GDDR6X 256-bit | 48.7 TF  | 48.7 TF  | 320 W   | ~13 W    | ❌                  | **~$700 – $1,000+** (used listings vary widely) ([eBay][3])          |
| [**RTX 4090**](https://www.techpowerup.com/gpu-specs/geforce-rtx-4090.c3889)                  | 16384    | 24 GB GDDR6X 384-bit | 82.6 TF  | 82.6 TF  | 450 W   | ~16 W    | ❌                  | **~$1,400 – $2,000+** (many used listings in this range) ([eBay][3]) |

[1]: https://www.ebay.com/shop/nvidia-geforce-rtx-4060?_nkw=nvidia+geforce+rtx+4060&utm_source=chatgpt.com "Nvidia Geforce Rtx 4060"
[2]: https://www.ebay.com/shop/used-4060?_nkw=used+4060&utm_source=chatgpt.com "Used 4060"
[3]: https://www.ebay.com/shop/rtx-4090?_nkw=rtx+4090&utm_source=chatgpt.com "Rtx 4090"


## NVIDIA RTX 50 Series (Blackwell)

| **GPU**                                                                      | **CUDA** | **VRAM**            | **FP32**     | **FP16**     | **TDP** | **Idle** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                               |
| ---------------------------------------------------------------------------- | -------- | ------------------- | ------------ | ------------ | ------- | -------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| [**RTX 5050**](https://www.techpowerup.com/gpu-specs/geforce-rtx-5050.c4220) | 2560     | 8 GB GDDR6 128-bit  | 13.17 TFLOPS | 13.17 TFLOPS | 130 W   | ~12 W    | ❌                  | **~$350 – $450** (used listings like MSI RTX 5050 ~$450) ([eBay][1])                                                          |
| [**RTX 5060**](https://www.techpowerup.com/gpu-specs/geforce-rtx-5060.c4219) | 3840     | 8 GB GDDR7 128-bit  | 19.18 TFLOPS | 19.18 TFLOPS | 145 W   | ~13 W    | ❌                  | **~$250 – $350** (used eBay listings for RTX 5060 shown ~$274) ([eBay][2])                                                    |
| [**RTX 5070**](https://www.techpowerup.com/gpu-specs/geforce-rtx-5070.c4218) | 6144     | 12 GB GDDR7 256-bit | 30.87 TFLOPS | 30.87 TFLOPS | 250 W   | ~14 W    | ❌                  | **~$500 – $600** (used eBay listings show ~$550 for RTX 5070) ([eBay][2])                                                     |
| [**RTX 5080**](https://www.techpowerup.com/gpu-specs/geforce-rtx-5080.c4190) | 10752    | 16 GB GDDR7 256-bit | 56.28 TFLOPS | 56.28 TFLOPS | 360 W   | ~15 W    | ❌                  | **~$800 – $1,200+** (used availability limited; high pricing trends) ([eBay][2])                                              |
| [**RTX 5090**](https://www.techpowerup.com/gpu-specs/geforce-rtx-5090.c4189) | 21760    | 32 GB GDDR7 512-bit | 104.8 TFLOPS | 104.8 TFLOPS | 575 W   | ~20 W    | ❌                  | **~$2,300 – $4,500+** (eBay listings show high priced flagship cards; scalpers reported significantly above MSRP) ([eBay][2]) |

[1]: https://www.ebay.com/itm/257040138024?utm_source=chatgpt.com "MSI SHADOW GeForce RTX 5050 8GB GDDR6 PCI ..."
[2]: https://www.ebay.com/t/Nvidia-Geforce/27386/bn_7023364009?utm_source=chatgpt.com "Best Nvidia Geforce"


## NVIDIA Quadro / Professional GPUs

| **Model**                                                                      | **VRAM**   | **FP16 (half)** | **FP32 (float)** | **TDP** | **Idle Power (typical)** | **Bandwidth**    | **Virtualization** | **Avg. eBay.com Used Price**                                           |
| ------------------------------------------------------------------------------ | ---------- | --------------- | ---------------- | ------- | ------------------------ | ---------------- | ------------------ | ---------------------------------------------------------------------- |
| [Quadro P5000](https://www.techpowerup.com/gpu-specs/quadro-p5000.c2864)       | 16GB       | 138.6 GFLOPS    | 8.873 TFLOPS     | 180W    | ~15–20W                  | (256-bit GDDR5X) | ✅                  | **~$300 – $450** (many listings around ~$250-$349) ([eBay][1])         |
| [Quadro P6000](https://www.techpowerup.com/gpu-specs/quadro-p6000.c2865)       | 24GB       | 197 GFLOPS      | 12.63 TFLOPS     | 250W    | ~20–25W                  | 432.8 GB/s       | ✅                  | **~$550 – $700** (common used around ~$548-$694) ([eBay][2])           |
| [Quadro GP100](https://www.techpowerup.com/gpu-specs/quadro-gp100.c2994)        | 16GB HBM2  | 20.69 TFLOPS    | 10.34 TFLOPS     | 235W    | ~25–30W                  | 732.2 GB/s       | ✅                  | **~$300-$330** (typical Quadro GP100 used price) ([eBay][3])           |
| [Quadro GV100](https://www.techpowerup.com/gpu-specs/quadro-gv100.c3066)         | 32GB HBM2  | 33.32 TFLOPS    | 16.66 TFLOPS     | 250W    | ~25–30W                  | 868.4 GB/s       | ✅                  | **~$900+** (used GV100 listings often near or above ~$900) ([eBay][3]) |
| [Quadro RTX 6000](https://www.techpowerup.com/gpu-specs/quadro-rtx-6000.c3307) | 24GB GDDR6 | 32.62 TFLOPS    | 16.31 TFLOPS     | 260W    | ~22–30W                  | 672.0 GB/s       | ✅                  | **~$1,000 – $1,399** (common used around ~$1,019-$1,390) ([eBay][4])   |

[1]: https://www.ebay.com/shop/nvidia-quadro-p5000-16gb?_nkw=nvidia+quadro+p5000+16gb&utm_source=chatgpt.com "Nvidia Quadro P5000 16GB"
[2]: https://www.ebay.com/itm/357770011779?utm_source=chatgpt.com "NVIDIA Quadro P6000 24GB Graphic Card 699-5G611-0500-210 | eBay"
[3]: https://cl.ebay.com/b/NVIDIA-NVIDIA-Quadro-NVIDIA-Computer-Graphics-Cards/27386/bn_110676354?utm_source=chatgpt.com "NVIDIA NVIDIA Quadro NVIDIA Computer Graphics Cards for sale | eBay"
[4]: https://www.ebay.com/b/NVIDIA-NVIDIA-Computer-Graphics-Cards-NVIDIA-Quadro-6000/27386/bn_7116917630?utm_source=chatgpt.com "NVIDIA NVIDIA Computer Graphics Cards NVIDIA Quadro 6000 for sale - eBay"


## NVIDIA RTX A-Series (Professional GPUs)

| **GPU**                                                                         | **VRAM**   | **FP16 (half)** | **FP32 (float)** | **TDP** | **Idle Power** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (USD)** |
| ------------------------------------------------------------------------------- | ---------- | --------------- | ---------------- | ------- | -------------- | ------------- | ------------------ | --------------------------------- |
| [RTX A2000](https://www.techpowerup.com/gpu-specs/rtx-a2000.c3820) 6GB          | 6GB GDDR6  | 7.987 TFLOPS    | 7.987 TFLOPS     | 70W     | ~7–10W         | 288 GB/s      | ✅                  | ~$300–$450 ([eBay][1])            |
| [RTX A2000 (12GB)](https://www.techpowerup.com/gpu-specs/rtx-a2000-12-gb.c3853) | 12GB GDDR6 | 7.987 TFLOPS    | 7.987 TFLOPS     | 70W     | ~7–10W         | 288 GB/s      | ✅                  | ~$575–$650 ([eBay][1])            |
| [RTX A4500](https://www.techpowerup.com/gpu-specs/rtx-a4500.c3849)              | 20GB GDDR6 | 23.65 TFLOPS    | 23.65 TFLOPS     | 200W    | ~13–18W        | 640 GB/s      | ✅                  | ~$1,295–$1,450 ([eBay][2])        |
| [RTX A5000](https://www.techpowerup.com/gpu-specs/rtx-a5000.c3748)              | 24GB GDDR6 | 27.77 TFLOPS    | 27.77 TFLOPS     | 230W    | ~10–20W        | 768 GB/s      | ✅                  | ~$1,675–$1,900 ([eBay][3])        |
| [RTX A6000](https://www.techpowerup.com/gpu-specs/rtx-a6000.c3686)              | 48GB GDDR6 | 38.71 TFLOPS    | 38.71 TFLOPS     | 300W    | ~8–12W         | 768 GB/s      | ✅                  | ~$4,250–$5,000 ([eBay][4])        |

[1]: https://www.ebay.com/shop/a2000-12gb?_nkw=a2000+12gb&utm_source=chatgpt.com "A2000 12GB | eBay"
[2]: https://www.ebay.com/shop/quadro-rtx-a4500?_nkw=quadro+rtx+a4500&utm_source=chatgpt.com "Quadro Rtx A4500"
[3]: https://www.ebay.com/shop/nvidia-rtx-a5000?_nkw=nvidia+rtx+a5000&utm_source=chatgpt.com "Nvidia Rtx A5000"
[4]: https://www.ebay.com/itm/187325705020?utm_source=chatgpt.com "NVIDIA RTX A6000 48GB GDDR6 GPU - Pro Workstation, AI, Rendering, ECC | eBay"


## NVIDIA Tesla Series

| **GPU**                                                                                       | **VRAM**   | **FP16 (half)**    | **FP32 (float)** | **TDP** | **Idle Power (typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                    |
| --------------------------------------------------------------------------------------------- | ---------- | ------------------ | ---------------- | ------- | ------------------------ | ------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------ |
| [**Tesla P4**](https://www.techpowerup.com/gpu-specs/tesla-p4.c2879)                          | 8 GB       | 89.12 GFLOPS       | 5.704 TFLOPS     | 75 W    | ~6–10 W                  | 192.3 GB/s    | ✅                  | **~$65 – $100** – Tesla P4 listings often show used cards in the $65–$100 range. ([eBay][1])                       |
| [**Tesla P40**](https://www.techpowerup.com/gpu-specs/tesla-p40.c2878)                        | 24 GB      | 183.7 GFLOPS       | 11.76 TFLOPS     | 250 W   | ~9–12 W                  | 384-bit GDDR5 | ✅                  | **~$190 – $300+** – Multiple used Tesla P40 listings available between about $180 and $300. ([eBay][2])            |
| [**Tesla P100 PCIe 12GB**](https://www.techpowerup.com/gpu-specs/tesla-p100-pcie-12-gb.c2915) | 12 GB HBM2 | 19.05 TFLOPS       | 9.526 TFLOPS     | 250 W   | ~25–27 W                 | 549.1 GB/s    | ✅                  | **~$90 – $130** – Typical used cards around ~$100+ on eBay. ([eBay][1])                                            |
| [**Tesla P100 SXM2 16GB**](https://www.techpowerup.com/gpu-specs/tesla-p100-sxm2.c3183)       | 16GB HBM2  | 21.22 TFLOPS       | 10.61 TFLOPS     | 300 W   | ~25–30 W                 | 732.2 GB/s    | ✅                  | **~$180 – $300+** – Listings vary based on adapter combos; typical range observed. ([eBay][1])                     |
| [**Tesla V100 PCIe 16GB**](https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-16-gb.c2957) | 16 GB HBM2 | 28.26 TFLOPS       | 14.13 TFLOPS     | 300 W   | ~20–30 W                 | 897.0 GB/s    | ✅                  | **~$300 – $500+** – Used listings frequently show V100 16GB cards around this range. ([eBay][1])                   |
| [**Tesla V100 PCIe 32GB**](https://www.techpowerup.com/gpu-specs/tesla-v100-pcie-32-gb.c3184) | 32 GB HBM2 | ~28.26 TFLOPS      | ~14.13 TFLOPS    | 300 W   | ~20–30 W                 | 897.0 GB/s    | ✅                  | **~$700 – $1,000+** – Larger-memory units on eBay.com trend significantly higher. ([eBay][1])                      |
| [**Tesla T4**](https://www.techpowerup.com/gpu-specs/tesla-t4.c3316)                          | 16 GB      | 65.13 TFLOPS (8:1) | 8.141 TFLOPS     | 70 W    | ~8–12 W                  | 320.0 GB/s    | ✅                  | **~$100 – $200** – Used T4 cards often appear in this range on eBay.com. ([eBay][1])                               |
| [**Tesla L4**](https://www.techpowerup.com/gpu-specs/l4.c4091)                                | 24 GB      | 30.29 TFLOPS (1:1) | 30.29 TFLOPS     | 72 W    | ~8–12 W                  | 192.3 GB/s    | ✅                  | **~$600 – $900+ (est.)** – Limited direct used eBay.com data; inference-class cards often list higher. ([eBay][1]) |

[1]: https://www.ebay.com/shop/nvidia-tesla-p4?_nkw=nvidia+tesla+p4&utm_source=chatgpt.com "Nvidia Tesla P4"
[2]: https://www.ebay.com/shop/tesla-p40-24gb?_nkw=tesla+p40+24gb&utm_source=chatgpt.com "Tesla P40 24GB"

## AMD Radeon RX 5000 Series (RDNA1)

| **GPU**                                                                                         | **VRAM**          | **FP32**    | **FP16**     | **TDP** | **Idle (Typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                                                   |
| ----------------------------------------------------------------------------------------------- | ----------------- | ----------- | ------------ | ------- | ------------------ | ------------- | ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| [**Radeon RX 5500**](https://www.techpowerup.com/gpu-specs/radeon-rx-5500.c3455)                | 4GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 110W    | ~5–8W              | 224 GB/s      | ❌                  | **~$60 – $90** – early used listings for RX 5500 variants appear around ~$60-$90 on eBay.com (e.g., pre-owned RX 5500 XT/5500 cards). ([eBay][1]) |
| [**Radeon RX 5500 XT 4GB**](https://www.techpowerup.com/gpu-specs/radeon-rx-5500-xt.c3468)      | 4GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 130W    | ~6–10W             | 224 GB/s      | ❌                  | **~$70 – $110** – eBay.com used RX 5500 XT 4GB listings often range ~$60-$110+. ([eBay][1])                                                       |
| [**Radeon RX 5500 XT 8GB**](https://www.techpowerup.com/gpu-specs/radeon-rx-5500-xt-8-gb.c3499) | 8GB GDDR6 128-bit | 5.20 TFLOPS | 10.40 TFLOPS | 130W    | ~6–10W             | 224 GB/s      | ❌                  | **~$110 – $150** – Many pre-owned RX 5500 XT 8GB listings around ~$120-$130+ on eBay.com. ([eBay][1])                                             |
| [**Radeon RX 5600 XT**](https://www.techpowerup.com/gpu-specs/radeon-rx-5600-xt.c3474)          | 6GB GDDR6 192-bit | 7.19 TFLOPS | 14.38 TFLOPS | 150W    | ~8–12W             | 288 GB/s      | ❌                  | **~$120 – $200** – eBay.com shows *RX 5600 XT* used listings commonly around ~$140-$180+, though some show higher. ([eBay][2])                    |
| [**Radeon RX 5700**](https://www.techpowerup.com/gpu-specs/radeon-rx-5700.c3437)                | 8GB GDDR6 256-bit | 7.95 TFLOPS | 15.90 TFLOPS | 180W    | ~10–15W            | 448 GB/s      | ❌                  | **~$140 – $180** – eBay.com used RX 5700 marketplace listings often around ~$150+. ([eBay][3])                                                    |
| [**Radeon RX 5700 XT**](https://www.techpowerup.com/gpu-specs/radeon-rx-5700-xt.c3339)          | 8GB GDDR6 256-bit | 9.75 TFLOPS | 19.50 TFLOPS | 225W    | ~12–18W            | 448 GB/s      | ❌                  | **~$140 – $200** – RX 5700 XT used cards commonly list around $145-$180+ on eBay.com. ([eBay][3])                                                 |

[1]: https://www.ebay.com/shop/rx-5500-xt?_nkw=rx+5500+xt&utm_source=chatgpt.com "RX 5500 XT"
[2]: https://www.ebay.com/shop/amd-radeon-rx-5600-xt?_nkw=amd+radeon+rx+5600+xt&utm_source=chatgpt.com "AMD Radeon RX 5600 XT"
[3]: https://www.ebay.com/shop/rx-5700-xt?_nkw=rx+5700+xt&utm_source=chatgpt.com "RX 5700 XT"


## AMD Radeon RX 6000 Series (RDNA2)

| **GPU**                                                                            | **VRAM**           | **FP32**     | **FP16**     | **TDP** | **Idle (Typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                                                                         |
| ---------------------------------------------------------------------------------- | ------------------ | ------------ | ------------ | ------- | ------------------ | ------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Radeon RX 6500 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6500-xt.c3850) | 4GB GDDR6 64-bit   | 5.77 TFLOPS  | 11.54 TFLOPS | 107W    | ~5–8W              | 144 GB/s      | ❌                  | **~$70 – $160** – multiple eBay.com used listings show 4GB RX 6500 XT cards commonly **~$60–$150+ USD** (e.g., $63.99–$150+). ([eBay][1])                               |
| [Radeon RX 6600](https://www.techpowerup.com/gpu-specs/radeon-rx-6600.c3696)       | 8GB GDDR6 128-bit  | 8.93 TFLOPS  | 17.86 TFLOPS | 132W    | ~6–10W             | 224 GB/s      | ❌                  | **~$140 – $200** – used RX 6600 listings typically around **$150–$180+ USD** on eBay.com (e.g., $155, $180). ([eBay][2])                                                |
| [Radeon RX 6600 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6600-xt.c3774) | 8GB GDDR6 128-bit  | 10.60 TFLOPS | 21.20 TFLOPS | 160W    | ~7–12W             | 256 GB/s      | ❌                  | **~$170 – $250** – various RX 6600 XT used listings roughly **$175–$250+ USD** on eBay.com. ([eBay][3])                                                                 |
| [Radeon RX 6650 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6650-xt.c3898) | 8GB GDDR6 128-bit  | 10.79 TFLOPS | 21.58 TFLOPS | 176W    | ~7–12W             | 280 GB/s      | ❌                  | **~$200 – $300** – limited direct data, but common used RX 6650 XT listings appear around ~$200–$300 USD on eBay.com. ([eBay][4])                                       |
| [Radeon RX 6700](https://www.techpowerup.com/gpu-specs/radeon-rx-6700.c3716)       | 10GB GDDR6 160-bit | 10.37 TFLOPS | 20.74 TFLOPS | 175W    | ~10–15W            | 320 GB/s      | ❌                  | **~$200 – $300+** – representative used RX 6700 XT (similar generation) listings often around **$270–$340** (RX 6700 used may trend similar). ([eBay][4])               |
| [Radeon RX 6700 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6700-xt.c3695) | 12GB GDDR6 192-bit | 13.21 TFLOPS | 26.42 TFLOPS | 230W    | ~12–18W            | 384 GB/s      | ❌                  | **~$250 – $350+** – used RX 6700 XT listings frequently show prices roughly **~$249–$340+ USD** on eBay.com. ([eBay][4])                                                |
| [Radeon RX 6750 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6750-xt.c3899) | 12GB GDDR6 192-bit | 13.31 TFLOPS | 26.62 TFLOPS | 250W    | ~12–18W            | 432 GB/s      | ❌                  | **~$250 – $350+** – some used listings for RX 6750 XT show ~**$270+**, suggesting similar mid-upper RDNA2 pricing. ([eBay][4])                                          |
| [Radeon RX 6800](https://www.techpowerup.com/gpu-specs/radeon-rx-6800.c3713)       | 16GB GDDR6 256-bit | 16.17 TFLOPS | 32.34 TFLOPS | 250W    | ~15–22W            | 512 GB/s      | ❌                  | **~$280 – $380** – used cards from the same generation often list **~$285–$380+ USD** on eBay.com (approximate from 6800 XT comparables and 6800 listings). ([eBay][5]) |
| [Radeon RX 6800 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6800-xt.c3694) | 16GB GDDR6 256-bit | 20.74 TFLOPS | 41.48 TFLOPS | 300W    | ~15–25W            | 512 GB/s      | ❌                  | **~$350 – $450** – common used RX 6800 XT listings around **$379–$450+ USD** on eBay.com. ([eBay][5])                                                                   |
| [Radeon RX 6900 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6900-xt.c3693) | 16GB GDDR6 256-bit | 23.04 TFLOPS | 46.08 TFLOPS | 300W    | ~18–28W            | 512 GB/s      | ❌                  | **~$400 – $600+** – used listings for RX 6900 XT often show **~$400–$600+ USD** on eBay.com. ([eBay][4])                                                                |
| [Radeon RX 6950 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-6950-xt.c3897) | 16GB GDDR6 256-bit | 23.65 TFLOPS | 47.30 TFLOPS | 335W    | ~18–30W            | 576 GB/s      | ❌                  | **~$450 – $650+** – used RX 6950 XT listings commonly around **$450–$650 USD** on eBay.com. ([eBay][6])                                                                 |

[1]: https://www.ebay.com/shop/amd-6500-xt?_nkw=amd+6500+xt&utm_source=chatgpt.com "Amd 6500 XT"
[2]: https://www.ebay.com/itm/357569961453?utm_source=chatgpt.com "ASRock Radeon RX 6600 8GB GDDR6 Graphics Card Black, Used | eBay"
[3]: https://www.ebay.com/shop/rx-660-xt?_nkw=rx+660+xt&utm_source=chatgpt.com "RX 660 XT"
[4]: https://www.ebay.com/shop/radeon-xt?_nkw=radeon+xt&utm_source=chatgpt.com "Radeon XT | eBay"
[5]: https://www.ebay.com/shop/amd-radeon-rx-6800-xt?_nkw=amd+radeon+rx+6800+xt&utm_source=chatgpt.com "AMD Radeon RX 6800 XT"
[6]: https://www.ebay.com/shop/amd-radeon-rx-6950-xt?_nkw=amd+radeon+rx+6950+xt&utm_source=chatgpt.com "AMD Radeon RX 6950 XT | eBay"


## AMD Radeon RX 7000 Series (RDNA3)

| **GPU**                                                                              | **VRAM**           | **FP32**     | **FP16**      | **TDP** | **Idle (Typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                                               |
| ------------------------------------------------------------------------------------ | ------------------ | ------------ | ------------- | ------- | ------------------ | ------------- | ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| [Radeon RX 7600](https://www.techpowerup.com/gpu-specs/radeon-rx-7600.c4153)         | 8GB GDDR6 128-bit  | 21.75 TFLOPS | 43.50 TFLOPS  | 165W    | ~7–12W             | 288 GB/s      | ❌                  | **~$160 – $230** – Used RX 7600 ended around **$170 USD** in recent eBay sold listings. ([eBay][1])                                           |
| [Radeon RX 7600 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7600-xt.c4198)   | 16GB GDDR6 128-bit | 22.57 TFLOPS | 45.14 TFLOPS  | 190W    | ~8–14W             | 288 GB/s      | ❌                  | **~$250 – $320+** – Used RX 7600 XT listings like one at **$289.99 USD** show typical current ranges. ([eBay][2])                             |
| [Radeon RX 7700 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7700-xt.c3911)   | 12GB GDDR6 192-bit | 35.17 TFLOPS | 70.34 TFLOPS  | 245W    | ~15–22W            | 432 GB/s      | ❌                  | **~$350 – $480** – eBay shows mixed used listings and price variations; typical offers often cluster around **$350–$480+**. ([eBay][3])       |
| [Radeon RX 7800 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7800-xt.c3839)   | 16GB GDDR6 256-bit | 37.32 TFLOPS | 74.64 TFLOPS  | 263W    | ~18–25W            | 624 GB/s      | ❌                  | **~$450 – $600+** – U.S. eBay used/pre-owned typical prices often seen **~$450–$550+**. ([eBay][4])                                           |
| [Radeon RX 7900 GRE](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-gre.c4156) | 16GB GDDR6 256-bit | 40.35 TFLOPS | 80.70 TFLOPS  | 260W    | ~18–25W            | 576 GB/s      | ❌                  | **~$450 – $650** – Used GRE variants likely track similar to other RX 7900 series pricing (e.g., XT) on eBay.com. ([eBay][5])                 |
| [Radeon RX 7900 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xt.c3912)   | 20GB GDDR6 320-bit | 51.48 TFLOPS | 102.96 TFLOPS | 300W    | ~20–30W            | 800 GB/s      | ❌                  | **~$600 – $800+** – Pre-owned listings often show around **$600–$800+ USD** on eBay.com. ([eBay][5])                                          |
| [Radeon RX 7900 XTX](https://www.techpowerup.com/gpu-specs/radeon-rx-7900-xtx.c3941) | 24GB GDDR6 384-bit | 61.39 TFLOPS | 122.78 TFLOPS | 355W    | ~20–35W*           | 960 GB/s      | ❌                  | **~$690 – $1,300+** – Used reference editions have been listed near **$690 USD**, while higher-end OC units approach **$1,300+**. ([eBay][6]) |

[1]: https://www.ebay.com/itm/389341971269?utm_source=chatgpt.com "AMD Radeon RX 7600 | eBay"
[2]: https://www.ebay.com/itm/177496579703?utm_source=chatgpt.com "AMD Radeon RX 7600 XT 16GB – With Box, Tested & Working | eBay"
[3]: https://www.ebay.com/shop/7700-xt?_nkw=7700+xt&utm_source=chatgpt.com "7700 XT"
[4]: https://www.ebay.com/shop/7800-xt-graphics-card?_nkw=7800+xt+graphics+card&utm_source=chatgpt.com "7800 XT Graphics Card"
[5]: https://www.ebay.com/shop/radeon-rx-7900-xt?_nkw=radeon+rx+7900+xt&utm_source=chatgpt.com "Radeon RX 7900 XT"
[6]: https://www.ebay.com/itm/389470601371?utm_source=chatgpt.com "AMD Radeon RX 7900 XTX 24GB Reference Edition Graphics Card | eBay"


## AMD Radeon RX 9000 Series (RDNA4)

| **GPU**                                                                                           | **VRAM**   | **FP16 (half)** | **FP32 (float)** | **TDP**  | **Idle Power (typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------- | ---------- | --------------- | ---------------- | -------- | ------------------------ | ------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [AMD Radeon RX 9600](https://www.techpowerup.com/gpu-specs/radeon-rx-9060.c4326)                  | 8GB GDDR6  | ~42.9 TFLOPS    | ~21.4 TFLOPS     | ~132W    | ~10–15W                  | 288 GB/s      | ❌                  | **~$250 – $350** – while direct used listings are sparse, similar RX 9000-series boards suggest this rough range on eBay.com based on market pricing trends and adjacent model data.([eBay][1]) |
| [AMD Radeon RX 9060 XT 8GB](https://www.techpowerup.com/gpu-specs/radeon-rx-9060-xt-8-gb.c4251)   | 8GB GDDR6  | 51.3 TFLOPS     | 25.6 TFLOPS      | 150W     | ~12–18W                  | 320 GB/s      | ❌                  | **~$280 – $380** – eBay.com shows various used/near-new RX 9060 XT 8GB listings (e.g., Gigabyte ~**$299.99 USD** for used) suggesting a ~low-$300s range.([eBay][2])                            |
| [AMD Radeon RX 9060 XT 16GB](https://www.techpowerup.com/gpu-specs/radeon-rx-9060-xt-16-gb.c4293) | 16GB GDDR6 | 51.3 TFLOPS     | 25.6 TFLOPS      | 160W     | ~12–18W                  | 320 GB/s      | ❌                  | **~$360 – $550** – eBay.com used listings for 9060 XT 16GB show examples around **~$425–$480 USD** (pre-owned); higher end reflects condition/brand.([eBay][3])                                 |
| [AMD Radeon RX 9070](https://www.techpowerup.com/gpu-specs/radeon-rx-9070.c4250)                  | 16GB GDDR6 | 72.25 TFLOPS    | 36.13 TFLOPS     | 220W     | ~18–28W                  | ~640–896 GB/s | ❌                  | **~$450 – $650+** – similar RX 9070 eBay.com used listings and comparative search results suggest typical used prices around **$500+ USD**.([eBay][4])                                          |
| [AMD Radeon RX 9070 XT](https://www.techpowerup.com/gpu-specs/radeon-rx-9070-xt.c4229)            | 16GB GDDR6 | 97.32 TFLOPS    | 48.66 TFLOPS     | 260–304W | ~20–30W                  | 640 GB/s+     | ❌                  | **~$600 – $800+** – eBay.com has *used/pre-owned* RX 9070 XT listings (e.g., PowerColor ~**$699 USD**) with a broad range depending on condition.([eBay][1])                                    |

[1]: https://www.ebay.com/shop/amd-rx-9070-xt?_nkw=amd+rx+9070+xt&utm_source=chatgpt.com "Amd RX 9070 XT"
[2]: https://www.ebay.com/itm/406557591590?utm_source=chatgpt.com "Gigabyte Radeon RX 9060 xt 8GB GDDR6X Graphics Card GV- ..."
[3]: https://www.ebay.com/p/6085827196?utm_source=chatgpt.com "SAPPHIRE PULSE AMD Radeon RX 9060 XT Gaming OC 16GB ..."
[4]: https://www.ebay.com/b/SAPPHIRE-AMD-Computer-Graphics-Cards/27386/bn_7113421085?utm_source=chatgpt.com "SAPPHIRE AMD Computer Graphics Cards for sale"



## AMD Pro/Compute GPUs

| **GPU**         | **VRAM**  | **FP16 (half)** | **FP32 (float)** | **TDP** | **Idle Power (typical)** | **Bandwidth** | **Virtualization** | **Avg Used eBay.com Price (≈)**            |
| ----------------------------- | --------- | --------------- | ---------------- | ------- | ------------------------ | ------------- | ------------------ | ----------------------------------------- |
| [Radeon Instinct MI25](https://www.techpowerup.com/gpu-specs/radeon-instinct-mi25.c2983) | 16GB HBM2 | 24.58 TFLOPS | 12.29 TFLOPS | 300W | ~30–40W | 436.2 GB/s | 🟡 | **~$90 – $180** ([eBay][1]) |

[1]: https://www.ebay.com/p/17070539862?utm_source=chatgpt.com "AMD Radeon Instinct MI25 16GB HBM2 GPU AI HPC Accelerator Card 102D0513300 for sale online | eBay"



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


