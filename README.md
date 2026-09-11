# RASPBERRY-PI-AI-HAT 2026-09
## The AI HAT+ 2 setting up
RaspberryPiのカーネルとファームウェアの自動更新を止めた｜yoshiteru  
$ sudo apt-mark hold raspberrypi-kernel  
$ sudo apt-mark hold firmware*  
hold -> unhold  
uname -a  
pi@AI-HATplus2:~ $ uname -a  
Linux AI-HATplus2 6.12.93+rpt-rpi-2712 #1 SMP PREEMPT Debian 1:6.12.93-1+rpt1 (2026-06-12) aarch64 GNU/Linux  
AI software - Raspberry Pi Documentation  
https://www.raspberrypi.com/documentation/computers/ai.html  
sudo apt update  
sudo apt full-upgrade -y  
sudo rpi-eeprom-update -a  
sudo reboot  
sudo apt install dkms  
sudo apt install hailo-all  
  
https://github.com/gregm123456/raspberry_pi_hailo_ai_services/blob/main/reference_documentation/system_setup.md  
Option B: Install 5.3.0 from Hailo dev-public (recommended — latest)  

Download and install the three .deb packages for aarch64:
# Download packages
wget https://dev-public.hailo.ai/2026_04/Hailo10/hailort-pcie-driver_5.3.0_all.deb
wget https://dev-public.hailo.ai/2026_04/Hailo10/hailort_5.3.0_arm64.deb
wget https://dev-public.hailo.ai/2026_04/Hailo10/hailo-tappas-core_5.3.0_arm64.deb

# Install in order (driver first)
sudo apt install ./hailort-pcie-driver_5.3.0_all.deb
sudo apt install ./hailort_5.3.0_arm64.deb
sudo apt install ./hailo-tappas-core_5.3.0_arm64.deb

sudo reboot
$ hailortcli fw-control identify

dmesg | grep -i hail
sudo apt-mark hold firmware*

The Python wheel for service venvs:
# Per isolated venv — run once per service venv that needs hailo_platform
sudo /opt/hailo-{service}/venv/bin/python3 -m pip install \
  https://dev-public.hailo.ai/2026_04/Hailo10/hailort-5.3.0-cp313-cp313-linux_aarch64.whl


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
