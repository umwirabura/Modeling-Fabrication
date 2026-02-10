## Day 3 – PCB Milling Techniques & Fabrication Process

### Single-Sided Microcontroller PCB Design (KiCad)

Day 3 introduced PCB design using KiCad, focusing on creating a single-sided printed circuit board featuring an ATtiny45 microcontroller. The objective was to design a functional board that controls an LED using a push button input and can be programmed via an ISP (In-System Programming) header. This activity bridged the gap between digital design and physical fabrication, emphasizing design-for-manufacturing principles specific to PCB milling.

The circuit design centered around the ATtiny45, an 8-pin microcontroller running at 5V. The board includes an LED with a current-limiting resistor connected to one of the microcontroller's GPIO pins, a tactile push button for user input, a 6-pin ISP header for programming, and a power connector for external 5V supply. A decoupling capacitor was included between VCC and GND to ensure power stability, which is essential for reliable microcontroller operation. The design represents a complete microcontroller system rather than a simple demonstration circuit.

The design process began in KiCad's schematic editor. Each component was placed and connected according to the circuit requirements. The ATtiny45 symbol served as the central component, with the LED and resistor forming the output circuit, the push button providing input functionality, and the ISP header enabling code uploads. All nets were labeled clearly to maintain organization and prevent connection errors. Particular attention was paid to the ISP header pinout, ensuring correct connections for MOSI, MISO, SCK, RESET, VCC, and GND, as incorrect wiring would prevent programming.

After completing the schematic, footprints were assigned to each component. Through-hole (THT) components were selected to simplify hand soldering and make the board more beginner-friendly. The ATtiny45 used a DIP-8 footprint, the LED a standard 5mm THT footprint, and the resistor an axial through-hole package. The tactile button and headers also used through-hole footprints. This choice of footprints was deliberate, considering both fabrication constraints and assembly accessibility.

The PCB layout phase presented the most significant design challenge due to the single-sided constraint. Unlike double-sided boards that can route traces on both top and bottom layers, this design required all copper traces to exist on a single layer. Components were arranged strategically to minimize trace crossings and reduce the need for jumper wires. The ISP header was positioned close to the ATtiny45 to keep programming traces short and direct. The LED was placed near the board edge for visibility, and the power connector was positioned for convenient access.

Routing the board within the single-layer constraint required careful planning. Once a trace occupies a path, another trace cannot cross it, which became especially challenging in areas with many connections. Traces were kept as wide as practical to ensure they could be reliably milled without breaking. In situations where direct routing was impossible without crossing traces, the layout was adjusted by repositioning components or changing route paths. The routing process required multiple iterations to achieve a clean, manufacturable design.

Design rule checking (DRC) was performed to verify the layout met manufacturing requirements. The DRC identified any unconnected nets, trace overlaps, or clearance violations that could cause fabrication or functional issues. All errors flagged by the DRC were resolved before proceeding to file generation. This step is critical in PCB design, as catching errors digitally is far easier than fixing them on a physical board.

The final preparation involved adding identifying text to the board and exporting Gerber files and drill files. These files serve as the manufacturing instructions for the milling machine, defining where copper should be removed and where holes should be drilled. The design was reviewed in the 3D viewer to verify component placement and overall board aesthetics before export.

![Final routed PCB design (3D view)](../images/day_3/3dview.png)

One of the primary learning outcomes from this activity was understanding that component placement is critical in single-sided PCB design. Good planning at the layout stage significantly reduces routing complexity. The challenge of working within single-sided constraints emphasized the importance of thinking ahead about fabrication requirements rather than simply connecting nets. This activity provided hands-on experience with the complete PCB design workflow, from schematic capture through layout and file generation.

### Download Files

[Download KiCad Project Files (.zip)](../files/Microcontroller_PCB_Design.zip)