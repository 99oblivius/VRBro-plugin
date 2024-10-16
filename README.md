# VRBro Plugin for OBS Studio

![VRBro Banner](assets/VRBro_banner.png)

## Introduction

VRBro Plugin is an OBS Studio plugin designed to bridge the gap between virtual reality and content creation. 
It works in tandem with a SteamVR overlay application to provide seamless control of OBS Studio directly from within VR.
This plugin was built with multi-PC streaming setups in mind ([refer bellow](#Usage)). 

## Features

- Creates and manages a simplified WebSocket server for fast, performant control of OBS from in-game VR environments
- Enables VR users to control OBS functions without leaving their VR experience
- Supports various OBS actions such as starting/stopping streaming, recording, and replay buffer
- Provides a user-friendly settings interface within OBS Studio

## Installation

1. Download the latest release of the VRBro Plugin from the [Releases](https://github.com/99oblivius/VRBro-plugin/releases) page.
2. Run the installer or extract the contents of the zip file to your OBS Studio plugins folder:
   - Windows: `C:\Program Files\obs-studio\`
   - Linux: Differing OBS Studio installation methods will have different installation paths.  
*e.g.* On an Arch system where OBS Studio was compiled and installed manually, `/usr/lib/obs-plugins/` and `/usr/share/obs/obs-plugins/` will be your folders of interest. `~/.config/obs-studio/plugins` is another valid path.
3. Restart OBS Studio.

## Usage

1. Launch OBS with VRBro plugin installed  
   - Configure the plugin in `Tools -> VRBro Server Settings`  
     - Optionally set listen address to 0.0.0.0 to receive commands from another computer running the overlay. Simply configure the overlay's host IP to point to your streaming computer, and create a firewall rule on your streaming computer to allow the port (*default: 33390*) through.  
   - To monitor for issues go to `Help -> Log Files -> View Current Log`
3. Launch SteamVR.
4. Launch VRBro Overlay.
5. Use your VR controller bindings to send commands to OBS.

## GUI

![VRBro GUI](assets/VRBro_Server_Settings.png)

## Configuration

1. In OBS Studio, go to Tools > VRBro Server Settings.
2. Enable the "Auto Buffer" feature to automatically start the replay buffer when OBS loads, if desired.
3. Optionally, set a custom listening address and port for the WebSocket server.

## How It Works

1. The VRBro Plugin sets up a WebSocket server within OBS Studio.
2. A companion SteamVR overlay application (sold separately) connects to this WebSocket server.
3. VR users can configure their VR controller bindings to send commands to OBS via the overlay.
4. The plugin receives these commands and executes the corresponding actions in OBS Studio using the Frontend API.

## Supported Commands

- Start/Stop Streaming
- Start/Stop Recording
- Start/Stop Replay Buffer
- Save Replay Buffer
- Split Recording File

## Contributing & Feedback

Contributions and or issues are welcome! Feel free to submit a Pull Request.

## Acknowledgements

- OBS Studio team for their excellent software and API
- Asio and nlohmann/json library authors
