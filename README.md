# RASPBERRY-PI-AI-HAT 2026-09
## The AI HAT+ 2 setting up
<ul>
```bash  
cd ~  
git clone https://github.com/TechMind428/RPi_AI_HAT-2.git  
mkdir -p ~/scripts  
cp ~/RPi_AI_HAT-2/scripts/* ~/scripts/  
chmod +x ~/scripts/*.sh  
```  
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
  
Raspberry Pi 5 llama.cpp: Local LLM Setup Guide   
https://pidiylab.com/raspberry-pi-5-llama-cpp-local-llm-install-setup/  
  
hailo-ai/hailo-rpi5-examples  
https://github.com/hailo-ai/hailo-rpi5-examples  
