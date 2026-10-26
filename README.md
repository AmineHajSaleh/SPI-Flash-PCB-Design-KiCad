
# SPI Flash Memory PCB Design | KiCad

### 2-Layer PCB Design — W25Q32JV SPI Flash Memory

A personal electronics project focused on schematic design, PCB layout, signal routing, power distribution, and design verification using **KiCad**.

The objective was to design a compact SPI Flash memory breakout board that can interface with an external STM32 microcontroller.

## 1. PCB 3D Visualization

![SPI Flash PCB 3D View](Images/pcb-3d.png)

## 2. PCB Layout & Routing

![SPI Flash PCB Layout](Images/pcb-layout.png)

The board uses a **2-layer PCB architecture**:

- **F.Cu (Top Layer):** SPI signals and 3.3 V power routing.
- **B.Cu (Bottom Layer):** Ground copper plane and necessary signal connections.
- **GND vias:** Connections between component ground pads and the bottom ground plane.
- **Decoupling:** 100 nF capacitor placed near the Flash memory power pin.

## 3. Hardware Components

| Component | Description |
|-----------|-------------|
| W25Q32JVSS | 32 Mbit SPI Flash Memory |
| R1 | 10 kΩ CS pull-up resistor |
| C1 | 100 nF decoupling capacitor |
| J1 | 6-pin SPI connector |

**Supply voltage:** 3.3 V

## 4. SPI Connector Pinout

| Pin | Signal | Description |
|-----|--------|-------------|
| 1 | 3V3 | Power supply |
| 2 | CS | Chip Select |
| 3 | MISO | Master In Slave Out |
| 4 | SCK | SPI Clock |
| 5 | MOSI | Master Out Slave In |
| 6 | GND | Ground |

The connector is intended for connection to an external 3.3 V STM32 development board.

## 5. PCB Design Decisions

### Component Placement

- Positioned the SPI Flash memory close to the connector.
- Placed the decoupling capacitor near the VCC pin.
- Positioned the CS pull-up resistor near the memory.
- Optimized component placement to reduce unnecessary trace lengths.

### Signal Routing

- Routed SPI signals while respecting electrical clearances.
- Used copper layers and vias where necessary to avoid trace crossings.
- Optimized routing paths to reduce excessive detours.

### Ground Plane

- Implemented a GND copper zone on B.Cu.
- Connected ground pads using vias.
- Considered signal return paths and ground-plane continuity.

### Power Distribution

- Designed the board for a regulated 3.3 V supply.
- Added local power-supply decoupling.
- Considered trace width and routing constraints.

## 6. Design Verification

The following design steps were completed:

- [x] Electronic schematic design
- [x] Component footprint assignment
- [x] Electrical Rules Check (ERC)
- [x] PCB component placement
- [x] Signal and power routing
- [x] Ground copper plane implementation
- [x] Design Rules Check (DRC)
- [x] 3D PCB visualization
- [ ] Physical PCB manufacturing
- [ ] Hardware testing with STM32

**Validation status:** The schematic and PCB were checked using KiCad ERC/DRC tools. Physical manufacturing and functional testing have not yet been performed.

## 7. Project Files

| File | Description |
|------|-------------|
| `SPI_FLASH_STM32.kicad_pro` | KiCad project configuration |
| `SPI_FLASH_STM32.kicad_sch` | Electronic schematic |
| `SPI_FLASH_STM32.kicad_pcb` | PCB layout and routing |
| `images/pcb-layout.png` | PCB routing screenshot |
| `images/pcb-3d.png` | 3D PCB visualization |

## 8. Tools & Skills

**Software:** KiCad

**Technical skills:**
- Electronic schematic design
- PCB layout and routing
- Component placement
- Power distribution and decoupling
- Ground plane design
- SPI communication
- ERC/DRC verification
- PCB manufacturing preparation

## 9. Future Improvements

- Further optimization of signal routing
- Review of EMC and signal integrity considerations
- Manufacturing the PCB prototype
- SPI communication testing with STM32
- Reading the Flash memory JEDEC ID
- Functional read/write verification

---

## Author

**Amine Haj Salah**

Electronics & Embedded Systems

[LinkedIn](https://www.linkedin.com/in/amine-haj-salah/) |
[GitHub](https://github.com/aminehajsaleh) |
[Portfolio](https://aminehajsaleh.github.io/PORTFOLIO/)
