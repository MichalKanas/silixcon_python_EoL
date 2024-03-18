# silixcon_python_EoL

Welcome to the silixcon_python_EoL documentation! This repository provides an EXAMPLE of production scripts built around siliXcon SWTools for seamless integration and control of siliXcon devices using Python.

## A little background of the scripts:

The scripts are a small part of the scripts used in siliXcon production. The script was modified to work without other proprietary tools from siliXcon manufacturing.

This means that the scripts are not used by siliXcon, because siliXcon has an internal copy. Their purpose is an example, that you can automate things using Python and SWTools. If you want to use the scripts as they are, you may need some work on them. **The scripts are not maintained, but you can use them as a starting point for your own scripts.**

## Getting Started

Connect siliXcon controller and run the example.py script provided in this repository. This script demonstrates the usage of various functions and showcases the capabilities of the production scripts.

```bash
python example.py
```

## Description

The core components of this repository are the swtools.py and yos_device.py scripts. These scripts serve as wrappers around the siliXcon SWTools, enabling you to utilize Python functions for efficient control and interaction with siliXcon devices.

## Include in PYTHONPATH:

For easy accessibility from any location, consider adding the path to the `swtools.py` and `yos_device.py` scripts to the PYTHONPATH environmental variable.
## setup guide 
Whether you're a seasoned developer or just starting out, we've made managing siliXcon devices easy. With swtools.py, you're holding the key to unlocking powerful configurations, analyzing device data , and solving mysteries with our diagnostic tools. Let's dive in!
 ## Configuring Your Device

## Advanced Device Configuration, Data Analysis, and Diagnostics

# Overview

This documentation serves as a comprehensive guide for utilizing our suite of Python scripts designed to enhance your interaction with siliXcon devices. These scripts, including `swtools.py`, `yos_device.py`, and `example.py`, offer a wide range of functionalities from device configuration to data analysis and diagnostics. Our goal is to facilitate seamless integration and effective management of siliXcon devices within your operational environment.


## Getting Started

### Prerequisites

Ensure your Python environment is correctly set up and that you have access to the siliXcon devices you intend to manage.

### Running the Scripts

- **Setup**: Familiarize yourself with the scripts and the functionalities they offer as outlined above.
- **Execution**: Utilize the command line or an integrated development environment (IDE) to run the scripts. For specific functions, refer to the detailed instructions provided in the subsequent sections.

## Detailed Instructions

## Overview

Welcome to the siliXcon Device Management Toolkit! This guide is designed specifically for new users, providing all the necessary information to get started with our Python scripts. These tools, including `swtools.py`, `yos_device.py`, and `example.py`, offer functionalities ranging from device configuration and data analysis to diagnostics, ensuring you can effectively manage siliXcon devices in your operational environment.

## Features at a Glance

### `swtools.py`

- **Device Configuration (`configure_device`)**: Customize your device's settings, including network configurations and operational modes.
- **Data Processing (`process_device_data`)**: Turn raw data from your device into actionable insights.
- **Diagnostics (`diagnose_device`)**: Identify and fix device issues to maintain optimal performance.

### `yos_device.py`

- **Device Initialization (`init_device`)**: Start communicating with your siliXcon devices by initializing them.
- **Sensor Data Acquisition (`read_sensor_data`)**: Gather data from your device's sensors for monitoring or analysis.
- **Device Control (`write_device_control`)**: Send commands to your devices to activate specific functions or change settings.

### `example.py`

- **Integration Demonstration**: Learn how to use `swtools.py` and `yos_device.py` together, from initializing to diagnosing your devices.

# Getting Started with SWTools

## Prerequisites

Ensure you're ready to begin by confirming the following:

- Your Python environment is up and running.
- You have access to the siliXcon devices you wish to manage.

## Overview of Running the Scripts

Familiarize yourself with the scripts to maximize their potential:

- **Setup**: Understand the functionalities provided by each script.
- **Execution**: Utilize the command line or an Integrated Development Environment (IDE) for script execution. Detailed instructions for each script are provided below to cater to your specific needs.

## Detailed Instructions for New Users

### Setting Up Your Device for Optimal Performance

Configure your device for the best results:

1. **Prepare the Environment**: Open `swtools.py` with your preferred text editor.
2. **Configuration**:
   - Locate the `configure_device` function to start customizing your device's settings.
   - Replace `device_id` with the unique identifier of your device.
   - Substitute `settings` with your desired configurations. For available settings, refer to the script comment labeled `# Device settings options`.

### Interpreting Your Device's Data

Transform and understand your device's data:

1. **Access the Interpreter**: Find the `process_device_data` function in `swtools.py`.
2. **Data Input**: Change `data` to the actual data retrieved from your device.
3. **Execution**: Run the script to convert your data into an easily understandable format.

### Diagnosing and Resolving Device Issues

Identify and fix potential device issues:

1. **Initiate Diagnostics**: Locate `diagnose_device` in `swtools.py`, serving as the health check tool for your device.
2. **Device Identification**: Enter your device's identifier to commence diagnostics.
3. **Analysis and Fixes**: Execute the script and review the generated report for any detected issues along with their recommended solutions.

### Integrating Functions with `example.py`

To observe the scripts in action:

1. **Environment Setup**: Open a terminal or command prompt.
2. **File Navigation**: Move to the directory containing `example.py` using `cd path/to/your/folder`.
3. **Script Execution**: Launch `python example.py` to start the integrated script sequence—configuring a device, processing its data, and performing diagnostics.
4. **Review**: Examine the outcomes for a comprehensive understanding of how the scripts operate together.

## Script Functionality Overview

The `swtools.py` script encompasses a variety of functions aimed at device management and data processing, such as:

- **Command Execution Without Output**: `run_no_output(command)` executes a given command without producing any output.
- **Command Execution with Returned Output**: `run_ret_output(command)` executes a given command and returns its output for further processing.
- **Interface Validation**: `interface_valid(interface)` confirms if the specified interface is supported.
- **Interface Conversion**: `convert_if_to_num(interface)` translates an interface designation from a string to a numeric value.
- **Configuration Parsing**: `parse_msgconf_from_string(conf)` interprets message configuration settings from a string format into a structured dictionary.

Additional details on managing connection options, executing various diagnostics, and performing device configuration are encapsulated within the `swtools` class and its associated methods.

By replacing placeholders like `device_id`, `settings`, and `data` with actual values pertinent to your setup, you can leverage the full potential of the SWTools for efficient device management.
