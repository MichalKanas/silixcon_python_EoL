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

## Overview

Welcome to the siliXcon Device Management Toolkit! This guide is designed specifically for new users, providing all the necessary information to get started with our Python scripts. These tools, including `swtools.py`, `yos_device.py`, and `example.py`, offer functionalities ranging from device configuration and data analysis to diagnostics, ensuring you can effectively manage siliXcon devices in your operational environment.


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

# Function and Class Overview

This documentation outlines the functions and classes available in the script, focusing on their purposes and usage within the context of managing and automating device interactions.

## Functions

### `run_no_output(command)`
Executes a command without returning any output to the caller. It captures both stdout and stderr internally.

### `run_ret_output(command)`
Executes a command and returns its output, capturing both stdout and stderr. Output is returned in a format that includes line breaks.

### `run_std(command)`
Executes a command and specifically handles stderr output, printing a message if the command fails. It also prints the return code of the command execution.

### `run_check(command, ret_val=0, stdin=None)`
Executes a command and checks its return value against a specified `ret_val`. If the return value does not match, it prints the command output and the expected vs. actual return values.

### `run_ch(command, ret_val)`
Similar to `run_check` but designed for continuous handling. It prints the output line by line as it's being executed and checks if the return value matches `ret_val`.

### `get_swtools_path()`
Determines the path to the `swtools` directory by looking for the `term` command. Raises `SwtoolsError` if not found.

### `interface_valid(interface)`
Checks if a given interface is valid among a predefined set of interfaces.

### `convert_if_to_num(interface)`
Converts interface names to their corresponding numerical representations.

### `parse_msgconf_from_string(conf)`
Parses a configuration string into a dictionary for message configuration.

## Class `swtools_connection_options`
Handles connection options for the swtools, allowing the setting of interface, address, and message configuration.

### Methods
- `set_if(interface)`: Sets the interface for connection options.
- `update_msgconf(msgconf_str)`: Updates the message configuration from a string.
- `get_if()`: Retrieves interface-related options for command execution.

## Class `swtools`
Facilitates interaction with devices, including executing commands and handling configurations.

### Methods
- `get_options(add_login=True)`: Retrieves a list of options for command execution.
- `srm_upgrade(swid="")`: Performs an SRM upgrade with the specified software ID.
- `login()`: Executes the login procedure for a device.
- `yosctl_ret_std(data, check=True)`: Executes a yosctl command and returns its standard output.
- `yosctl_parse(data=["id", "info", "name"], attempts=1)`: Parses output from a yosctl command.
- `get_vars_from_list(vars_list)`: Retrieves variables from a list and returns them as a dictionary.
- `get_vars(prefix="/vars/o_")`: Retrieves variables based on a prefix.
- `script_check(file, ret_val=0)`: Checks the execution of a script file.
- `script_std(file)`: Executes a script and handles its standard output.
- `yosctl(cmd)`: Executes a yosctl command without returning output.
- `yosctl_check(cmd, ret_val=0, attempts=1)`: Checks a yosctl command execution.
- `claim()`: Claims the interface for device communication.
- `yosctl_push(file="", stdin=None)`: Pushes variables or configurations to the device.
- `yosctl_pull(file="", non_default_values=False, type="")`: Pulls variables or configurations from the device.
- `yosctl_cmd_exec(cmd=[])`: Executes a command with yosctl.
- `cmd(cmd, exit_code=12345, asyn=False)`: Executes a command and checks for a specific exit code.

### Utility Functions

#### `resetconn()`
Resets the network connections by calling the `resetconn` system command.

## Error Handling

### Class `SwtoolsError`
A custom exception class for handling errors within the swtools script.

## Using `swtools_connection_options`

- Initialize with connection settings: `swtools_connection_options(interface, addr, msgconf_str)`.
- Update connection settings: `set_if(interface)`, `update_msgconf(msgconf_str)`.

## Automating with `swtools` Class

- Initialize `swtools` with connection options.
- Manage device configurations and execute scripts: `srm_upgrade(swid)`, `login()`, `yosctl_ret_std(data, check)`, `yosctl_parse(data, attempts)`.
- Retrieve and manage device variables: `get_vars_from_list(vars_list)`, `get_vars(prefix)`.
- Execute and check scripts and commands: `script_check(file, ret_val)`, `script_std(file)`, `yosctl(cmd)`, `yosctl_check(cmd, ret_val, attempts)`.
- Handle device claims and configurations: `claim()`, `yosctl_push(file, stdin)`, `yosctl_pull(file, non_default_values, type)`, `yosctl_cmd_exec(cmd)`.
- Custom command execution: `cmd(cmd, exit_code, asyn)`.

## Utility Function

- Reset connections: `resetconn()`.

## Example Usage

- To automate firmware updates, use `srm_upgrade` with the software ID.
- Configure device settings via `yosctl_push` and `yosctl_pull` for configuration management.
- Fetch and manage device variables with `get_vars` or `get_vars_from_list`.