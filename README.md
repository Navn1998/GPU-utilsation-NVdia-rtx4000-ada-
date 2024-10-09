# GPU-utilsation-NVdia-rtx4000-ada
# GPU Monitoring Script

This script allows continuous monitoring of an NVIDIA GPU along with system resources such as vCPU usage and memory utilization. The metrics are logged to a file (`gpu_metrics.log`) with a timestamp for later analysis. It provides information on:

- GPU Utilization (%)
- GPU Memory Usage (MB)
- GPU Temperature (°C)
- vCPU Usage (%)
- System Memory Usage (%)

## Prerequisites

Before using this script, make sure you have the following installed on your system:

1. **NVIDIA GPU Drivers**: Ensure that your system has the appropriate NVIDIA drivers installed.
2. **nvidia-smi**: This command-line utility comes with the NVIDIA driver and is used to gather GPU metrics.
3. **Basic Linux Utilities**: Utilities such as `top`, `free`, and `bash` must be available, which are typically included in most Linux distributions.

Installing Nvidia drivers if not already done: 
  `sudo apt update`
  `sudo apt install nvidia-driver-525  # Change '525' to the appropriate version for your system`
  `sudo reboot`

SETUP INSTRUCTIONS: 

`git clone https://github.com/Navn1998/gpu-monitoring-script.git`
`cd gpu-monitoring-script
`
Make script executable: 
`chmod +x gpu_monitor.sh`

Run the script in the background: 
`./gpu_monitor.sh &`

View logs: 
`tail -f gpu_metrics.log`

Stop the script once done:
`killall gpu_monitor.sh`

Sample output: 
`Timestamp, GPU Utilization (%), Memory Usage (MB), GPU Temperature (C), vCPU Usage (%), Memory Usage (%)
2024-10-09 15:12:30, 45, 2048, 70, 15.2, 40.3`

Customization
You can adjust the frequency at which metrics are captured by modifying the sleep interval in the script (default is 10 seconds). This can prevent logfile from occupying too much storage space. 
    `sleep 10  # Change this value for faster or slower logging interval`s

