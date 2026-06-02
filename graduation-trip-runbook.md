# Graduation Trip Runbook: Robert "Ender" Woodward (Class of 2026)

## Overview
This runbook covers the logistics and technical execution for the graduation trip from San Antonio, TX to Everett, WA, including the ceremony live stream and the K10 Polaroid Booth deployment.

## 1. Itinerary
- **Departure (SAT -> SEA):** ~June 10-11, 2026 (Projected)
- **Graduation Ceremony:**
  - **Date:** Saturday, June 13, 2026
  - **Time:** 3:00 PM – 5:00 PM PT
  - **Location:** Angel of the Winds Arena, Everett, WA
- **Return (SEA -> SAT):** ~June 15-16, 2026 (Projected)
- **Graduation Party:**
  - **Date:** Saturday, June 27, 2026
  - **Time:** 1:00 PM – 5:00 PM CT
  - **Location:** MacArthur Park, San Antonio, TX

## 2. Parts List
### K10 Polaroid Booth
- [ ] 5-6 K10 Units (fully charged)
- [ ] USB-C charging hub + cables
- [ ] Tripods/mounts for K10s
- [ ] Spare SD cards (for local backups)

### Networking
- [ ] GL.iNet Mango Router (Travel Router)
- [ ] Ethernet cables (10ft+)
- [ ] Power bank for Mango router

### Live Stream & Media
- [ ] Laptop with OBS installed (for stream management)
- [ ] iPhone/Camera for capture
- [ ] Tripod for camera
- [ ] ESP32 Slideshow boards (3-4 units)

## 3. Pre-Departure Checklist
- [ ] **K10 Firmware:** Verify firmware v2 (self-discovery API + OTA) is installed on all units.
- [ ] **Graduation Site:** Update `VIDEO_ID` in `index.html` once the YouTube stream is scheduled.
- [ ] **Mango Router:** Test WireGuard VPN connection back to homelab.
- [ ] **Gallery Server:** Verify `booth/server.py` is running on the deployment laptop.
- [ ] **ESP32 Boards:** Flash with latest slideshow firmware and verify they connect to Mango router AP.

## 4. On-Site Setup (Everett)
- [ ] Deploy Mango router and connect to venue WiFi/Ethernet.
- [ ] Start WireGuard VPN.
- [ ] Launch `booth/server.py` on laptop.
- [ ] Position K10 units around venue and confirm they hit the gallery API.
- [ ] Set up ESP32 slideshow boards at key locations.
- [ ] **Live Stream:** Start OBS stream 15 mins early (2:45 PM PT). Verify audio sync.

## 5. Post-Event
- [ ] Collect all K10 units and check for damage.
- [ ] Sync all photos from gallery server to homelab `~/Workspace/graduation-site/photos`.
- [ ] Update `index.html` on `class2026.woodhead.tech` to show the stream recording.
- [ ] Prepare portfolio writeup for `woodhead.tech`.
