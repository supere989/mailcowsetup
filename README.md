# Mailcow with Tailscale Integration Project

## Project Overview
Implementation of Mailcow mail server with Tailscale integration, maintaining existing mail flow through Vultr server while providing web access via Tailscale Funnel.

## Architecture
```
Mail Flow:
Incoming: Internet → Vultr (Port 25) → Tailscale → Mailcow
Outgoing: Mailcow → Tailscale → Vultr → Gmail Relay → Internet

Web Access:
Users → Tailscale Funnel → Mailcow Web Interface (HTTPS)
```

## Prerequisites
1. Proxmox server with sufficient resources:
   - Minimum 6GB RAM ✅
   - 20GB disk space ✅
   - Docker support in LXC ✅
2. Tailscale account and network set up ✅
3. Existing mail configuration backup ✅

## Implementation Status

### Phase 1: Initial Setup
#### 1.1 Tailscale Setup
- [ ] Install Tailscale on Vultr server
- [ ] Configure Tailscale ACLs for mail ports
- [ ] Test connectivity

#### 1.2 Proxmox Preparation
- [x] Create LXC container (VMID: 106, Name: mail)
- [x] Install Docker and Docker Compose
- [x] Install Tailscale in container
- [x] Complete Tailscale network authentication

### Phase 2: Mailcow Installation
- [x] Clone Mailcow repository
- [x] Configure Mailcow
- [x] Initialize services
- [x] Test local access

### Phase 3: Mail Flow Configuration
- [ ] Configure Vultr Postfix relay
- [ ] Configure Mailcow outbound relay
- [ ] Test mail flow in both directions

### Phase 4: Web Access Setup
- [ ] Enable Tailscale Funnel
- [ ] Configure DNS for web interface
- [ ] Test web access
- [ ] Verify SSL certificates

### Final Phase: Testing & Verification
- [ ] Test incoming mail flow
- [ ] Test outgoing mail flow
- [ ] Verify web interface access
- [ ] Check SSL certificates

## Current Progress
- Container successfully created and running (VMID: 106)
