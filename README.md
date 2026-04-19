InkTime Smartwatch
Bill of Materials (BOM)

| Componenta | Model | Rol |
|-----------|------|-----|
| MCU | nRF52840 | control principal |
| Charger | BQ25180YBGR | incarcare baterie |
| DC/DC | RT6160AWSC | conversie tensiune |
| Fuel Gauge | MAX17048G+T10 | monitorizare baterie |
| Haptic Driver | DRV2605YZFR | vibratii |
| IMU | (generic) | senzori |
| USB-C | KH-TYPE-C-16P | alimentare |
| ESD | USBLC6-2SC6Y | protectie |
| Display | E-Paper | afisaj |
| Rezistente | 0201 | bias, pull-up |
| Condensatoare | 0201 / 0402 | filtrare |
| Inductori | diverse | alimentare |

---

Functionalitate Hardware

Proiectul este bazat pe microcontroller-ul nRF52840 care gestioneaza toate perifericele.

Alimentarea se face din baterie LiPo, care este incarcata prin circuitul BQ25180. Tensiunea este stabilizata folosind convertorul RT6160.

Fuel gauge MAX17048 monitorizeaza nivelul bateriei si transmite datele catre MCU.

Display-ul E-Paper este controlat de MCU prin SPI (semnale EPD_CS, EPD_DC, EPD_RST, EPD_BUSY).

IMU-ul comunica cu MCU prin I2C (SCL, SDA).

Haptic driver DRV2605 controleaza motorul de vibratii.

USB-C este folosit pentru alimentare si este protejat de circuitul ESD.

Butoanele sunt conectate la pini GPIO si sunt folosite pentru interactiunea utilizatorului.


Pin Mapping (nRF52840)

- SPI Display:
  - MOSI -> P0.xx
  - SCK -> P0.xx
  - EPD_CS -> P0.xx
  - EPD_DC -> P0.xx
  - EPD_RST -> P0.xx
  - EPD_BUSY -> P0.xx

- I2C:
  - SDA -> P0.xx
  - SCL -> P0.xx

- IMU:
  - INT1 -> GPIO
  - INT2 -> GPIO

- Haptic:
  - HAPTIC_EN -> GPIO

- USB:
  - D+ / D- -> pini dedicati
  - VBUS -> alimentare

- Debug:
  - SWDIO
  - SWDCLK
  - RESET

- Fuel Gauge:
  - ALERT -> GPIO

---

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
