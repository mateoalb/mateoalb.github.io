---
layout: post
title: Home Server with Docker
description: Repurposed an old Dell desktop into a multi-service home server using Docker. Configured Pi-hole, Plex, RetroPie, and Homebridge containers for networking, media, gaming, and smart home integration.
skills:
- Docker / Containerization
- Linux Server Setup
- Networking
- Media Streaming (Plex)
- IoT / Home Automation
main-image: /homeServer.png
---

---
# Overview
This project documents the setup of my **home server** on a repurposed Dell desktop computer. Using Docker as the container platform, the server runs multiple services for networking, entertainment, and home automation. This approach maximized hardware efficiency, centralized system management, and created a flexible foundation for expanding future services.

## Features
- **Pi-hole** – Network-wide ad blocking and DNS sinkhole.  
- **Plex Media Server** – Stream personal movies, shows, and music to any device.  
- **RetroPie (via Docker)** – Emulation setup for retro gaming.  
- **Homebridge Integration** – Bridge non-HomeKit devices into Apple’s smart home ecosystem.  
- **Containerized Management** – All services isolated and easily configurable with Docker Compose.  

---
## Hardware
- **Old Dell Desktop (repurposed)**  
- **Linux OS (Ubuntu Server)** – Stable base environment for Docker deployment.  
- **Local Network Access** – Server connected via Ethernet for reliable performance.  

---
## Setup
1. **Operating System Installation** – Installed Ubuntu Server to maximize performance.  
2. **Docker & Docker Compose** – Configured for managing containerized services.  
3. **Service Deployment** – Each service defined in `docker-compose.yml`:  
   - Pi-hole for DNS filtering.  
   - Plex for media streaming.  
   - RetroPie container for emulation.  
   - Homebridge container for smart home integration.  
4. **Networking Configuration** – Pi-hole set as DNS across the home network.  
5. **Remote Access** – Enabled web UI and local network access for service management.  

---
# Summary
This project transformed an old Dell desktop into a powerful **all-in-one home server**. By leveraging **Docker containers**, I deployed Pi-hole for ad-blocking, Plex for media streaming, RetroPie for retro gaming, and Homebridge for smart home automation. The setup not only extended the life of older hardware but also provided a **centralized, flexible, and expandable platform** for managing home network, entertainment, and IoT devices.  

