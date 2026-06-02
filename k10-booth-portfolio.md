# Portfolio: The K10 Polaroid Photo Booth
**Client:** Personal / Woodhead Tech Showcase
**Date:** June 2026
**Technologies:** ESP32-S3, MicroPython, FastAPI, Python (PIL/Pillow), WebSockets, HTML5/CSS3

## The Challenge
For Robert "Ender" Woodward's high school graduation, I wanted to create an interactive experience that captured the "analog" nostalgia of polaroid cameras with the seamlessness of modern digital sharing. The goal was to build a fleet of handheld cameras that would instantly push live, formatted photos to a "gallery wall" displayed at the venue.

## The Solution
I engineered a custom IoT ecosystem using the **UniHiker K10**, an ESP32-S3 based board with an integrated camera and screen. 

### 1. Embedded Firmware (MicroPython)
The firmware was developed to handle the constraints of the ESP32-S3's parallel bus. Key technical hurdles included:
- **DMA Synchronization:** Coordinating the camera's continuous Direct Memory Access (DMA) with screen draws to prevent system hangs.
- **Hardware Resource Management:** Solving a conflict where the physical A/B buttons were shared with the camera's parallel bus, necessitating a move to touch-based triggers and the HOME button.
- **Power Efficiency:** Implementing a synchronous touch-poll loop that maintained responsiveness without starving the WiFi radio.

### 2. High-Signal Processing (FastAPI Server)
The backend server, built with **FastAPI**, served as the central hub for the fleet.
- **Raw Image Decoding:** The K10 transmits raw RGB565 frames to minimize on-device processing. The server uses **Pillow (PIL)** to decode these 153,600-byte buffers into standard RGB.
- **Dynamic Polaroid Generation:** Each photo is center-cropped to a 3:4 portrait ratio, mounted on a digital white frame, and captioned with event-specific metadata. A slight random rotation (±4.5°) is applied to each image to enhance the "physical photo" aesthetic.
- **Real-Time Distribution:** **WebSockets** were used to broadcast new photos to all connected clients instantly.

### 3. The Live Gallery
The front-end is a high-performance masonry grid designed for "TV-as-a-canvas" deployment.
- **Visual Feedback:** New photos "slide in" with a drop animation, immediately capturing the attention of guests.
- **Performance:** Optimized for dozens of simultaneous uploads, handling the live feed of 6+ cameras without latency.

## Results
The project successfully deployed at the graduation ceremony, providing a unique, low-friction way for guests to contribute to the celebration's visual story. It has since become a centerpiece of the Woodhead Tech "Small-Scale IoT" service offering, demonstrating the ability to bridge complex embedded engineering with polished, user-facing web applications.

---
*Developed by Woodhead Tech. For inquiries on custom IoT event solutions, visit [woodhead.tech](https://woodhead.tech).*
