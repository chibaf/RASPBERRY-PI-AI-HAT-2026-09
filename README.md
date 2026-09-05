# RASPBERRY-PI-AI-HAT 2026-09
## The AI HAT+ 2 setting up
<ul>
  sudo apt install dkms<br>
  sudo apt install hailo-h10-all<br>
  <img width="537" height="173" alt="image" src="https://github.com/user-attachments/assets/f71ec73f-5ab3-4005-a56b-8b43edf25b76" />
</ul>

## remarks
The AI HAT+ 2 is auto-detected as PCIe Gen 3, which it needs for full speed. If a check shows it running at Gen 2, set it explicitly by adding dtparam=pciex1_gen=3 to /boot/firmware/config.txt (or use the PCIe Speed option under Advanced in sudo raspi-config) and reboot.  
  
## references
Getting started - Raspberry Pi Documentation  
https://www.raspberrypi.com/documentation/computers/getting-started.html  
  
Buy a Raspberry Pi AI HAT+ 2 – Raspberry Pi  
https://www.raspberrypi.com/products/ai-hat-plus-2/  

hailo-ai/hailo-apps  
https://github.com/hailo-ai/hailo-apps  
  
Raspberry Pi AI HAT+ 2: Setup, Object Detection & LLMs  
https://pidiylab.com/raspberry-pi-ai-hat-plus-2/  
  
AI HAT +2 not detected - Raspberry Pi Forums  
https://forums.raspberrypi.com/viewtopic.php?t=395534
