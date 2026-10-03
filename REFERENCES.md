# Technical References and Citations

This document provides a comprehensive citation guide for all technical claims made in this project.

## Class 4 Fault Managed Power Systems

### Regulatory & Standards Framework

- **NFPA 70 (NEC) Article 726**: Establishes Class 4 Fault Managed Power Systems in the National Electrical Code
  - URL: https://www.nfpa.org/codes-and-standards/nfpa-70-standard-development/70
  - Scope: Regulatory foundation for FMPS implementation

### Technical Implementation Guides

- **Panduit FMPS Application Guide (PDF)**
  - URL: https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf
  - Covers: Pulse current architecture, ~360V distribution, remote receivers, rapid fault detection
  - Format: PDF technical reference

- **Belden FMPS Cable Portfolio**
  - URL: https://www.belden.com/products/cable/fiber-optic-cable/fmps-cable
  - Covers: Up to 2 km cable reach, Class 4 cable systems, long-distance power delivery specifications
  - Format: Product/technical specifications

### Industry Guidance

- **Telecommunications Industry Association (TIA): A Closer Look at Class 4 Fault Managed Power Systems in Smart Buildings**
  - URL: https://tiaonline.org/a-closer-look-at-class-4-fault-managed-power-systems-in-smart-buildings/
  - Covers: High-voltage pulsed DC distribution, millisecond fault interruption, central transmitter/remote receiver architecture
  - Scope: Industry perspectives on FMPS in building infrastructure

- **Panduit Blog: The Future of Power Distribution is Here: Introducing Fault Managed Power**
  - URL: https://www.panduit.com/en/about/blogs/the-future-of-power-distribution-is-here-introducing-fault-managed-power.html
  - Covers: Continuous monitoring, fault interruption within milliseconds, safe operation despite high distribution voltages
  - Format: Blog/thought leadership

## Hierarchical Power Architecture (FMPS + PoE)

### Architecture Presentations

- **Cisco Live On-Demand Session CENGRN-2110**
  - Source: Cisco Live On-Demand Library
  - Covers: "Highway, road, driveway" hierarchical power distribution concept
  - Access: Search Cisco Live website for session number CENGRN-2110
  - Note: Primary source for hierarchical network power architecture terminology

### Integration Architecture

- **Panduit & Optical LAN Architecture Video: Fault Managed Power + PoE Integration**
  - URL: https://www.youtube.com/watch?v=Ox1P7SAA2RQ
  - Covers: Class 4 backbone feeding remote receivers, receiver conversion to 48V DC, PoE distribution at the edge
  - Format: Video presentation

## Power over Ethernet (PoE) Standards

### IEEE Standards

- **IEEE 802.3 Ethernet Working Group**
  - URL: https://www.ieee802.org/3/
  - Covers: PoE standards including 802.3bt, standard Ethernet power delivery specifications
  - Scope: Authoritative standards body for PoE protocols

## USB-C Power Delivery

### USB Standards Organization

- **USB Power Delivery Specifications**
  - URL: https://usb.org/usb-charger-pd
  - Covers: USB-C PD power profiles, laptop charging over USB-C specifications
  - Scope: Official USB standards

### Vendor Solutions

- **Black Box USB-C PD over PoE Solutions**
  - URL: https://www.blackbox.com
  - Product category: USB-C Power Delivery over PoE infrastructure

- **Eaton/Tripp Lite USB-C over PoE Solutions**
  - URL: https://tripplite.eaton.com
  - Product category: USB-C Power Delivery over PoE infrastructure
  - Note: Wattage claims should be matched to specific products in your documentation

## Direct DC Power Integration & Solar

### Solar-to-Device Architecture

- **ICT Today: Fault Managed Power—Safe and Disruptive Innovation for Powering the Future**
  - URL: https://www.icttoday.com/fault-managed-power-safe-and-disruptive-innovation-for-powering-the-future/
  - Covers: Direct solar integration, battery integration, reduced conversion losses, distributed DC power architectures
  - Scope: Case studies and future-forward applications of FMPS
  - Strength: Comprehensive coverage of direct DC integration benefits

## Safety & Compliance Engineering

### Standards & Certification

- **IEEE Product Compliance Engineering**
  - URL: https://ieeexplore.ieee.org/
  - Covers: UL 1400-1 compliance, ATIS standards, safety engineering for Class 4 power systems
  - Scope: Technical papers on safety compliance

## Citation Usage Guide

### In Technical Writing

When citing these sources in technical documentation, use this format:

```
According to [Panduit FMPS Application Guide](https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf), 
Class 4 FMPS systems support ~360V distribution with remote receiver architecture.
```

### In Code Comments

```python
# FMPS receiver architecture converts high-voltage DC to 48V
# Reference: Panduit FMPS Application Guide
# https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf
```

### In Presentations

1. **Panduit FMPS Application Guide** - Covers pulse current architecture and ~360V distribution
2. **TIA Industry Guidance** - Contextualizes rapid fault detection capabilities (milliseconds)
3. **IEEE 802.3 Standards** - Authorizes PoE integration with FMPS backbone
4. **ICT Today** - Demonstrates solar integration use cases

## Primary Reference Set

For most comprehensive coverage of this project's technical claims, prioritize these five sources:

1. [Panduit FMPS Application Guide](https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf)
2. [Belden FMPS Cable](https://www.belden.com/products/cable/fiber-optic-cable/fmps-cable)
3. [TIA: A Closer Look at Class 4 FMPS in Smart Buildings](https://tiaonline.org/a-closer-look-at-class-4-fault-managed-power-systems-in-smart-buildings/)
4. [ICT Today: Fault Managed Power](https://www.icttoday.com/fault-managed-power-safe-and-disruptive-innovation-for-powering-the-future/)
5. [Cisco Live Session CENGRN-2110](https://ciscolive.cisco.com/) (Search on-demand library)

## Updates & Corrections

If you identify missing references or outdated citations, please open an issue or pull request.
