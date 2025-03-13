# Advantech MIC-AI Product Series

Advantech AI Edge Solutions – MIC Jetson series, powered by full NVIDIA® Jetson™ platform, which gets all the performance of a GPU workstation in an embedded module.Featuring strict validation to ensure thermal, mechanical, and electrical compatibility, plus industrial-grade anti-vibration, high temperature operation capabilities, and modular, compact-sized design, Advantech’s MIC Jetson series are perfect hardware platforms for the surveillance, transportation, and manufacturing sectors.

![](https://advcloudfiles.advantech.com/cms/b57dfa32-3b50-46fc-8930-6475dd67fd3e/Content/og.jpg)

## Visit MIC-AI Product Series

- [AI Developer Kit, Solution Kit & Peripheral](https://www.advantech.com/en/products/ai-developer-kit-solution-kit--peripheral/sub_d843578f-4f6f-41b1-aa5a-fdfdbdcd7d2b)
- [AI Computer Systems](https://www.advantech.com/en/products/ai-computer-systems/sub_965e4edb-fb98-429e-89ed-9a0a8435a7be)
- [AI Rugged System & AI NVR](https://www.advantech.com/en/products/ai-rugged-system-ai-nvr-/sub_7514cce2-46ae-4b55-ac6d-b9698a6fb448)
- [AI Camera](https://www.advantech.com/en/products/ai-camera/sub_ce666c81-b9fc-4675-b7aa-0c16ce758636)
- [AI IGX System](https://www.advantech.com/en/products/ai-igx-system/sub_f5ae6d7f-14c2-4c4d-b027-448808aba483)

## Resources for MIC-AI Product Series

Partners and users of the MIC-AI Product Series can find comprehensive resources—including BSPs, reflashing SOPs, release notes, and more—in this repository's [wiki](https://github.com/advantech-edge-ai/MIC-AI/wiki) (_under construction, for now please use the table below_).

📌 For quick access to frequently downloaded resources, refer to the table below.


## AI Applications on MIC-AI: Advantech Edge AI and More

The MIC-AI Product Series is designed to support a wide range of AI applications, making it easier to deploy and optimize models at the edge. To help users get started, the [Advantech Edge AI](https://github.com/advantech-EdgeAI/) provides several production-ready applications that can be readily installed and used.

### Deploying DeepSeek

DeepSeek is a powerful AI model that can be installed and deployed on MIC-AI devices. Follow the steps below to set up DeepSeek on your MIC-AI system:

1. Make NVIDIA's Jetson apt source available
   ```sh
   gedit /etc/apt/sources.list.d/nvidia-l4t-apt-source.list
   ```
   Uncomment the lines as the following:
   ```sh
   deb https://repo.download.nvidia.com/jetson/common r36.3 main
   deb https://repo.download.nvidia.com/jetson/t234 r36.3 main
   deb https://repo.download.nvidia.com/jetson/ffmpeg r36.3 main
   ```
2. Manually install cuda, tensorrt, opencv, and Docker
   ```sh
   sudo apt-get update
   sudo apt-get install nvidia-l4t-dla-compiler
   sudo apt-get install nvidia-cuda-dev nvidia-tensorrt-dev nvidia-vpi-dev nvidia-opencv-dev nvidia-cudnn-dev tensorrt
   sudo apt-get install apt-utils
   sudo curl https://get.docker.com | sh && sudo systemctl --now enable docker
   sudo systemctl restart docker
   ```
   If Docker cannot start up successfully due to network/firewall issues, please try to configure the firewall setting to legacy:
   ```sh
   sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
   sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
   ```
3. Install Ollama and run deepseek-r1
   ```sh
   curl -fsSL https://ollama.ai/install.sh > install.sh
   sudo sh install.sh
   ollama –version
   export OLLAMA_HOST=127.0.0.1:11434
   ollama pull deepseek-r1:1.5b
   ollama run deepseek-r1:1.5b --keepalive 1h --verbose
   ```
For more AI applications and ready-to-use solutions, visit the [Advantech Edge AI](https://github.com/advantech-EdgeAI/).
