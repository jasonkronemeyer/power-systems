# power-systems

Documentation and resources for Class 4 Fault Managed Power, Power over Ethernet, and USB-C Power Delivery infrastructure.

## Overview

This project explores next-generation power distribution architectures that combine safety, efficiency, and scalability through Fault Managed Power (FMPS) systems, Power over Ethernet (PoE), and standardized power delivery protocols.

## Key Technologies

### Class 4 Fault Managed Power (FMPS)

Class 4 Fault Managed Power Systems represent a paradigm shift in electrical infrastructure, establishing safe, high-voltage DC power distribution through rapid fault detection and intelligent control.

**Core Capabilities:**
- **High-voltage distribution**: ~360V DC architecture with pulse-current topology
- **Extended reach**: Up to 2 km cable runs for remote power delivery
- **Rapid fault detection**: Millisecond-level fault interruption
- **Touch-safe operation**: Central transmitter with distributed remote receivers
- **Continuous monitoring**: Real-time safety management across the distribution network

*References:*
- [NFPA 70 (NEC) Article 726 - Class 4 Fault Managed Power Systems](https://www.nfpa.org/codes-and-standards/nfpa-70-standard-development/70)
- [Panduit FMPS Application Guide](https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf)
- [Belden Class 4 FMPS Cable Portfolio](https://www.belden.com/products/cable/fiber-optic-cable/fmps-cable)
- TIA: [A Closer Look at Class 4 Fault Managed Power Systems in Smart Buildings](https://tiaonline.org/a-closer-look-at-class-4-fault-managed-power-systems-in-smart-buildings/)
- Panduit Blog: [The Future of Power Distribution is Here: Introducing Fault Managed Power](https://www.panduit.com/en/about/blogs/the-future-of-power-distribution-is-here-introducing-fault-managed-power.html)

### Power over Ethernet (PoE)

Power over Ethernet enables standardized power delivery over existing data infrastructure, creating a unified network and power architecture.

**Integration with FMPS:**
- Class 4 backbone (FMPS) feeds remote receivers deployed across the network
- Remote receivers convert high-voltage DC to 48V DC
- 48V feeds local PoE switches for edge device power distribution
- Creates a hierarchical "highway, road, driveway" architecture: long-distance backbone → mid-range distribution → edge access

*References:*
- [IEEE 802.3 Ethernet Working Group - PoE Standards](https://www.ieee802.org/3/) (including 802.3bt for higher power)
- Panduit & Optical LAN Architecture: [Fault Managed Power + PoE Integration](https://www.youtube.com/watch?v=Ox1P7SAA2RQ)
- Cisco Live On-Demand: Search session **CENGRN-2110** in the Cisco Live On-Demand Library for "highway, road, driveway" power architecture presentation

### USB-C Power Delivery

USB-C PD extends unified power delivery to end devices, enabling direct charging of laptops and high-power peripherals through PoE infrastructure.

**Vendor Solutions:**
- PoE-powered USB-C ports charge compatible laptops (wattage varies by product and standard)
- Enables simplified cabling and power distribution at the edge

*References:*
- [USB Power Delivery Specifications](https://usb.org/usb-charger-pd)
- [Black Box USB-C PD over PoE Solutions](https://www.blackbox.com)
- [Eaton/Tripp Lite USB-C over PoE Solutions](https://tripplite.eaton.com)

### Direct DC Power Integration

Next-generation architectures enable direct integration of renewable energy sources with distributed DC power networks, reducing conversion losses and improving overall system efficiency.

**Benefits:**
- Direct solar-to-battery integration
- Reduced power conversion losses
- Distributed, resilient DC architecture
- Lower operational costs

*References:*
- [ICT Today: Fault Managed Power—Safe and Disruptive Innovation for Powering the Future](https://www.icttoday.com/fault-managed-power-safe-and-disruptive-innovation-for-powering-the-future/)

## Documentation

- [USB-C Power Delivery](docs/usb-c-power-delivery.md) — technical limits, deployment guidance, and example installations for PoE-fed USB-C charging.

## Standards & Compliance

This work aligns with:
- **NEC Article 726**: Class 4 Fault Managed Power Systems
- **IEEE 802.3**: Ethernet and Power over Ethernet standards
- **UL 1400-1**: Safety compliance for Class 4 power systems
- **ATIS Standards**: Telecommunications power infrastructure specifications

*References:*
- [IEEE Product Compliance Engineering](https://ieeexplore.ieee.org/)

## Core References

The technical claims in this project are grounded in these authoritative sources:

1. [Panduit FMPS Application Guide](https://www.panduit.com/content/dam/panduit/en/power-environmental-security-connectivity-hardware/documents/puag2-ww-eng-fmps-application-guide/fmps-puag2-ww-eng.pdf)
2. [Belden FMPS Cable](https://www.belden.com/products/cable/fiber-optic-cable/fmps-cable)
3. [TIA: A Closer Look at Class 4 Fault Managed Power Systems in Smart Buildings](https://tiaonline.org/a-closer-look-at-class-4-fault-managed-power-systems-in-smart-buildings/)
4. [ICT Today: Fault Managed Power—Safe and Disruptive Innovation for Powering the Future](https://www.icttoday.com/fault-managed-power-safe-and-disruptive-innovation-for-powering-the-future/)
5. Cisco Live On-Demand Library: Session **CENGRN-2110**

## Contributing

Contributions, corrections, and additional references are welcome. Please open an issue or pull request.

## License

This documentation is provided as-is for educational and technical reference purposes.
