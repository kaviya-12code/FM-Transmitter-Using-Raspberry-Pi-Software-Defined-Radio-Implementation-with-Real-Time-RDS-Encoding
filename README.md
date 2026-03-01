FM Transmitter Using Raspberry Pi
Software-Defined Radio (SDR) Implementation with Real-Time RDS Encoding

🔷 Project Summary

Designed and implemented a low-cost, software-defined FM transmitter using Raspberry Pi 3 by leveraging GPIO-based Pulse Width Modulation (PWM) and Direct Memory Access (DMA) streaming.

The system broadcasts stereo audio along with real-time Radio Data System (RDS) metadata without requiring dedicated RF transmission hardware.

This project demonstrates practical implementation of:

Digital Signal Processing (DSP)

Software-Defined Radio (SDR)

Embedded C Programming

Real-Time Audio Processing

RF Signal Generation via GPIO

🔷 Engineering Problem Addressed

Conventional FM transmitters depend on dedicated RF modules and analog modulation circuitry, increasing hardware cost and system complexity.

This project eliminates external RF hardware by implementing FM modulation entirely in software using Raspberry Pi peripherals, proving that general-purpose embedded systems can be repurposed for RF communication tasks.

🔷 Technical Architecture
🧠 Processing Layer

Real-time audio sampling (WAV / Live Stream)

Upsampling to 228 kHz internal rate

60th-order FIR filtering

Stereo multiplex baseband generation:

L+R

L−R

19 kHz pilot tone

RDS group generation (0A, 2A, 4A)

CRC-based RDS encoding

⚙ Hardware Layer

Raspberry Pi 3 (ARM-based SBC)

GPIO 4 (PWM output)

8.6 cm wire antenna

5V regulated power supply

MicroSD (16GB+)

📡 Transmission Layer

DMA controller streams multiplex samples to PWM peripheral

PWM generates frequency-modulated square wave

Antenna radiates VHF FM signal (~107.9 MHz)

🔷 Antenna Optimization

Optimal antenna length formula:

Length (cm) = (300 / Frequency in MHz / 16) × 100

For 107.9 MHz:

Theoretical length: 17.3 cm

Practical length used: 8.6 cm (to limit interference)

Measured broadcast radius: ~50 meters.

🔷 Performance Evaluation
Mode	CPU Utilization
RDS Only	9%
Mono Audio	33%
Stereo Audio	40%
Measured Results:

Clear stereo separation

Zero RDS group errors

Stable continuous transmission

No runtime buffer underflow

The system remained computationally stable under sustained real-time operation.

🔷 Key Technical Contributions

✔ Implemented stereo FM multiplex signal generation
✔ Integrated EN 50067 compliant RDS encoding
✔ Achieved stable DMA-based continuous transmission
✔ Optimized CPU usage for real-time DSP operations
✔ Validated reception using multiple FM receivers

🔷 Core Technical Skills Demonstrated

Embedded C programming

GPIO peripheral control

DMA configuration

FIR filter implementation

CRC encoding techniques

Real-time system optimization

Linux command-line environment

Software-defined radio concepts

🔷 Innovation & Differentiation

RF transmission achieved without external RF modules

Combines Embedded Systems + DSP + RF Communication

Minimal hardware dependency (cost-effective solution)

Demonstrates strong system-level integration capability

🔷 Practical Applications

Educational SDR experimentation platform

Localized campus broadcasting

Embedded communication lab prototype

Digital signal processing demonstration system

🔷 Limitations & Compliance

Transmission range intentionally limited (~50m) to minimize interference.
The system is intended strictly for educational and controlled experimental use in compliance with local RF regulations.

🔷 Future Enhancements

Harmonic filtering for improved spectral purity

Web-based broadcast control dashboard

Remote RDS dynamic update interface

IoT-based streaming integration

🔷 Conclusion

This project validates that Raspberry Pi can function as a software-defined FM transmitter through intelligent use of PWM and DMA-based modulation.

It showcases applied knowledge in embedded systems, digital signal processing, and RF communication — demonstrating practical engineering problem-solving capability suitable for real-world applications.
