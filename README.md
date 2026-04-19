InkTime Smartwatch

Diagrama se afla in images

Bill of Materials (BOM)

## Bill of Materials (BOM)

| Categorie | Capsula | Denumire Schematic | JLC |
| :--- | :--- | :--- | :--- |
| **Capacitors** | **0201** | C1, C2, C3, C4, C5, C7, C8, C9, C11, C12, C13, C16, C17, C18, C19, C22, C23, C27, C29, C30, C31, C32, C34, C37, C38, C42, EPD_C5 | [JLCPCB](https://jlcpcb.com/partdetail/16204-CL05A106MQ5NUNC/C15525) |
| | **0402** | C6, C14, C15, C20, C21, C24, C25, C33, C39, C43, EPD_C1, EPD_C2, EPD_C6, EPD_C7, EPD_C8, EPD_C9, EPD_C10, EPD_C11, EPD_C12, C2-EP-DR1 | [JLCPCB](https://jlcpcb.com/partdetail/C9900006337) |
| **Resistors** | **0201** | R2, R3, R4, R5, R7, R8, R9, R17, R18, R_TYPE_SEL, R1_EP_DR, R2_EP_DR, R2_PWR_EPD, R1_USB, R2_USB | [JLCPCB](https://jlcpcb.com/partdetail/26484-0402WGF1003TCE/C25741) |
| **Inductors** | **0402** | L1, L2, L3 | [JLCPCB](https://jlcpcb.com/partdetail/6763488-FTC252012SR47MBCA/C5832368) |
| | **SMD** | L5, L7 | [JLCPCB](https://jlcpcb.com/partdetail/Walsin_TechCorp-WR06X60R4FTL/C168340) |
| **ICs** | **BGA/WLCSP** | U1 (nRF52840) | [JLCPCB](https://jlcpcb.com/partdetail/NordicSemicon-NRF52840_QIAAR/C190794) |
| | **BGA/WLCSP** | IC1 (BQ25180YBGR) | [JLCPCB](https://jlcpcb.com/partdetail/TexasInstruments-BQ25180YBGR/C3682423) |
| | **BGA/WLCSP** | IC2 (DRV2605YZFR) | [JLCPCB](https://jlcpcb.com/partdetail/TexasInstruments-DRV2605YZFR/C81079) |
| | **BGA/WLCSP** | IC9 (RT6160AWSC) | [JLCPCB](https://jlcpcb.com/partdetail/RichtekTech-RT6160AWSC/C7065276) |
| | **LGA** | IC3 (BMA421) | [JLCPCB](https://jlcpcb.com/partdetail/BoschSensortec-BMA421/C5242966) |
| | **SON/TDFN** | U3 (MAX17048) | [JLCPCB](https://jlcpcb.com/partdetail/2777647-MAX17048GT10/C2682616) |
| **Diodes/FETs** | **SOD-123** | D2, D4, D5 | [JLCPCB](https://jlcpcb.com/partdetail/ST_Semtech-1N4148W/C81598) |
| | **SOT-23** | Q1 (DMG2305) | [JLCPCB](https://jlcpcb.com/partdetail/TECHPUBLIC-DMG2305UX/C2940629) |
| | **SOT-323** | Q3 (SI1308EDL) | [JLCPCB](https://jlcpcb.com/partdetail/VishayIntertech-SI1308EDL_T1GE3/C469327) |
| | **SOT-23-6** | D3 (USBLC6) | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-USBLC62SC6/C7519) |
| **Connectors** | **FPC 24** | J1 | [JLCPCB](https://jlcpcb.com/partdetail/MOLEX-5034802400/C122434) |
| | **USB-C** | J4 | [JLCPCB](https://jlcpcb.com/partdetail/EverlightElec-16_213SDRC_S530_A3TR8/C71911) |
| | **Tag-Connect** | J2 (TC2030) | [JLCPCB](https://jlcpcb.com/partdetail/MicrochipTech-TC2030_CLIP3PACK/C5444772) |
| **User I/O** | **Switch** | SW_DN, SW_ENT, SW_UP | [JLCPCB](https://jlcpcb.com/partdetail/ALPSALPINE-SKRKAEE020/C115357) |
| **RF** | **Antenna** | ANT1 | [JLCPCB](https://jlcpcb.com/partdetail/JohansonDielectrics-2450AT18B100E/C2917717) |
| **Oscillator** | **Crystal** | X1, X2 | [JLCPCB](https://jlcpcb.com/partdetail/STMicroelectronics-BALNRF01D3/C87765) |
| **Mechanical** | **Custom** | Baterie, Display, Shaker | - |


Functionalitate Hardware

Proiectul este bazat pe microcontroller-ul nRF52840 care gestioneaza toate perifericele.

Alimentarea se face din baterie LiPo, care este incarcata prin circuitul BQ25180. Tensiunea este stabilizata folosind convertorul RT6160.

Fuel gauge MAX17048 monitorizeaza nivelul bateriei si transmite datele catre MCU.

Display-ul E-Paper este controlat de MCU prin SPI (semnale EPD_CS, EPD_DC, EPD_RST, EPD_BUSY).

IMU-ul comunica cu MCU prin I2C (SCL, SDA).

Haptic driver DRV2605 controleaza motorul de vibratii.

USB-C este folosit pentru alimentare si este protejat de circuitul ESD.

Butoanele sunt conectate la pini GPIO si sunt folosite pentru interactiunea utilizatorului.


## Pin Mapping (nRF52840)

### SPI - E-Paper Display
- MOSI -> P0.31
- SCK -> P0.30
- EPD_CS -> P0.04
- EPD_DC -> P0.13
- EPD_RST -> P0.14
- EPD_BUSY -> P0.15

### I2C (IMU + Fuel Gauge + Haptic)
- SDA -> P1.01
- SCL -> P1.02

### IMU
- IMU_INT1 -> P0.19
- IMU_INT2 -> P0.20

### Haptic Driver
- HAPTIC_EN -> P1.09

### Fuel Gauge
- ALERT -> P0.21

### USB
- D+ -> pin dedicat USB (D+)
- D- -> pin dedicat USB (D-)
- VBUS -> alimentare

### Debug (SWD)
- SWDIO -> SWDIO
- SWDCLK -> SWDCLK
- RESET -> P0.18

### Alte GPIO
- Butoane -> P0.13, P0.14 (shared sau configurabile)

Power Consumption

Estimare consum:

- nRF52840: ~5-10 mA
- Display E-Paper: ~10-20 mA (in refresh)
- IMU: ~1-2 mA
- Haptic: ~50-100 mA (doar activ)
- restul: <5 mA

Consum total mediu: ~20-30 mA

---

PCB Design

Placa este pe 2 layere (Top + Bottom).

Toate componentele sunt plasate pe Top.

Planul de masa este prezent pe ambele layere si conectat prin via stitching.

Zona antenei este lasata fara copper si fara trasee sub ea.

Traseele de alimentare sunt mai groase fata de cele de semnal.

---

3D Design

Modelul 3D contine:
- PCB complet
- baterie
- display
- carcasa

Toate componentele sunt integrate intr-un volum compact.

Exista si exploded view pentru vizualizare.

---

Images

Randari ale PCB-ului si dispozitivului sunt incluse in folderul Images.

---

Concluzie

Proiectul InkTime este un smartwatch functional bazat pe nRF52840.

Integreaza alimentare, afisare, senzori si feedback haptic intr-un design compact.

Structura hardware este corecta si respecta cerintele proiectului.
