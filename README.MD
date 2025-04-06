E-readerul implementat integrează mai multe module esențiale, inclusiv ESP32-C6, un modul RTC, senzori de mediu, 
conectivitate USB-C, un slot pentru card MicroSD și un sistem de gestionare a bateriei. 
Toate componentele comunică prin interfețe standard precum I²C, SPI, UART și GPIO analogice/digitale.

Controler de încărcare – MCP73831
Tip baterie: Li-ion/Li-Po cu o singură celulă

Curent de încărcare: Programabil până la 500 mA

Interfață: Standalone (fără I²C/SPI)

Tensiune de intrare: 3.75 V – 6 V

Ieșire stare: Indicație a stării de încărcare prin LED

Senzor de mediu – BME688
Măsurători: Temperatură, umiditate, presiune, gaze (VOC, calitatea aerului)

Interfață: I²C, SPI

Interval temperatură: -40 °C – +85 °C

Senzor de gaze: Detecție AI a amestecurilor de gaze și VOC

Consum de energie: Ultra redus (ideal pentru dispozitive mobile/wearables)

Display e-paper
Interfață: SPI

Rezoluție: 800×480

Consum de energie: Foarte redus (consum doar în timpul actualizării)

Caracteristici: Lizibil excelent în lumină solară, unghiuri largi de vizualizare

Conector Qwiic
Tip: Conector JST SH cu 4 pini (1.0 mm)

Scop: Interconectare I²C standardizată pentru senzori/module

Tensiune: Logică de 3.3 V

Pini: SDA, SCL, VCC, GND

Conector card memorie – 112A-TAAR-R03
Tip: Slot pentru card MicroSD

Interfață: SPI sau SDIO

Tensiune: Logică 3.3 V

Caracteristici: Mecanism push-push, contact pentru detectare card

Utilizare: Stocare de date, redare media

Microcontroler – ESP32-C6-WROOM-1-N8
Procesor: RISC-V pe 32 de biți, până la 160 MHz

Memorie: 512 KB SRAM intern, 8 MB flash extern (W25Q512JVEIQ)

Conectivitate: Wi-Fi 6 (802.11ax), Bluetooth 5 (LE), IEEE 802.15.4 (Thread/Zigbee), USB 2.0 (Full-Speed)

Periferice: SPI, I²C, UART, PWM, ADC, mai mulți pini GPIO

Memorie externă – W25Q512JVEIQ
Capacitate: 512 Mbit (64 MB)

Interfață: Quad SPI (QPI)

Frecvență de operare: Până la 133 MHz

Tensiune de alimentare: 2.7 V – 3.6 V

Caracteristici: rezistență mare (100.000 cicluri scriere/ștergere)

Ceas în timp real – DS3231SN#
Precizie: ±2 ppm între 0°C și +40°C

Interfață: I²C

Caracteristici: Oscilator cu cristal compensat termic (TCXO) integrat

Tensiune de funcționare: 2.3 V – 5.5 V

Funcționalități suplimentare: suport pentru baterie de rezervă, 2 alarme programabile, ieșire pătrată 1Hz

Monitor baterie – MAX17048G+T10
Funcție: Indicator de încărcare pentru baterii Li-ion/Li-Po cu o singură celulă

Interfață: I²C

Tensiune: 2.5 V – 4.5 V

Consum de putere: Curent de repaus ultra-redus (~23 µA)



Utilizarea pinilor ESP32-C6
Dispozitiv	Pin ESP32-C6	Componentă conectată	Funcție
U2 - ESP32-C6	GPIO0	Buton BOOT	Activează modul bootloader la pornire (input)
U2 - ESP32-C6	GPIO1	UART TX	Comunicație serială pentru debug/programare
U2 - ESP32-C6	GPIO2	UART RX	Comunicație serială pentru debug/programare
U2 - ESP32-C6	GPIO3	BME688 (I²C SDA)	Linie date senzor mediu
U2 - ESP32-C6	GPIO4	BME688 (I²C SCL)	Linie ceas senzor mediu
U2 - ESP32-C6	GPIO5	MAX17048 (I²C SDA)	Linie date monitor baterie (bus partajat)
U2 - ESP32-C6	GPIO6	MAX17048 (I²C SCL)	Linie ceas monitor baterie (bus partajat)
U2 - ESP32-C6	GPIO7	Qwiic SDA	Comunicație I²C (senzori partajați)
U2 - ESP32-C6	GPIO8	Qwiic SCL	Comunicație I²C (senzori partajați)
U2 - ESP32-C6	GPIO9	DS3231 (RTC SDA)	Linie date pentru ceas în timp real
U2 - ESP32-C6	GPIO10	DS3231 (RTC SCL)	Linie ceas pentru ceas în timp real
U2 - ESP32-C6	GPIO18	E-Paper (SPI MOSI)	Date seriale către display
U2 - ESP32-C6	GPIO19	E-Paper (SPI CLK)	Ceas serial pentru display
U2 - ESP32-C6	GPIO20	E-Paper (CS)	Linie de selecție cip display
U2 - ESP32-C6	GPIO21	E-Paper (DC)	Control Date/Comandă display
U2 - ESP32-C6	GPIO22	E-Paper (RST)	Linie de reset display
U2 - ESP32-C6	GPIO23	E-Paper (BUSY)	Semnal stare ocupat display
U2 - ESP32-C6	GPIO13	Card SD (SPI CS)	Linie de selecție cip card SD
U2 - ESP32-C6	GPIO14	Card SD (SPI MISO)	Master In Slave Out – citire de pe SD
U2 - ESP32-C6	GPIO15	Card SD (SPI MOSI)	Master Out Slave In – scriere pe SD
U2 - ESP32-C6	GPIO16	Card SD (SPI CLK)	Ceas SPI pentru card SD



Bill of Materials:
BOOT_BUTTON	BUTTON_CUSYOMV1	https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k
C1	ESP32_WROVER_EAGLE-LTSPICE_CC0402	https://eu.mouser.com/ProductDetail/YAGEO/CC0402MRX5R5BB106?qs=zEY9bCHj09eCmUJdZuS5Lg%3D%3D
C1_BAT	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C1_BAT1	EAGLE-LTSPICE_CC0402	n/a
C1_BAT2	EAGLE-LTSPICE_CC0402	n/a
C2	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C2_BAT\	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C3	RCL_CPOL-EUCT3528	n/a
C4	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C4_USB	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C5	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C5_USB	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C6	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C7	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C8	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C9	EAGLE-LTSPICE_CC0402	n/a
C10	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
C10_SUPERCAP	CPH3225A	https://www.snapeda.com/parts/CPH3225A/Seiko+Instruments/view-part/?ref=eda
CHANGE_BUTTON	BUTTON_CUSYOMV1	https://industry.panasonic.com/global/en/products/control/switch-light-touch/number/evqpuj02k
CHG_LED	ADAFRUIT_LEDCHIP-LED0603	https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603
C_DELAY	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
D1	USBLC6-2SC6Y	https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda
D2	ESP32_WROVER_AVX---SD0805S020S1R0_AVX_...	https://eu.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D
D3	MBR0530	https://eu.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D
D4	MBR0530	https://www.snapeda.com/parts/MBR0530/Onsemi/view-part/?ref=eda
D5	MBR0530	https://www.snapeda.com/parts/MBR0530/Onsemi/view-part/?ref=eda
D6	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
D7	ESP32_WROVER_AVX---SD0805S020S1R0_AVX_...	https://eu.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D
D8	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
D9	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
D10	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
D11	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
D12	PGB1010603MR	https://www.snapeda.com/parts/PGB1010603MR/Littelfuse/view-part/?ref=eda
EPD_C1	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C2	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C5	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C6	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C7	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C8	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C9	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C10	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C11	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
EPD_C12	ESP32_WROVER_EAGLE-LTSPICE_CC0402	n/a
IC1	BD5229G-TR	https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor
IC4	XC6220A331MR-G	https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex
J1	FH34SRJ-24S-0.5SH_99_	https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex
J2	SAMACSYS_PARTS_USB4110-GF-A	https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY
J3	QWIIC_CONNECTORJS-1MM	n/a
J4	112A-TAAR-R03_ATTEND	https://store.comet.srl.ro/Catalogue/Product/43497/
L1	744043680IND_4828-WE-TPC_WRE	https://eu.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D
PFMF.050.1	ESP32C6_VARISTORCN1812	https://www.mouser.co.uk/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D
Q1	ESP32_WROVER_SPARKFUN-DISCRETESEMI_MOSFET_...	https://componentsearchengine.com/part-view/DMG2305UX-7/Diodes%20Incorporated
Q2	ESP32_WROVER_SPARKFUN-DISCRETESEMI_MOSFET_...	n/a
Q3	D8	https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay
R1	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R1-PINH	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R1-PINH1	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R1_BAT	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R1_PWRUSB	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R2	ESP32_WROVER_EAGLE-LTSPICE_RR0402	https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL
R2-PINH	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R2-PINH1	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R2-USB	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R2-USB1	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R2_BAT	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R3	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R4	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R5	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R6	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R7	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R8	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R9	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R10	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
RESET_BUTTON	BUTTON_CUSYOMV1	https://industry.panasonic.com/global/en/products/control/switch/light-touch/number/evqpuj02k
R_BOOT	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R_CAPACITOR	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R_CHANGE	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R_CL1	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
R_RESET	ESP32_WROVER_EAGLE-LTSPICE_RR0402	n/a
SENSOR2	ESP32_WROVER_BME680_BME680	https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home
SJ1	SJ	https://grabcad.com/library/solder-jumpers-1
U1	W25Q512JVEIQ	https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda
U2	ESP32-C6-WROOM-1-N8	https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda
U3	DS3231SN#	https://www.snapeda.com/parts/DS3231SN%23/Analog+Devices/view-part/?ref=eda
U4	MAX17048G+T10	https://www.snapeda.com/parts/MAX17048G+T10/Analog+Devices/view-part/?ref=eda
U5	ESP32_WROVER_SPARKFUN-IC-POWER_MCP73831	https://eu.mouser.com/ProductDetail/Microchip-Technology/MCP73831T-2ACI-OT?qs=yUQqVecv4qvbBQBGbHx0Mw%3D%3Dcf


*Schema-bloc atasata in imagini*