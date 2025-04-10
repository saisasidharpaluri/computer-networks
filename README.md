# Go-Back-N Protocol Simulation

This project is an interactive web-based simulation of the Go-Back-N ARQ (Automatic Repeat reQuest) protocol, which is a data link layer protocol used for reliable data transmission over unreliable communication channels.

## Overview

The simulation visualizes the Go-Back-N protocol with the following features:
- Configurable number of packets
- Adjustable window size
- Customizable timeout settings
- Variable animation speed
- Different error modes (none, random, manual)
- Interactive packet transmission visualization
- Detailed simulation log

## Installation

No installation is required as this is a browser-based application using HTML, CSS, and JavaScript.

### Prerequisites
- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled in your browser

## Project Structure

```
project_root/
├── simulation.html        # Main HTML file
├── js/
│   └── simulation.js      # JavaScript implementation of the simulation
├── css/
│   └── styles.css         # CSS styling (if applicable)
└── README.md              # This file
```

## How to Run the Simulation

### Method 1: Direct File Opening
1. Ensure all project files are in their correct folders as shown in the project structure.
2. Double-click on `simulation.html` to open it in your default web browser.

### Method 2: Using Local Server (Recommended)
1. Open a terminal/command prompt in the project root directory.
2. If you have Python installed:
   - For Python 3.x: `python -m http.server`
   - For Python 2.x: `python -m SimpleHTTPServer`
3. If you have Node.js installed:
   - Install `http-server` by running: `npm install -g http-server`
   - Start the server: `http-server`
4. Open your browser and navigate to `http://localhost:8000/simulation.html` (or the port specified by your server).

### Method 3: Using VSCode
1. Install the "Live Server" extension in VSCode.
2. Right-click on `simulation.html` in the VSCode file explorer.
3. Select "Open with Live Server".

## Using the Simulation

1. Configure the simulation parameters:
   - Packet Count: Number of packets to send
   - Window Size: Size of the sliding window
   - Timeout: Time before retransmitting packets (5000-100000ms)
   - Animation Speed: Speed of the visual animations
   - Error Mode:
     - None: No errors
     - Random: Random ACK failures based on error rate
     - Manual: Click on packets in transit to simulate errors

2. Simulation Controls:
   - Start: Begin the simulation
   - Pause/Resume: Temporarily halt or continue the simulation
   - Reset: Return the simulation to its initial state
   - Clear Log: Remove all entries from the simulation log

## Protocol Behavior

In this implementation of Go-Back-N:
- The sender sends packets within the current window without waiting for individual acknowledgments.
- All packets in the window are sent before any acknowledgments are processed.
- Packets always reach the receiver, but ACKs may fail to reach the sender (in random error mode).
- If an ACK is lost, a timeout will occur and the sender will retransmit all packets in the window.
- The window slides forward as packets are acknowledged.

## Troubleshooting

If the simulation doesn't appear correctly:
- Ensure JavaScript is enabled in your browser
- Check the browser console for any errors
- Verify all files are in the correct directory structure
- Try using a different modern browser

## Further Development

To modify or extend the simulation:
- The main logic is contained in `js/simulation.js`
- Parameter configurations can be adjusted in the configuration section
- The visual appearance can be modified via CSS 