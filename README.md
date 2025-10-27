# Rave!  
### Distributed Wearable & Lighting Control System  
**by Fluffy Toaster Fursuits**  
[![License: CEL v1.0](https://img.shields.io/badge/License-CEL%20v1.0-purple.svg)](./LICENSE.md)

---

## Overview
**Rave!** is a distributed control system for synchronized lighting, wearables, and artistic effects.  
It enables costumes, props, and installations to communicate wirelessly using **ESP-NOW**, allowing group lighting or animation effects without servers or pairing.

Designed for community and creative events — not for large commercial use — Rave! provides a flexible, low-latency protocol for expressive collaboration across many devices.

This protocol is likely to change before a stable release with example code.

---

## Furry Lighting Protocol (FLP) v1.0

### Packet Layout
| Field | Bytes | Description |
|--------|-------|-------------|
| `type` | 1 | Packet type |
| `version` | 1 | Protocol version (currently 1) |
| `speciesMask` | 3 | 24-bit bitmask identifying species or wearable types |
| `groupMask` | 2 | 16-bit bitmask for LED or effect groups |
| `dataLength` | 2 | Length of valid bytes in `data[]` (≤ 216) |
| `frameCounter` | 4 | Frame sequence / sync counter |
| `data` | 216 | LED or effect data payload |

**Total:** 229 bytes  

---

### Species Bit Table (24-bit Mask)
| Bit | Meaning |
|-----|----------|
| 0 | Wearables / Accessories |
| 1 | Canine |
| 2 | Feline |
| 3 | Rodent / Lagomorph |
| 4 | Mustelid |
| 5 | Ursine |
| 6 | Equine |
| 7 | Bovine |
| 8 | Reptile / Amphibian |
| 9 | Avian |
| 10 | Aquatic |
| 11 | Insect / Arthropod |
| 12 | Mythic |
| 13 | Primate |
| 14 | Marsupial |
| 15 | Cybrid (Protogen / Synth) |
| 16-23 | Reserved / Hybrid |

---

### Group Bit Table (16-bit Mask)
| Bit | Group |
|-----|--------|
| 0 | All / Global |
| 1 | Left Eye |
| 2 | Right Eye |
| 3 | Left Ear |
| 4 | Right Ear |
| 5 | Mouth / Visor |
| 6 | Chest |
| 7 | Tail |
| 8 | Paws |
| 9 | Back / Spines |
| 10 | Wings |
| 11-15 | Reserved |

---

## Key Features
- Broadcast-based, no pairing or routing  
- Low latency and deterministic timing (≈ 30 Hz)  
- Simple mask-based addressing for expressive targeting  
- Supports lighting, haptic, and custom payloads  
- Openly documented for community collaboration

---

## License
Released under the **[Community Experience License (CEL) v1.0](./LICENSE.md)**  
© 2025 Fluffy Toaster Fursuits  
Free for community and creative use — attribution required.
