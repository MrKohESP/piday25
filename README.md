![](https://github.com/MrKohESP/piday25/blob/5b20a6e6c4fbf412ede0f5826ad5f6908304fdba/3D_PCB1_2025-03-11.png)
# Pi DAY 2025 (sort of)
For this Pi Day, we have created a development board based on the Raspberry Pi [RP2350B microcontroller (MCU)](https://datasheets.raspberrypi.com/rp2350/rp2350-datasheet.pdf)
This MCU is a Dual Cortex-M33 or Hazard3 RISC cores at up to 150MHz and the board has 16MB of Flash memory.
While this board is pretty much Pico 2 compatible there are some differences.  The LED is on GPIO04 and it has a highly stable 3.00V voltage reference which is connected for ADC circuits.
There is also connectivity and space for an addressable RGB LED on GPIO08, it was left off in production because of it's baking requirement.  You may solder your own RGB LED on this board.

# Warning

>[!CAUTION]
>UPDATE: PLease do not make this board.  There is currently an issue where it will not load programs.  It does present as a USB drive but when files are copied to it, it restarts and comes back in BOOT mode.$$

>[!CAUTION]
>UPDATE2: Pins 2 and 5 are mistakenly swapped on the Flash RAM on this board.  It makes sense that we could not upload any programs. A new board will be coming soon (hopefully with an RGB LED too).  I think too that we should use GPIO25 for the LED so that blinky is compatible with Pico 2 blinky(s).  In the mean time we will try to fix this error with some tiny wire and see if it is the only mistake.

# Pin Out
![Pin Out](https://github.com/MrKohESP/piday25/blob/7aa0499c4f427dc0b9bd07b8a9af8c04fe3a9cd1/Screenshot%202025-03-15%20175123.png)

# Schematic
![Schematic](https://github.com/MrKohESP/piday25/blob/9f478729204b799b942757d8fb7b606811b21294/Screenshot%202025-03-11%20141103.png)
Full size PDF is available here: https://github.com/MrKohESP/piday25/blob/441c7a7571a44883a6261e9f15735d09b5271e8f/Hardware/SCH_Schematic1_2025-03-02.pdf

# Bill of Materials (BOM)
| No. | Quantity | Comment                | Designator                                     | Footprint                                | Manufacturer Part      | Manufacturer         | Supplier Part |
|-----|----------|------------------------|------------------------------------------------|------------------------------------------|------------------------|----------------------|---------------|
| 1   | 2        | TS1201-TZ25HAM         | BOOT,RUN                                       | KEY-SMD_L3.9-W3.0-LS5.0_1                | TS1201-TZ25HAM         | BXCONN(宝讯)           | C36936654     |
| 2   | 2        | 10uF                   | C1,C2                                          | C0402                                    | CL05A106MQ5NUNC        | SAMSUNG(三星)          | C15525        |
| 3   | 2        | 4.7uF                  | C3,C4                                          | C0603                                    | CL10A475KO8NNNC        | SAMSUNG(三星)          | C19666        |
| 4   | 2        | 15pF                   | C6,C7                                          | C0402                                    | 0402CG150J500NT        | FH(风华)               | C1548         |
| 5   | 12       | 100nF                  | All Others | C0402                                    | CL05B104KO5NNNC        | SAMSUNG(三星)          | C1525         |
| 6   | 2        | 4.7uF                  | C9,C10                                         | C0402                                    | CL05A475MP5NRNC        | SAMSUNG(三星)          | C23733        |
| 7   | 3        | DF2B7AFS,L3M           | D1,D2,D4                                       | SOD-923_L0.8-W0.6-LS1.0-BI               | DF2B7AFS,L3M           | TOSHIBA(东芝)          | C1972965      |
| 8   | 2        | X6511WV-26H-C60D30     | H1,H2                                          | HDR-TH_26P-P2.54-V-M                     | X6511WV-26H-C60D30     | XKB Connection(中国星坤) | C725958       |
| 9   | 1        | AOTA-B201610S3R3-101-T | L1                                             | IND-SMD_L2.0-W1.6_AOTA-B201610S3R3-101-T | AOTA-B201610S3R3-101-T | ABRACON              | C42411119     |
| 10  | 1        | KT-0603R               | PWR                                            | LED0603-RD                               | KT-0603R               | KENTO                | C2286         |
| 11  | 1        | 33Ω                    | R1                                             | R0402                                    | 0402WGF330JTCE         | UNI-ROYAL(厚声)        | C25105        |
| 12  | 3        | 1kΩ                    | R4,R5,R6                                       | R0402                                    | 0402WGF1001TCE         | UNI-ROYAL(厚声)        | C11702        |
| 13  | 2        | 27Ω                    | R7,R8                                          | R0402                                    | 0402WGF270JTCE         | UNI-ROYAL(厚声)        | C25100        |
| 14  | 1        | 10kΩ                   | R9                                             | R0402                                    | 0402WGF1002TCE         | UNI-ROYAL(厚声)        | C25744        |
| 15  | 2        | 5.1kΩ                  | R10,R11                                        | R0402                                    | 0402WGF5101TCE         | UNI-ROYAL(厚声)        | C25905        |
| 16  | 2        | 1.5kΩ                  | R14,R15                                        | R0402                                    | 0402WGF1501TCE         | UNI-ROYAL(厚声)        | C25867        |
| 17  | 1        | 820Ω                   | R16                                            | R0603                                    | 0603WAF8200T5E         | UNI-ROYAL(厚声)        | C23253        |
| 18  | 1        | 0Ω                     | R17                                            | R0603                                    | 0603WAF0000T5E         | UNI-ROYAL(厚声)        | C21189        |
| 19  | 1        | XL-5050RGBC-WS2812B    | RGB                                            | LED-SMD_4P-L5.0-W5.0-BL_XL-5050RGBC      | XL-5050RGBC-WS2812B    | XINGLIGHT(成兴光)       | C2843785      |
| 20  | 1        | RP2350B                | U1                                             | QFN-80_L10.0-W10.0-P0.40-TL-EP3.4        | RP2350B                | Raspberry Pi(树莓派)    | C42415655     |
| 21  | 1        | NCP1117ST33T3G         | U2                                             | SOT-223-3_L6.5-W3.4-P2.30-LS7.0-BR       | NCP1117ST33T3G         | onsemi(安森美)          | C26537        |
| 22  | 1        | W25Q128JVSIQ           | U3                                             | SOIC-8_L5.2-W5.2-P1.27-LS8.0-BL          | W25Q128JVSIQ           | WINBOND(华邦)          | C97521        |
| 23  | 1        | LM4040D30FTA           | U5                                             | SOT-23-3_L2.9-W1.3-P1.90-LS2.4-BR        | LM4040D30FTA           | DIODES(美台)           | C460726       |
| 24  | 1        | TYPE-C-31-M-12         | USBC1                                          | USB-C_SMD-TYPE-C-31-M-12                 | TYPE-C-31-M-12         | 韩国韩荣                 | C165948       |
| 25  | 1        | KT-0603W               | USR                                            | LED0603-R-RD                             | KT-0603W               | KENTO                | C2290         |
| 26  | 1        | ABM8-272-T3            | Y1                                             | CRYSTAL-SMD_4P-L3.2-W2.5-BL              | ABM8-272-T3            | ABRACON              | C20625731     |

>[!CAUTION]
>Item 19 above could not be assembled with the economy pcb and was cost prohibitive.

Full size BOM in xslx format: https://github.com/MrKohESP/piday25/blob/441c7a7571a44883a6261e9f15735d09b5271e8f/Hardware/BOM_Board1_Schematic1_2025-03-02.xlsx 

# PCB component side
![PCBF](https://github.com/MrKohESP/piday25/blob/441c7a7571a44883a6261e9f15735d09b5271e8f/Hardware/2D_PCB1_2025-03-02%20(1).png)

# PCB back side
![PCBB](https://github.com/MrKohESP/piday25/blob/441c7a7571a44883a6261e9f15735d09b5271e8f/Hardware/2D_PCB1_2025-03-02.png)
