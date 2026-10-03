# USB-C Power Delivery

## Overview

USB-C Power Delivery is the driveway of power distribution infrastructure. At desks, conference tables, and phone booths, PoE-powered USB-C ports charge laptops and devices directly with up to approximately 45 watts, completely eliminating wall warts, floor boxes, and power strips.

## Technical Specifications

### Power Delivery Levels
- **Example PoE-fed output:** Up to ~45W per port, subject to the input PoE budget, converter efficiency, and product rating
- **Connector Type:** USB-C (USB Type-C)
- **Integration:** PoE-powered delivery
- **Data Transfer:** Simultaneous power and data capability

### USB Power Delivery Standard

The USB Power Delivery (USB PD) specification defines multiple power levels:

| USB PD Version | Max Power | Voltage | Current |
|---|---|---|---|
| USB PD 2.0 | Up to 100W | Standard Power Range (SPR), up to 20V | Up to 5A with a 5A-rated cable |
| USB PD 3.0 | Up to 100W | SPR, up to 20V | Up to 5A with a 5A-rated cable |
| USB PD 3.1 | Up to 240W | SPR up to 20V; Extended Power Range (EPR) adds 28V, 36V, and 48V | Up to 5A; EPR requires a suitable EPR-rated cable |

These are limits of the USB PD standard, not a promise that a PoE-to-USB-C product can provide that much power. The actual USB-C output is limited by the converter, its PoE input class, cabling, and configured power budget. In particular, a single IEEE 802.3at (PoE+) powered-device port is limited to 25.5W at the device, before conversion losses, so it cannot provide 45W at USB-C.

### PoE Input Budget

The following are maximum power levels defined for common IEEE PoE types. The powered-device value is the maximum available at the end of the Ethernet channel, before a downstream USB-C converter uses any power.

| PoE type | Maximum from PSE port | Maximum at powered device |
|---|---:|---:|
| IEEE 802.3af (Type 1) | 15.4W | 12.95W |
| IEEE 802.3at (Type 2) | 30W | 25.5W |
| IEEE 802.3bt (Type 3) | 60W | 51W |
| IEEE 802.3bt (Type 4) | 90W | 71.3W |

Usable USB-C output is lower than the powered-device input because the converter has losses and may consume power itself. Check the switch's per-port and total PoE budgets as well as the USB-C adapter's published output ratings; do not size a design from the switch's advertised aggregate wattage alone.

## Benefits Over Traditional Charging

### Eliminates Multiple Chargers
- **Before:** Different chargers for laptops, phones, tablets
- **After:** Single USB-C Power Delivery standard
- **Result:** Reduced e-waste and clutter

### Removes Desk Infrastructure
- No wall warts cluttering desks
- Eliminates floor boxes
- Removes power strips from under desks
- Cleaner, more organized workspaces

### Environmental Impact
- Reduced manufacturing of multiple chargers
- Lower energy consumption
- Simplified recycling

## System Architecture

```
PoE Network (-48V/-52V DC)
            ↓
PoE to USB PD Converter
            ↓
USB-C Port (up to 45W)
            ↓
Laptops, Phones, Tablets, Peripherals
```

## Applications

### Office Environments

#### Desks
- Primary laptop charging station
- Phone/tablet charging
- Peripheral power (monitors, docks)

#### Conference Rooms
- Laptop charging during meetings
- Mobile device charging
- Presentation equipment

#### Phone Booths
- Mobile device charging for privacy calls
- Headset charging
- Recording device power

### Mobile Workspaces
- Co-working spaces
- Flexible work areas
- Temporary workstations

### Educational Institutions
- Student laptop charging
- Classroom flexibility
- Library workstations

## Device Compatibility

### Laptops Supporting USB-C Charging
- Apple MacBook (all recent models)
- Dell XPS series
- Lenovo ThinkPad series
- HP EliteBook series
- ASUS ZenBook series
- Many others with USB-C ports

### Mobile Devices
- All modern smartphones
- Tablets
- Wireless earbuds
- Smartwatches
- E-readers

### Accessories
- USB-C hubs
- Docking stations
- External displays with USB-C
- Portable SSDs

## Power Management

### Negotiation Protocol
- Device communicates power requirements to adapter
- Adapter delivers requested voltage/current
- Dynamic adjustment based on load
- Safety mechanisms prevent over-delivery

### Thermal Considerations
- Proper ventilation around charging ports
- Heat dissipation in converters
- Temperature monitoring
- Automatic power limiting if overheat detected

## Installation Best Practices

### Placement
- Mount USB-C ports at ergonomic heights
- Position near work surfaces
- Consider cable routing and management

### Infrastructure
- Ensure adequate PoE switch capacity
- Use quality converters with certifications
- Plan for redundancy in critical areas
- Label ports clearly

### Cable Management
- Use managed cabling systems
- Avoid excessive cable lengths
- Protect cables from damage
- Plan for scalability

## Implementation Guide

### 1. Establish the charging requirement

- List the devices to be charged and the maximum power each actually requires.
- Decide whether each port must support a particular USB PD voltage/current profile, rather than relying on a headline wattage.
- Include simultaneous-use expectations. A multiport adapter may share or dynamically allocate its available power.
- Treat the adapter's USB-C output rating as the design limit; a device's ability to accept higher USB PD power does not increase that rating.

### 2. Select and budget the PoE source

- Confirm the exact IEEE PoE type supported by both the switch port and the powered USB-C adapter.
- Check the switch's available per-port allocation, total PoE budget, and behavior when its budget is oversubscribed.
- Account for conversion loss, adapter overhead, and any power shared between outputs.
- For example, a 45W USB-C load at 90% conversion efficiency needs about 50W at the adapter input, before other overhead. That leaves almost no margin on a Type 3 PoE port (51W maximum at the powered device); a Type 4 source or a lower USB-C output target may be needed. Verify the adapter's own rating and reserve against the actual switch budget.
- Confirm that the complete Ethernet channel and installation method meet the switch and adapter manufacturer's requirements.

### 3. Verify USB-C behavior and safety

- Use an adapter designed to negotiate USB PD profiles and regulate its output; never connect raw PoE voltage to a USB-C receptacle.
- Check USB-IF and applicable electrical safety certifications for the specific product and market.
- Confirm that cables are suitable for the required current and power. Higher-current and EPR operation requires appropriately rated, electronically marked cables.
- Review protections, thermal limits, fault behavior, and whether the adapter reduces or shuts off output if its input budget is exceeded.

### 4. Install and commission

- Coordinate the port locations, mounting, cable routing, and service access with the furniture and network installation.
- Label ports with their supported output and any device or cable limitations.
- Before broad deployment, test representative laptop and mobile-device models under simultaneous load.
- Record the negotiated USB PD profile, measured output under load, PoE class/allocation, and any throttling or thermal behavior.
- Confirm that disconnects, re-connections, and switch power-budget changes leave the port in a safe, usable state.

## Illustrative Case Studies

These examples describe design approaches, not measured customer deployments or guaranteed performance.

### Open-office desk charging

**Need:** Provide a convenient USB-C charging point at each desk while keeping chargers and power strips off the work surface.

**Design approach:** Connect a desk-mounted PoE-to-USB-C adapter to a managed PoE switch. Select the adapter output for the target laptop workload, then size the switch port and aggregate budget for realistic concurrent use. If the target is 45W, the input calculation above shows why PoE+ is insufficient and why even a Type 3 port requires careful margin assessment.

**Commissioning checks:** Test the laptop models used by staff, confirm charging continues during normal workload, inspect adapter temperature in its installed position, and verify switch allocation after all planned ports are connected.

### Shared conference table

**Need:** Offer charging at several seating positions without assuming every attendee will draw maximum power at the same time.

**Design approach:** Use a product explicitly rated for the number of USB-C outputs and its simultaneous power-sharing behavior. Determine an expected concurrent load from room use, but also document what happens when all ports request power. Provide higher-capacity PoE sources only where the adapter and switch support them, and avoid promising a full laptop charge at every seat unless the budget supports it.

**Commissioning checks:** Exercise all ports concurrently with representative devices, confirm the advertised power allocation, and ensure users can identify which ports support laptop charging versus lower-power accessories.

## Advantages

1. **Universal Standard:** Works with most modern devices
2. **Space-Saving:** Eliminates multiple charging systems
3. **Cost-Effective:** Reduced infrastructure needed
4. **User-Friendly:** Simple plug-and-charge experience
5. **Scalable:** Easy to add charged ports throughout facility
6. **Sustainable:** Reduces e-waste and energy consumption

## Challenges and Considerations

- Legacy device compatibility (older laptops, phones)
- Adapter reliability and quality variations
- Cost of initial conversion infrastructure
- Need for user education on proper usage
- Thermal management in high-density environments

## Specifications and Standards

### USB PD Specifications
- Compliant with USB Power Delivery standard
- Power Management ICs for regulation
- Over-voltage/current protection
- Temperature monitoring

### Certifications
- USB-IF (USB Implementers Forum) certification
- UL/safety certifications
- Regional compliance (CE, FCC, etc.)

## Future Developments

### Higher Power Delivery
- 100W+ standards in development
- Support for larger systems
- Desktop computing possibilities

### Enhanced Capabilities
- Improved efficiency standards
- Better thermal management
- Advanced power monitoring
- AI-optimized power distribution

### Ecosystem Evolution
- Increased device adoption
- Standardized cables and adapters
- Integration with building management systems
- Environmental monitoring integration

## Real-World Implementation Example

**Typical Office Desk Setup:**
```
PoE Cat6A Cable → Desk Mount USB-C Port
                    ↓
                Laptop (45W charging)
                ↓
                Charging while working
                ↓
                No desk clutter
                ↓
                Clean workspace
```

## References

- USB Power Delivery Specification (USB-IF)
- USB Implementers Forum
- Cisco Live On Demand - CENGRN 2110
