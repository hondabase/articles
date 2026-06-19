---
summary: 'Uma base de dados abrangente de tabelas de compensação de bateria (tempo morto/latência) para injetores de combustível originais (OEM) e de pós-venda.'
tags: [injectors, fuel-offsets, tuning, reference]
complexity: intermediate
---

# Base de Dados de Compensações de Injetores de Combustível

Este artigo serve como uma base de dados abrangente e gerida pela comunidade de tabelas de compensação de tensão da bateria (tempo morto / latência) para injetores de combustível originais (OEM) e de pós-venda. Na afinação (tuning) do motor, a definição correta das compensações dos injetores é crucial para garantir uma alimentação de combustível estável e qualidade de ralenti, especialmente sob tensões de bateria variáveis.

### Índice

- [Accel](#accel)
- [Acura](#acura)
- [Audi](#audi)
- [Blitz](#blitz)
- [Bosch](#bosch)
- [Bosch EV14](#bosch-ev14)
- [Deatschwerks](#deatschwerks)
- [Denso](#denso)
- [Dodge](#dodge)
- [Edelbrock](#edelbrock)
- [Ford](#ford)
- [Fuel Injector Clinic](#fuel-injector-clinic)
- [HKS](#hks)
- [Hahn Racecraft](#hahn-racecraft)
- [Holley](#holley)
- [Honda](#honda)
- [Injector Dynamics](#injector-dynamics)
- [MSD](#msd)
- [Mitsubishi](#mitsubishi)
- [Nissan](#nissan)
- [Precision Turbo (Rochester)](#precision-turbo-rochester)
- [RC Engineering](#rc-engineering)
- [Sard](#sard)
- [Siemens Deka](#siemens-deka)
- [Subaru](#subaru)
- [Toyota](#toyota)
- [Ultimate Racing](#ultimate-racing)
- [Vennom](#vennom)
- [Volkswagen](#volkswagen)

---

## Accel

### Peak and Hold

#### Accel 578CC

- **Taxa de Fluxo:** 578 CC/min (aprox. 55.39 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.970 ms |
| 10.00V | 0.830 ms |
| 12.13V | 0.710 ms |
| 14.16V | 0.620 ms |
| 16.08V | 0.550 ms |
| 24.56V | 0.480 ms |

#### Accel 872CC

- **Taxa de Fluxo:** 872 CC/min (aprox. 83.56 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.110 ms |
| 10.00V | 0.930 ms |
| 12.13V | 0.800 ms |
| 14.16V | 0.700 ms |
| 16.08V | 0.610 ms |
| 24.56V | 0.530 ms |

---

## Acura

### Peak and Hold

#### CL

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 0.980 ms |
| 10.00V | 0.730 ms |
| 12.00V | 0.520 ms |
| 13.00V | 0.430 ms |
| 14.00V | 0.360 ms |
| 15.00V | 0.250 ms |
| 16.00V | 0.220 ms |

### Integra (92-96 VTEC)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.220 ms |
| 10.05V | 0.790 ms |
| 12.13V | 0.560 ms |
| 14.16V | 0.400 ms |
| 16.08V | 0.290 ms |
| 24.56V | 0.290 ms |

### NSX

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.610 ms |
| 10.05V | 0.510 ms |
| 12.13V | 0.430 ms |
| 14.16V | 0.360 ms |
| 16.08V | 0.310 ms |
| 24.56V | 0.250 ms |

### RSX (02-04)

- **Taxa de Fluxo:** 290 CC/min (aprox. 27.79 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.000 ms |
| 10.05V | 0.830 ms |
| 12.13V | 0.690 ms |
| 14.16V | 0.580 ms |
| 16.08V | 0.500 ms |
| 24.56V | 0.430 ms |

### RSX Type-S (02-04)

- **Taxa de Fluxo:** 330 CC/min (aprox. 31.62 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.060 ms |
| 10.05V | 0.890 ms |
| 12.13V | 0.770 ms |
| 14.16V | 0.650 ms |
| 16.08V | 0.560 ms |
| 24.56V | 0.500 ms |

### RDX

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.500 ms |
| 10.00V | 1.800 ms |
| 12.00V | 1.410 ms |
| 14.00V | 1.100 ms |
| 16.00V | 1.040 ms |

---

## Audi

### S4/TT

- **Taxa de Fluxo:** 340 CC/min (aprox. 32.58 LB/hora)
- **Impedância:** 14 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.880 ms |
| 10.00V | 0.740 ms |
| 12.13V | 0.630 ms |
| 14.16V | 0.540 ms |
| 16.08V | 0.470 ms |
| 24.56V | 0.400 ms |

---

## Blitz

### Blitz 850CC

- **Taxa de Fluxo:** 850 CC/min (aprox. 81.46 LB/hora)
- **Impedância:** 14 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.040 ms |
| 10.00V | 0.840 ms |
| 12.13V | 0.700 ms |
| 14.16V | 0.590 ms |
| 16.08V | 0.520 ms |
| 24.56V | 0.440 ms |

---

## Bosch

### Peak and Hold

#### Bosch 1545CC

- **Taxa de Fluxo:** 1545 CC/min (aprox. 148.06 LB/hora)
- **Impedância:** 5 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.270 ms |
| 10.00V | 1.040 ms |
| 12.13V | 0.890 ms |
| 14.16V | 0.760 ms |
| 16.08V | 0.680 ms |
| 24.56V | 0.610 ms |

---

## Bosch EV14

### 1000CC

#### 1000CC at 29 PSI

- **Taxa de Fluxo:** 816 CC/min (aprox. 78.20 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.010 ms |
| 10.00V | 1.450 ms |
| 12.00V | 1.010 ms |
| 14.00V | 0.700 ms |
| 16.00V | 0.480 ms |

#### 1000CC at 43.5 PSI

- **Taxa de Fluxo:** 1000 CC/min (aprox. 95.83 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.370 ms |
| 10.00V | 1.720 ms |
| 12.00V | 1.220 ms |
| 14.00V | 0.880 ms |
| 16.00V | 0.680 ms |

#### 1000CC at 58 PSI

- **Taxa de Fluxo:** 1155 CC/min (aprox. 110.68 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.570 ms |
| 10.00V | 1.920 ms |
| 12.00V | 1.410 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.780 ms |

#### 1000CC at 72 PSI

- **Taxa de Fluxo:** 1291 CC/min (aprox. 123.72 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.910 ms |
| 10.00V | 2.190 ms |
| 12.00V | 1.520 ms |
| 14.00V | 1.150 ms |
| 16.00V | 0.910 ms |

---

## Deatschwerks

### Deatschwerks 600CC

- **Taxa de Fluxo:** 600 CC/min (aprox. 57.50 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.350 ms |
| 10.00V | 2.000 ms |
| 12.00V | 1.600 ms |
| 14.00V | 1.300 ms |
| 16.00V | 1.200 ms |

### Deatschwerks 800CC

- **Taxa de Fluxo:** 800 CC/min (aprox. 76.66 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.980 ms |
| 10.00V | 1.550 ms |
| 12.00V | 1.320 ms |
| 14.00V | 1.110 ms |
| 16.00V | 0.990 ms |

---

## Denso

### Peak and Hold

#### da phearable.net

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.660 ms |
| 11.00V | 0.580 ms |
| 12.00V | 0.500 ms |
| 13.00V | 0.410 ms |
| 14.00V | 0.340 ms |

#### Denso 1600CC

- **Taxa de Fluxo:** 1600 CC/min (aprox. 153.33 LB/hora)
- **Impedância:** 5 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.990 ms |
| 11.00V | 0.840 ms |
| 12.00V | 0.720 ms |
| 13.00V | 0.600 ms |
| 14.00V | 0.500 ms |

#### Denso 550CC

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.910 ms |
| 10.00V | 1.240 ms |
| 11.00V | 1.040 ms |
| 12.00V | 0.870 ms |
| 13.00V | 0.750 ms |
| 14.00V | 0.640 ms |
| 16.00V | 0.470 ms |

#### Denso 660CC

- **Taxa de Fluxo:** 660 CC/min (aprox. 63.25 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.710 ms |
| 10.00V | 1.150 ms |
| 11.00V | 0.990 ms |
| 12.00V | 0.860 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.640 ms |
| 16.00V | 0.470 ms |

#### Denso 720CC

- **Taxa de Fluxo:** 720 CC/min (aprox. 69.00 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.990 ms |
| 10.00V | 1.350 ms |
| 11.00V | 1.140 ms |
| 12.00V | 0.990 ms |
| 13.00V | 0.860 ms |
| 14.00V | 0.750 ms |
| 16.00V | 0.600 ms |

---

## Dodge

### 4.7

- **Taxa de Fluxo:** 273 CC/min (aprox. 26.16 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.350 ms |
| 10.00V | 1.750 ms |
| 12.00V | 1.220 ms |
| 14.00V | 0.890 ms |
| 15.00V | 0.730 ms |
| 16.00V | 0.610 ms |

### SRT-4 (2003)

- **Taxa de Fluxo:** 525 CC/min (aprox. 50.31 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.450 ms |
| 10.00V | 0.920 ms |
| 12.00V | 0.500 ms |
| 14.00V | 0.220 ms |
| 15.00V | 0.130 ms |
| 16.00V | 0.080 ms |

### SRT-4 (2004+)

- **Taxa de Fluxo:** 577 CC/min (aprox. 55.29 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.330 ms |
| 10.00V | 1.620 ms |
| 12.00V | 1.000 ms |
| 14.00V | 0.610 ms |
| 15.00V | 0.480 ms |
| 16.00V | 0.390 ms |

### Viper (96-2002)

- **Taxa de Fluxo:** 336 CC/min (aprox. 32.20 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.000 ms |
| 10.00V | 2.100 ms |
| 12.00V | 1.500 ms |
| 14.00V | 1.090 ms |
| 15.00V | 0.960 ms |
| 16.00V | 0.890 ms |

---

## Edelbrock

### Edelbrock 630CC

- **Taxa de Fluxo:** 630 CC/min (aprox. 60.37 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.450 ms |
| 10.00V | 0.760 ms |
| 12.00V | 0.390 ms |
| 14.00V | 0.150 ms |
| 15.00V | 0.040 ms |
| 16.00V | 0.010 ms |

---

## Ford

### Motorsport

#### Ford 378CC

- **Taxa de Fluxo:** 378 CC/min (aprox. 36.22 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.320 ms |
| 10.00V | 1.150 ms |
| 12.00V | 0.690 ms |
| 14.00V | 0.410 ms |
| 15.00V | 0.320 ms |
| 16.00V | 0.250 ms |

#### Ford 441CC

- **Taxa de Fluxo:** 441 CC/min (aprox. 42.26 LB/hora)
- **Impedância:** 14 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.150 ms |
| 10.00V | 1.140 ms |
| 12.00V | 0.750 ms |
| 14.00V | 0.560 ms |
| 15.00V | 0.490 ms |
| 16.00V | 0.420 ms |

#### Ford 809CC

- **Taxa de Fluxo:** 809 CC/min (aprox. 77.53 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.540 ms |
| 10.00V | 1.780 ms |
| 12.00V | 1.330 ms |
| 14.00V | 1.050 ms |
| 15.00V | 0.960 ms |
| 16.00V | 0.890 ms |

#### Peak and Hold

- **Taxa de Fluxo:** 1600 CC/min (aprox. 153.33 LB/hora)
- **Impedância:** 5 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.310 ms |
| 10.00V | 1.610 ms |
| 12.00V | 1.110 ms |
| 14.00V | 0.830 ms |
| 15.00V | 0.720 ms |
| 16.00V | 0.670 ms |

#### Peak and Hold

- **Taxa de Fluxo:** 1680 CC/min (aprox. 160.99 LB/hora)
- **Impedância:** 5 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.470 ms |
| 10.00V | 1.800 ms |
| 12.00V | 1.280 ms |
| 14.00V | 0.940 ms |
| 15.00V | 0.800 ms |
| 16.00V | 0.700 ms |

### Mustang GT (96-03)

- **Taxa de Fluxo:** 200 CC/min (aprox. 19.17 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.150 ms |
| 11.00V | 0.940 ms |
| 12.00V | 0.800 ms |
| 13.00V | 0.670 ms |
| 14.00V | 0.540 ms |

### Mustang (84-95)

- **Taxa de Fluxo:** 200 CC/min (aprox. 19.17 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.520 ms |
| 10.00V | 0.860 ms |
| 12.00V | 0.560 ms |
| 14.00V | 0.340 ms |
| 15.00V | 0.200 ms |
| 16.00V | 0.110 ms |

### Mustang Cobra

- **Taxa de Fluxo:** 252 CC/min (aprox. 24.15 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.570 ms |
| 10.00V | 0.910 ms |
| 12.00V | 0.590 ms |
| 14.00V | 0.360 ms |
| 15.00V | 0.250 ms |
| 16.00V | 0.190 ms |

---

## Fuel Injector Clinic

### Peak and Hold

#### Fuel Injector Clinic 650CC

- **Taxa de Fluxo:** 650 CC/min (aprox. 62.29 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.890 ms |
| 10.00V | 1.130 ms |
| 12.00V | 0.780 ms |
| 14.00V | 0.540 ms |
| 15.00V | 0.450 ms |
| 16.00V | 0.390 ms |

#### Fuel Injector Clinic 850CC

- **Taxa de Fluxo:** 850 CC/min (aprox. 81.46 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.560 ms |
| 10.00V | 1.020 ms |
| 12.00V | 0.740 ms |
| 14.00V | 0.510 ms |
| 15.00V | 0.430 ms |
| 16.00V | 0.380 ms |

#### Fuel Injector Clinic 950CC

- **Taxa de Fluxo:** 950 CC/min (aprox. 91.04 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.050 ms |
| 10.00V | 1.300 ms |
| 12.00V | 0.880 ms |
| 14.00V | 0.650 ms |
| 15.00V | 0.570 ms |
| 16.00V | 0.500 ms |

---

## HKS

### Peak and Hold

#### HKS 1000CC

- **Taxa de Fluxo:** 1000 CC/min (aprox. 95.83 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.900 ms |
| 10.00V | 1.310 ms |
| 11.00V | 1.140 ms |
| 12.00V | 1.040 ms |
| 13.00V | 0.970 ms |
| 14.00V | 0.890 ms |
| 16.00V | 0.710 ms |

---

## Hahn Racecraft

### Peak and Hold

#### Hahn Racecraft 625CC

- **Taxa de Fluxo:** 625 CC/min (aprox. 59.89 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.920 ms |
| 10.00V | 1.190 ms |
| 12.00V | 0.790 ms |
| 14.00V | 0.570 ms |
| 15.00V | 0.500 ms |
| 16.00V | 0.460 ms |

---

## Holley

### Peak and Hold

#### Holley 788CC

- **Taxa de Fluxo:** 788 CC/min (aprox. 75.51 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.680 ms |
| 10.00V | 1.020 ms |
| 12.00V | 0.710 ms |
| 14.00V | 0.540 ms |
| 15.00V | 0.440 ms |
| 16.00V | 0.380 ms |

---

## Honda

### Peak and Hold

#### All Models (86-91) da Phearable.net

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.470 ms |
| 11.00V | 0.370 ms |
| 12.00V | 0.290 ms |
| 13.00V | 0.210 ms |
| 14.00V | 0.140 ms |

#### All Models (86-91)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.590 ms |
| 10.05V | 0.480 ms |
| 12.13V | 0.410 ms |
| 14.16V | 0.350 ms |
| 16.08V | 0.300 ms |
| 24.56V | 0.250 ms |

#### Prelude (92-96 VTEC)

- **Taxa de Fluxo:** 330 CC/min (aprox. 31.62 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.120 ms |
| 10.00V | 0.720 ms |
| 11.00V | 0.560 ms |
| 12.00V | 0.450 ms |
| 13.00V | 0.350 ms |
| 14.00V | 0.270 ms |
| 16.00V | 0.210 ms |

### Civic (92-00 EX/SI)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 2.050 ms |
| 10.05V | 1.090 ms |
| 12.13V | 0.620 ms |
| 14.16V | 0.470 ms |
| 16.08V | 0.330 ms |
| 24.56V | 0.320 ms |

### Civic (92-00 LX/DX/HX)

- **Taxa de Fluxo:** 190 CC/min (aprox. 18.21 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.820 ms |
| 10.00V | 1.170 ms |
| 12.00V | 0.800 ms |
| 13.00V | 0.600 ms |
| 14.00V | 0.460 ms |
| 15.00V | 0.340 ms |
| 16.00V | 0.310 ms |

### Civic (01-Up LX/DX/HX)

- **Taxa de Fluxo:** 215 CC/min (aprox. 20.60 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.710 ms |
| 10.00V | 1.180 ms |
| 12.00V | 0.810 ms |
| 13.00V | 0.720 ms |
| 14.00V | 0.600 ms |
| 15.00V | 0.500 ms |
| 16.00V | 0.470 ms |

### Civic (01-Up EX)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.820 ms |
| 10.05V | 0.660 ms |
| 12.13V | 0.560 ms |
| 14.16V | 0.470 ms |
| 16.08V | 0.420 ms |
| 24.56V | 0.360 ms |

### Civic (03-Up SI) (CRV 02+)

- **Taxa de Fluxo:** 290 CC/min (aprox. 27.79 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.060 ms |
| 10.05V | 0.910 ms |
| 12.13V | 0.790 ms |
| 14.16V | 0.680 ms |
| 16.08V | 0.610 ms |
| 24.56V | 0.530 ms |

### Civic (06-Up SI)

- **Taxa de Fluxo:** 330 CC/min (aprox. 31.62 LB/hora)
- **Impedância:** 10 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.960 ms |
| 10.05V | 0.820 ms |
| 12.13V | 0.680 ms |
| 14.16V | 0.570 ms |
| 16.08V | 0.500 ms |
| 24.56V | 0.420 ms |

### Prelude (97-02)

- **Taxa de Fluxo:** 290 CC/min (aprox. 27.79 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.900 ms |
| 10.00V | 1.240 ms |
| 11.00V | 1.020 ms |
| 12.00V | 0.850 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.630 ms |
| 16.00V | 0.440 ms |

### S2000

- **Taxa de Fluxo:** 360 CC/min (aprox. 34.50 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.780 ms |
| 10.00V | 1.270 ms |
| 11.00V | 1.110 ms |
| 12.00V | 0.950 ms |
| 13.00V | 0.810 ms |
| 14.00V | 0.710 ms |
| 16.00V | 0.590 ms |

---

## Injector Dynamics

### ID725

#### ID725 at 40 PSI

- **Taxa de Fluxo:** 690 CC/min (aprox. 66.12 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.910 ms |
| 10.00V | 1.320 ms |
| 12.00V | 1.030 ms |
| 14.00V | 0.775 ms |
| 16.00V | 0.660 ms |

#### ID725 at 43.5 PSI

- **Taxa de Fluxo:** 715 CC/min (aprox. 68.52 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.975 ms |
| 10.00V | 1.355 ms |
| 12.00V | 1.040 ms |
| 14.00V | 0.795 ms |
| 16.00V | 0.730 ms |

#### ID725 at 45 PSI

- **Taxa de Fluxo:** 730 CC/min (aprox. 69.96 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.005 ms |
| 10.00V | 1.385 ms |
| 12.00V | 1.045 ms |
| 14.00V | 0.800 ms |
| 16.00V | 0.735 ms |

#### ID725 at 50 PSI

- **Taxa de Fluxo:** 770 CC/min (aprox. 73.79 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.095 ms |
| 10.00V | 1.420 ms |
| 12.00V | 1.065 ms |
| 14.00V | 0.830 ms |
| 16.00V | 0.770 ms |

#### ID725 at 55 PSI

- **Taxa de Fluxo:** 810 CC/min (aprox. 77.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.185 ms |
| 10.00V | 1.465 ms |
| 12.00V | 1.090 ms |
| 14.00V | 0.860 ms |
| 16.00V | 0.805 ms |

#### ID725 at 60 PSI

- **Taxa de Fluxo:** 850 CC/min (aprox. 81.46 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.270 ms |
| 10.00V | 1.520 ms |
| 12.00V | 1.115 ms |
| 14.00V | 0.895 ms |
| 16.00V | 0.835 ms |

#### ID725 at 65 PSI

- **Taxa de Fluxo:** 890 CC/min (aprox. 85.29 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.350 ms |
| 10.00V | 1.575 ms |
| 12.00V | 1.040 ms |
| 14.00V | 0.930 ms |
| 16.00V | 0.860 ms |

#### ID725 at 70 PSI

- **Taxa de Fluxo:** 925 CC/min (aprox. 88.64 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.440 ms |
| 10.00V | 1.630 ms |
| 12.00V | 1.175 ms |
| 14.00V | 0.970 ms |
| 16.00V | 0.865 ms |

#### ID725 at 75 PSI

- **Taxa de Fluxo:** 960 CC/min (aprox. 92.00 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.545 ms |
| 10.00V | 1.685 ms |
| 12.00V | 1.215 ms |
| 14.00V | 1.010 ms |
| 16.00V | 0.905 ms |

#### ID725 at 80 PSI

- **Taxa de Fluxo:** 990 CC/min (aprox. 94.87 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.675 ms |
| 10.00V | 1.740 ms |
| 12.00V | 1.265 ms |
| 14.00V | 1.045 ms |
| 16.00V | 0.930 ms |

#### ID725 at 85 PSI

- **Taxa de Fluxo:** 1020 CC/min (aprox. 97.75 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.840 ms |
| 10.00V | 1.790 ms |
| 12.00V | 1.320 ms |
| 14.00V | 1.075 ms |
| 16.00V | 0.955 ms |

#### ID725 at 90 PSI

- **Taxa de Fluxo:** 1050 CC/min (aprox. 100.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.035 ms |
| 10.00V | 1.845 ms |
| 12.00V | 1.375 ms |
| 14.00V | 1.100 ms |
| 16.00V | 0.985 ms |

#### ID725 at 95 PSI

- **Taxa de Fluxo:** 1080 CC/min (aprox. 103.50 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.250 ms |
| 10.00V | 1.900 ms |
| 12.00V | 1.435 ms |
| 14.00V | 1.125 ms |
| 16.00V | 1.020 ms |

#### ID725 at 100 PSI

- **Taxa de Fluxo:** 1110 CC/min (aprox. 106.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.965 ms |
| 12.00V | 1.490 ms |
| 14.00V | 1.155 ms |
| 16.00V | 1.055 ms |

#### ID725 at 105 PSI

- **Taxa de Fluxo:** 1140 CC/min (aprox. 109.25 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.040 ms |
| 12.00V | 1.540 ms |
| 14.00V | 1.185 ms |
| 16.00V | 1.020 ms |

#### ID725 at 110 PSI

- **Taxa de Fluxo:** 1170 CC/min (aprox. 112.12 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.120 ms |
| 12.00V | 1.580 ms |
| 14.00V | 1.220 ms |
| 16.00V | 1.055 ms |

#### ID725 at 115 PSI

- **Taxa de Fluxo:** 1200 CC/min (aprox. 115.00 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.219 ms |
| 12.00V | 1.615 ms |
| 14.00V | 1.260 ms |
| 16.00V | 1.055 ms |

#### ID725 at 120 PSI

- **Taxa de Fluxo:** 1235 CC/min (aprox. 118.35 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.300 ms |
| 12.00V | 1.650 ms |
| 14.00V | 1.300 ms |
| 16.00V | 1.070 ms |

### ID850

#### ID850 at 40 PSI

- **Taxa de Fluxo:** 845 CC/min (aprox. 80.98 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.195 ms |
| 10.00V | 1.495 ms |
| 12.00V | 1.115 ms |
| 14.00V | 0.885 ms |
| 16.00V | 0.710 ms |

#### ID850 at 43.5 PSI

- **Taxa de Fluxo:** 885 CC/min (aprox. 84.81 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.280 ms |
| 10.00V | 1.540 ms |
| 12.00V | 1.145 ms |
| 14.00V | 0.910 ms |
| 16.00V | 0.730 ms |

#### ID850 at 45 PSI

- **Taxa de Fluxo:** 905 CC/min (aprox. 86.73 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.320 ms |
| 10.00V | 1.560 ms |
| 12.00V | 1.160 ms |
| 14.00V | 0.920 ms |
| 16.00V | 0.735 ms |

#### ID850 at 50 PSI

- **Taxa de Fluxo:** 955 CC/min (aprox. 91.52 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.440 ms |
| 10.00V | 1.625 ms |
| 12.00V | 1.210 ms |
| 14.00V | 0.955 ms |
| 16.00V | 0.770 ms |

#### ID850 at 55 PSI

- **Taxa de Fluxo:** 1005 CC/min (aprox. 96.31 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.580 ms |
| 10.00V | 1.700 ms |
| 12.00V | 1.260 ms |
| 14.00V | 0.990 ms |
| 16.00V | 0.805 ms |

#### ID850 at 60 PSI

- **Taxa de Fluxo:** 1050 CC/min (aprox. 100.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.765 ms |
| 10.00V | 1.775 ms |
| 12.00V | 1.310 ms |
| 14.00V | 1.025 ms |
| 16.00V | 0.835 ms |

#### ID850 at 65 PSI

- **Taxa de Fluxo:** 1090 CC/min (aprox. 104.45 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.990 ms |
| 10.00V | 1.855 ms |
| 12.00V | 1.350 ms |
| 14.00V | 1.060 ms |
| 16.00V | 0.860 ms |

#### ID850 at 70 PSI

- **Taxa de Fluxo:** 1130 CC/min (aprox. 108.29 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.250 ms |
| 10.00V | 1.935 ms |
| 12.00V | 1.395 ms |
| 14.00V | 1.090 ms |
| 16.00V | 0.865 ms |

#### ID850 at 75 PSI

- **Taxa de Fluxo:** 1170 CC/min (aprox. 112.12 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.025 ms |
| 12.00V | 1.445 ms |
| 14.00V | 1.120 ms |
| 16.00V | 0.905 ms |

#### ID850 at 80 PSI

- **Taxa de Fluxo:** 1205 CC/min (aprox. 115.48 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.110 ms |
| 12.00V | 1.495 ms |
| 14.00V | 1.145 ms |
| 16.00V | 0.930 ms |

#### ID850 at 85 PSI

- **Taxa de Fluxo:** 1240 CC/min (aprox. 118.83 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.215 ms |
| 12.00V | 1.545 ms |
| 14.00V | 1.175 ms |
| 16.00V | 0.955 ms |

#### ID850 at 90 PSI

- **Taxa de Fluxo:** 1275 CC/min (aprox. 122.18 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.350 ms |
| 12.00V | 1.605 ms |
| 14.00V | 1.215 ms |
| 16.00V | 0.985 ms |

#### ID850 at 95 PSI

- **Taxa de Fluxo:** 1310 CC/min (aprox. 125.54 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.515 ms |
| 12.00V | 1.670 ms |
| 14.00V | 1.260 ms |
| 16.00V | 1.020 ms |

#### ID850 at 100 PSI

- **Taxa de Fluxo:** 1350 CC/min (aprox. 129.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.705 ms |
| 12.00V | 1.740 ms |
| 14.00V | 1.315 ms |
| 16.00V | 1.055 ms |

### ID1000

#### ID1000 at 40 PSI

- **Taxa de Fluxo:** 980 CC/min (aprox. 93.91 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.485 ms |
| 10.00V | 1.630 ms |
| 12.00V | 1.210 ms |
| 14.00V | 0.970 ms |
| 16.00V | 0.800 ms |

#### ID1000 at 43.5 PSI

- **Taxa de Fluxo:** 1015 CC/min (aprox. 97.27 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.600 ms |
| 10.00V | 1.675 ms |
| 12.00V | 1.240 ms |
| 14.00V | 0.990 ms |
| 16.00V | 0.805 ms |

#### ID1000 at 45 PSI

- **Taxa de Fluxo:** 1035 CC/min (aprox. 99.18 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.720 ms |
| 10.00V | 1.705 ms |
| 12.00V | 1.295 ms |
| 14.00V | 1.000 ms |
| 16.00V | 0.810 ms |

#### ID1000 at 50 PSI

- **Taxa de Fluxo:** 1085 CC/min (aprox. 103.98 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.855 ms |
| 10.00V | 1.750 ms |
| 12.00V | 1.355 ms |
| 14.00V | 1.025 ms |
| 16.00V | 0.815 ms |

#### ID1000 at 55 PSI

- **Taxa de Fluxo:** 1135 CC/min (aprox. 108.77 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.015 ms |
| 10.00V | 1.815 ms |
| 12.00V | 1.400 ms |
| 14.00V | 1.055 ms |
| 16.00V | 0.820 ms |

#### ID1000 at 60 PSI

- **Taxa de Fluxo:** 1180 CC/min (aprox. 113.08 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.195 ms |
| 10.00V | 1.880 ms |
| 12.00V | 1.440 ms |
| 14.00V | 1.080 ms |
| 16.00V | 0.845 ms |

#### ID1000 at 65 PSI

- **Taxa de Fluxo:** 1225 CC/min (aprox. 117.39 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.370 ms |
| 10.00V | 1.960 ms |
| 12.00V | 1.485 ms |
| 14.00V | 1.100 ms |
| 16.00V | 0.880 ms |

#### ID1000 at 70 PSI

- **Taxa de Fluxo:** 1265 CC/min (aprox. 121.22 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.550 ms |
| 10.00V | 2.050 ms |
| 12.00V | 1.530 ms |
| 14.00V | 1.125 ms |
| 16.00V | 0.925 ms |

#### ID1000 at 75 PSI

- **Taxa de Fluxo:** 1305 CC/min (aprox. 125.06 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.155 ms |
| 12.00V | 1.580 ms |
| 14.00V | 1.155 ms |
| 16.00V | 0.975 ms |

#### ID1000 at 80 PSI

- **Taxa de Fluxo:** 1345 CC/min (aprox. 128.89 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.280 ms |
| 12.00V | 1.625 ms |
| 14.00V | 1.195 ms |
| 16.00V | 1.020 ms |

#### ID1000 at 85 PSI

- **Taxa de Fluxo:** 1390 CC/min (aprox. 133.20 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.435 ms |
| 12.00V | 1.675 ms |
| 14.00V | 1.245 ms |
| 16.00V | 1.060 ms |

#### ID1000 at 90 PSI

- **Taxa de Fluxo:** 1435 CC/min (aprox. 137.52 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.610 ms |
| 12.00V | 1.725 ms |
| 14.00V | 1.305 ms |
| 16.00V | 1.095 ms |

#### ID1000 at 95 PSI

- **Taxa de Fluxo:** 1485 CC/min (aprox. 142.31 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.800 ms |
| 12.00V | 1.775 ms |
| 14.00V | 1.370 ms |
| 16.00V | 1.125 ms |

#### ID1000 at 100 PSI

- **Taxa de Fluxo:** 1530 CC/min (aprox. 146.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.995 ms |
| 12.00V | 1.855 ms |
| 14.00V | 1.440 ms |
| 16.00V | 1.155 ms |

### ID1050x

#### ID1050x at 40 PSI

- **Taxa de Fluxo:** 1020 CC/min (aprox. 97.75 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.920 ms |
| 10.00V | 1.410 ms |
| 12.00V | 1.115 ms |
| 14.00V | 0.920 ms |
| 16.00V | 0.790 ms |

#### ID1050x at 43.5 PSI

- **Taxa de Fluxo:** 1065 CC/min (aprox. 102.06 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.955 ms |
| 10.00V | 1.425 ms |
| 12.00V | 1.125 ms |
| 14.00V | 0.925 ms |
| 16.00V | 0.795 ms |

#### ID1050x at 45 PSI

- **Taxa de Fluxo:** 1085 CC/min (aprox. 103.98 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.970 ms |
| 10.00V | 1.435 ms |
| 12.00V | 1.130 ms |
| 14.00V | 0.930 ms |
| 16.00V | 0.800 ms |

#### ID1050x at 50 PSI

- **Taxa de Fluxo:** 1145 CC/min (aprox. 109.73 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.025 ms |
| 10.00V | 1.475 ms |
| 12.00V | 1.160 ms |
| 14.00V | 0.955 ms |
| 16.00V | 0.825 ms |

#### ID1050x at 55 PSI

- **Taxa de Fluxo:** 1205 CC/min (aprox. 115.48 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.080 ms |
| 10.00V | 1.515 ms |
| 12.00V | 1.190 ms |
| 14.00V | 0.980 ms |
| 16.00V | 0.845 ms |

#### ID1050x at 60 PSI

- **Taxa de Fluxo:** 1260 CC/min (aprox. 120.75 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.140 ms |
| 10.00V | 1.540 ms |
| 12.00V | 1.215 ms |
| 14.00V | 1.000 ms |
| 16.00V | 0.860 ms |

#### ID1050x at 65 PSI

- **Taxa de Fluxo:** 1305 CC/min (aprox. 125.06 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.195 ms |
| 10.00V | 1.560 ms |
| 12.00V | 1.225 ms |
| 14.00V | 1.010 ms |
| 16.00V | 0.855 ms |

#### ID1050x at 70 PSI

- **Taxa de Fluxo:** 1350 CC/min (aprox. 129.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.255 ms |
| 10.00V | 1.575 ms |
| 12.00V | 1.235 ms |
| 14.00V | 1.015 ms |
| 16.00V | 0.850 ms |

#### ID1050x at 75 PSI

- **Taxa de Fluxo:** 1390 CC/min (aprox. 133.20 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.340 ms |
| 10.00V | 1.610 ms |
| 12.00V | 1.250 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.850 ms |

#### ID1050x at 80 PSI

- **Taxa de Fluxo:** 1420 CC/min (aprox. 136.08 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.440 ms |
| 10.00V | 1.655 ms |
| 12.00V | 1.265 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.850 ms |

#### ID1050x at 85 PSI

- **Taxa de Fluxo:** 1455 CC/min (aprox. 139.43 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.555 ms |
| 10.00V | 1.705 ms |
| 12.00V | 1.280 ms |
| 14.00V | 1.030 ms |
| 16.00V | 0.855 ms |

#### ID1050x at 90 PSI

- **Taxa de Fluxo:** 1490 CC/min (aprox. 142.79 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.680 ms |
| 10.00V | 1.765 ms |
| 12.00V | 1.315 ms |
| 14.00V | 1.045 ms |
| 16.00V | 0.865 ms |

#### ID1050x at 95 PSI

- **Taxa de Fluxo:** 1530 CC/min (aprox. 146.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.815 ms |
| 10.00V | 1.825 ms |
| 12.00V | 1.355 ms |
| 14.00V | 1.075 ms |
| 16.00V | 0.880 ms |

#### ID1050x at 100 PSI

- **Taxa de Fluxo:** 1565 CC/min (aprox. 149.97 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.960 ms |
| 10.00V | 1.890 ms |
| 12.00V | 1.405 ms |
| 14.00V | 1.110 ms |
| 16.00V | 0.520 ms |

### ID1050-XDS

#### ID1050-XDS at 40 PSI

- **Taxa de Fluxo:** 1020 CC/min (aprox. 97.75 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.920 ms |
| 10.00V | 1.410 ms |
| 12.00V | 1.115 ms |
| 14.00V | 0.920 ms |
| 16.00V | 0.790 ms |

#### ID1050-XDS at 43.5 PSI

- **Taxa de Fluxo:** 1065 CC/min (aprox. 102.06 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.955 ms |
| 10.00V | 1.425 ms |
| 12.00V | 1.125 ms |
| 14.00V | 0.925 ms |
| 16.00V | 0.795 ms |

#### ID1050-XDS at 45 PSI

- **Taxa de Fluxo:** 1085 CC/min (aprox. 103.98 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.970 ms |
| 10.00V | 1.435 ms |
| 12.00V | 1.130 ms |
| 14.00V | 0.930 ms |
| 16.00V | 0.800 ms |

#### ID1050-XDS at 50 PSI

- **Taxa de Fluxo:** 1145 CC/min (aprox. 109.73 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.025 ms |
| 10.00V | 1.475 ms |
| 12.00V | 1.160 ms |
| 14.00V | 0.955 ms |
| 16.00V | 0.825 ms |

#### ID1050-XDS at 55 PSI

- **Taxa de Fluxo:** 1205 CC/min (aprox. 115.48 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.080 ms |
| 10.00V | 1.515 ms |
| 12.00V | 1.190 ms |
| 14.00V | 0.980 ms |
| 16.00V | 0.845 ms |

#### ID1050-XDS at 60 PSI

- **Taxa de Fluxo:** 1260 CC/min (aprox. 120.75 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.140 ms |
| 10.00V | 1.540 ms |
| 12.00V | 1.215 ms |
| 14.00V | 1.000 ms |
| 16.00V | 0.860 ms |

#### ID1050-XDS at 65 PSI

- **Taxa de Fluxo:** 1305 CC/min (aprox. 125.06 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.195 ms |
| 10.00V | 1.560 ms |
| 12.00V | 1.225 ms |
| 14.00V | 1.010 ms |
| 16.00V | 0.855 ms |

#### ID1050-XDS at 70 PSI

- **Taxa de Fluxo:** 1350 CC/min (aprox. 129.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.255 ms |
| 10.00V | 1.575 ms |
| 12.00V | 1.235 ms |
| 14.00V | 1.015 ms |
| 16.00V | 0.850 ms |

#### ID1050-XDS at 75 PSI

- **Taxa de Fluxo:** 1390 CC/min (aprox. 133.20 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.340 ms |
| 10.00V | 1.610 ms |
| 12.00V | 1.250 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.850 ms |

#### ID1050-XDS at 80 PSI

- **Taxa de Fluxo:** 1420 CC/min (aprox. 136.08 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.440 ms |
| 10.00V | 1.655 ms |
| 12.00V | 1.265 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.850 ms |

#### ID1050-XDS at 85 PSI

- **Taxa de Fluxo:** 1455 CC/min (aprox. 139.43 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.555 ms |
| 10.00V | 1.705 ms |
| 12.00V | 1.280 ms |
| 14.00V | 1.030 ms |
| 16.00V | 0.855 ms |

#### ID1050-XDS at 90 PSI

- **Taxa de Fluxo:** 1490 CC/min (aprox. 142.79 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.680 ms |
| 10.00V | 1.765 ms |
| 12.00V | 1.315 ms |
| 14.00V | 1.045 ms |
| 16.00V | 0.865 ms |

#### ID1050-XDS at 95 PSI

- **Taxa de Fluxo:** 1530 CC/min (aprox. 146.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.815 ms |
| 10.00V | 1.825 ms |
| 12.00V | 1.355 ms |
| 14.00V | 1.075 ms |
| 16.00V | 0.880 ms |

#### ID1050-XDS at 100 PSI

- **Taxa de Fluxo:** 1565 CC/min (aprox. 149.97 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.960 ms |
| 10.00V | 1.890 ms |
| 12.00V | 1.405 ms |
| 14.00V | 1.110 ms |
| 16.00V | 0.900 ms |

### ID1300x

#### ID1300x at 43.5 PSI

- **Taxa de Fluxo:** 1345 CC/min (aprox. 128.89 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.340 ms |
| 10.00V | 1.585 ms |
| 12.00V | 1.180 ms |
| 14.00V | 0.940 ms |
| 16.00V | 0.750 ms |

#### ID1300x at 45 PSI

- **Taxa de Fluxo:** 1365 CC/min (aprox. 130.81 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.385 ms |
| 10.00V | 1.605 ms |
| 12.00V | 1.195 ms |
| 14.00V | 0.950 ms |
| 16.00V | 0.760 ms |

#### ID1300x at 50 PSI

- **Taxa de Fluxo:** 1445 CC/min (aprox. 138.47 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.540 ms |
| 10.00V | 1.665 ms |
| 12.00V | 1.250 ms |
| 14.00V | 0.985 ms |
| 16.00V | 0.790 ms |

#### ID1300x at 55 PSI

- **Taxa de Fluxo:** 1520 CC/min (aprox. 145.66 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.695 ms |
| 10.00V | 1.730 ms |
| 12.00V | 1.300 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.820 ms |

#### ID1300x at 60 PSI

- **Taxa de Fluxo:** 1590 CC/min (aprox. 152.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.850 ms |
| 10.00V | 1.810 ms |
| 12.00V | 1.350 ms |
| 14.00V | 1.055 ms |
| 16.00V | 0.845 ms |

#### ID1300x at 65 PSI

- **Taxa de Fluxo:** 1655 CC/min (aprox. 158.60 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.010 ms |
| 10.00V | 1.890 ms |
| 12.00V | 1.395 ms |
| 14.00V | 1.095 ms |
| 16.00V | 0.875 ms |

#### ID1300x at 70 PSI

- **Taxa de Fluxo:** 1715 CC/min (aprox. 164.35 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.980 ms |
| 12.00V | 1.445 ms |
| 14.00V | 1.135 ms |
| 16.00V | 0.900 ms |

#### ID1300x at 75 PSI

- **Taxa de Fluxo:** 1775 CC/min (aprox. 170.10 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.080 ms |
| 12.00V | 1.500 ms |
| 14.00V | 1.175 ms |
| 16.00V | 0.930 ms |

#### ID1300x at 80 PSI

- **Taxa de Fluxo:** 1830 CC/min (aprox. 175.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 12.00V | 1.560 ms |
| 14.00V | 1.220 ms |
| 16.00V | 0.960 ms |

#### ID1300x at 85 PSI

- **Taxa de Fluxo:** 1885 CC/min (aprox. 180.64 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 12.00V | 1.620 ms |
| 14.00V | 1.260 ms |
| 16.00V | 0.995 ms |

#### ID1300x at 90 PSI

- **Taxa de Fluxo:** 1935 CC/min (aprox. 185.43 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 12.00V | 1.685 ms |
| 14.00V | 1.300 ms |
| 16.00V | 1.025 ms |

### ID1300x²

#### ID1300x² at 40 PSI

- **Taxa de Fluxo:** 1275 CC/min (aprox. 122.18 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.175 ms |
| 10.00V | 1.575 ms |
| 12.00V | 1.235 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.855 ms |

#### ID1300x² at 43.5 PSI

- **Taxa de Fluxo:** 1335 CC/min (aprox. 127.93 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.230 ms |
| 10.00V | 1.610 ms |
| 12.00V | 1.255 ms |
| 14.00V | 1.035 ms |
| 16.00V | 0.865 ms |

#### ID1300x² at 45 PSI

- **Taxa de Fluxo:** 1360 CC/min (aprox. 130.33 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.255 ms |
| 10.00V | 1.620 ms |
| 12.00V | 1.265 ms |
| 14.00V | 1.040 ms |
| 16.00V | 0.870 ms |

#### ID1300x² at 50 PSI

- **Taxa de Fluxo:** 1440 CC/min (aprox. 138.00 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.350 ms |
| 10.00V | 1.665 ms |
| 12.00V | 1.290 ms |
| 14.00V | 1.055 ms |
| 16.00V | 0.880 ms |

#### ID1300x² at 55 PSI

- **Taxa de Fluxo:** 1520 CC/min (aprox. 145.66 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.445 ms |
| 10.00V | 1.715 ms |
| 12.00V | 1.320 ms |
| 14.00V | 1.070 ms |
| 16.00V | 0.895 ms |

#### ID1300x² at 60 PSI

- **Taxa de Fluxo:** 1590 CC/min (aprox. 152.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.535 ms |
| 10.00V | 1.765 ms |
| 12.00V | 1.355 ms |
| 14.00V | 1.095 ms |
| 16.00V | 0.915 ms |

#### ID1300x² at 65 PSI

- **Taxa de Fluxo:** 1655 CC/min (aprox. 158.60 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.620 ms |
| 10.00V | 1.830 ms |
| 12.00V | 1.395 ms |
| 14.00V | 1.125 ms |
| 16.00V | 0.935 ms |

#### ID1300x² at 70 PSI

- **Taxa de Fluxo:** 1715 CC/min (aprox. 164.35 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.705 ms |
| 10.00V | 1.895 ms |
| 12.00V | 1.445 ms |
| 14.00V | 1.160 ms |
| 16.00V | 0.960 ms |

#### ID1300x² at 75 PSI

- **Taxa de Fluxo:** 1770 CC/min (aprox. 169.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.790 ms |
| 10.00V | 1.955 ms |
| 12.00V | 1.480 ms |
| 14.00V | 1.185 ms |
| 16.00V | 0.975 ms |

#### ID1300x² at 80 PSI

- **Taxa de Fluxo:** 1820 CC/min (aprox. 174.41 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.875 ms |
| 10.00V | 2.015 ms |
| 12.00V | 1.510 ms |
| 14.00V | 1.205 ms |
| 16.00V | 0.990 ms |

#### ID1300x² at 85 PSI

- **Taxa de Fluxo:** 1860 CC/min (aprox. 178.24 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.075 ms |
| 12.00V | 1.540 ms |
| 14.00V | 1.220 ms |
| 16.00V | 1.005 ms |

#### ID1300x² at 90 PSI

- **Taxa de Fluxo:** 1860 CC/min (aprox. 178.24 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.135 ms |
| 12.00V | 1.580 ms |
| 14.00V | 1.220 ms |
| 16.00V | 1.005 ms |

#### ID1300x² at 95 PSI

- **Taxa de Fluxo:** 1925 CC/min (aprox. 184.47 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.195 ms |
| 12.00V | 1.625 ms |
| 14.00V | 1.280 ms |
| 16.00V | 1.050 ms |

#### ID1300x² at 100 PSI

- **Taxa de Fluxo:** 1950 CC/min (aprox. 186.87 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.250 ms |
| 12.00V | 1.675 ms |
| 14.00V | 1.320 ms |
| 16.00V | 1.080 ms |

### ID1300-XDS

#### ID1300-XDS at 40 PSI

- **Taxa de Fluxo:** 1275 CC/min (aprox. 122.18 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.175 ms |
| 10.00V | 1.575 ms |
| 12.00V | 1.235 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.855 ms |

#### ID1300-XDS at 43.5 PSI

- **Taxa de Fluxo:** 1335 CC/min (aprox. 127.93 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.230 ms |
| 10.00V | 1.610 ms |
| 12.00V | 1.255 ms |
| 14.00V | 1.035 ms |
| 16.00V | 0.865 ms |

#### ID1300-XDS at 45 PSI

- **Taxa de Fluxo:** 1360 CC/min (aprox. 130.33 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.255 ms |
| 10.00V | 1.620 ms |
| 12.00V | 1.265 ms |
| 14.00V | 1.040 ms |
| 16.00V | 0.870 ms |

#### ID1300-XDS at 50 PSI

- **Taxa de Fluxo:** 1440 CC/min (aprox. 138.00 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.350 ms |
| 10.00V | 1.665 ms |
| 12.00V | 1.290 ms |
| 14.00V | 1.055 ms |
| 16.00V | 0.880 ms |

#### ID1300-XDS at 55 PSI

- **Taxa de Fluxo:** 1520 CC/min (aprox. 145.66 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.445 ms |
| 10.00V | 1.715 ms |
| 12.00V | 1.320 ms |
| 14.00V | 1.070 ms |
| 16.00V | 0.895 ms |

#### ID1300-XDS at 60 PSI

- **Taxa de Fluxo:** 1590 CC/min (aprox. 152.37 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.535 ms |
| 10.00V | 1.765 ms |
| 12.00V | 1.355 ms |
| 14.00V | 1.095 ms |
| 16.00V | 0.915 ms |

#### ID1300-XDS at 65 PSI

- **Taxa de Fluxo:** 1655 CC/min (aprox. 158.60 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.620 ms |
| 10.00V | 1.830 ms |
| 12.00V | 1.395 ms |
| 14.00V | 1.125 ms |
| 16.00V | 0.935 ms |

#### ID1300-XDS at 70 PSI

- **Taxa de Fluxo:** 1715 CC/min (aprox. 164.35 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.705 ms |
| 10.00V | 1.895 ms |
| 12.00V | 1.445 ms |
| 14.00V | 1.160 ms |
| 16.00V | 0.960 ms |

#### ID1300-XDS at 75 PSI

- **Taxa de Fluxo:** 1770 CC/min (aprox. 169.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.790 ms |
| 10.00V | 1.955 ms |
| 12.00V | 1.480 ms |
| 14.00V | 1.185 ms |
| 16.00V | 0.975 ms |

#### ID1300-XDS at 80 PSI

- **Taxa de Fluxo:** 1820 CC/min (aprox. 174.41 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.875 ms |
| 10.00V | 2.015 ms |
| 12.00V | 1.510 ms |
| 14.00V | 1.205 ms |
| 16.00V | 0.990 ms |

#### ID1300-XDS at 85 PSI

- **Taxa de Fluxo:** 1860 CC/min (aprox. 178.24 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.075 ms |
| 12.00V | 1.540 ms |
| 14.00V | 1.220 ms |
| 16.00V | 1.005 ms |

#### ID1300-XDS at 90 PSI

- **Taxa de Fluxo:** 1895 CC/min (aprox. 181.60 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.135 ms |
| 12.00V | 1.580 ms |
| 14.00V | 1.250 ms |
| 16.00V | 1.025 ms |

#### ID1300-XDS at 95 PSI

- **Taxa de Fluxo:** 1925 CC/min (aprox. 184.47 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.195 ms |
| 12.00V | 1.625 ms |
| 14.00V | 1.280 ms |
| 16.00V | 1.050 ms |

#### ID1300-XDS at 100 PSI

- **Taxa de Fluxo:** 1950 CC/min (aprox. 186.87 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.250 ms |
| 12.00V | 1.675 ms |
| 14.00V | 1.320 ms |
| 16.00V | 1.080 ms |

### ID1700x

#### ID1700x at 43.5 PSI

- **Taxa de Fluxo:** 1725 CC/min (aprox. 165.31 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.745 ms |
| 10.00V | 1.740 ms |
| 12.00V | 1.260 ms |
| 14.00V | 0.975 ms |
| 16.00V | 0.800 ms |

#### ID1700x at 45 PSI

- **Taxa de Fluxo:** 1760 CC/min (aprox. 168.66 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.805 ms |
| 10.00V | 1.760 ms |
| 12.00V | 1.275 ms |
| 14.00V | 0.980 ms |
| 16.00V | 0.805 ms |

#### ID1700x at 50 PSI

- **Taxa de Fluxo:** 1855 CC/min (aprox. 177.76 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.050 ms |
| 10.00V | 1.835 ms |
| 12.00V | 1.320 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.830 ms |

#### ID1700x at 55 PSI

- **Taxa de Fluxo:** 1950 CC/min (aprox. 186.87 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.330 ms |
| 10.00V | 1.915 ms |
| 12.00V | 1.375 ms |
| 14.00V | 1.065 ms |
| 16.00V | 0.855 ms |

#### ID1700x at 60 PSI

- **Taxa de Fluxo:** 2040 CC/min (aprox. 195.49 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.610 ms |
| 10.00V | 2.000 ms |
| 12.00V | 1.430 ms |
| 14.00V | 1.110 ms |
| 16.00V | 0.885 ms |

#### ID1700x at 65 PSI

- **Taxa de Fluxo:** 2125 CC/min (aprox. 203.64 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.895 ms |
| 10.00V | 2.090 ms |
| 12.00V | 1.490 ms |
| 14.00V | 1.150 ms |
| 16.00V | 0.920 ms |

#### ID1700x at 70 PSI

- **Taxa de Fluxo:** 2205 CC/min (aprox. 211.31 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.180 ms |
| 12.00V | 1.545 ms |
| 14.00V | 1.195 ms |
| 16.00V | 0.960 ms |

#### ID1700x at 75 PSI

- **Taxa de Fluxo:** 2285 CC/min (aprox. 218.97 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.270 ms |
| 12.00V | 1.605 ms |
| 14.00V | 1.235 ms |
| 16.00V | 0.995 ms |

#### ID1700x at 80 PSI

- **Taxa de Fluxo:** 2360 CC/min (aprox. 226.16 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.365 ms |
| 12.00V | 1.670 ms |
| 14.00V | 1.275 ms |
| 16.00V | 1.025 ms |

#### ID1700x at 85 PSI

- **Taxa de Fluxo:** 2435 CC/min (aprox. 233.35 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.455 ms |
| 12.00V | 1.730 ms |
| 14.00V | 1.315 ms |
| 16.00V | 1.055 ms |

#### ID1700x at 90 PSI

- **Taxa de Fluxo:** 2505 CC/min (aprox. 240.05 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.555 ms |
| 12.00V | 1.785 ms |
| 14.00V | 1.355 ms |
| 16.00V | 1.085 ms |

#### ID1700x at 95 PSI

- **Taxa de Fluxo:** 2575 CC/min (aprox. 246.76 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 12.00V | 1.845 ms |
| 14.00V | 1.400 ms |
| 16.00V | 1.120 ms |

#### ID1700x at 100 PSI

- **Taxa de Fluxo:** 2640 CC/min (aprox. 252.99 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 12.00V | 1.900 ms |
| 14.00V | 1.440 ms |
| 16.00V | 1.155 ms |

### ID1750-XDS

#### ID1750-XDS at 43.5 PSI

- **Taxa de Fluxo:** 1728 CC/min (aprox. 165.59 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.635 ms |
| 10.00V | 1.641 ms |
| 12.00V | 1.169 ms |
| 14.00V | 0.882 ms |
| 16.00V | 0.689 ms |

#### ID1750-XDS at 45 PSI

- **Taxa de Fluxo:** 1759 CC/min (aprox. 168.56 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.679 ms |
| 10.00V | 1.660 ms |
| 12.00V | 1.180 ms |
| 14.00V | 0.889 ms |
| 16.00V | 0.695 ms |

#### ID1750-XDS at 50 PSI

- **Taxa de Fluxo:** 1858 CC/min (aprox. 178.05 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.834 ms |
| 10.00V | 1.726 ms |
| 12.00V | 1.222 ms |
| 14.00V | 0.918 ms |
| 16.00V | 0.714 ms |

#### ID1750-XDS at 55 PSI

- **Taxa de Fluxo:** 1953 CC/min (aprox. 187.16 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.004 ms |
| 10.00V | 1.798 ms |
| 12.00V | 1.268 ms |
| 14.00V | 0.951 ms |
| 16.00V | 0.737 ms |

#### ID1750-XDS at 60 PSI

- **Taxa de Fluxo:** 2044 CC/min (aprox. 195.88 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.194 ms |
| 10.00V | 1.873 ms |
| 12.00V | 1.316 ms |
| 14.00V | 0.987 ms |
| 16.00V | 0.766 ms |

#### ID1750-XDS at 65 PSI

- **Taxa de Fluxo:** 2131 CC/min (aprox. 204.21 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.404 ms |
| 10.00V | 1.952 ms |
| 12.00V | 1.367 ms |
| 14.00V | 1.027 ms |
| 16.00V | 0.804 ms |

#### ID1750-XDS at 70 PSI

- **Taxa de Fluxo:** 2216 CC/min (aprox. 212.36 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.036 ms |
| 12.00V | 1.420 ms |
| 14.00V | 1.069 ms |
| 16.00V | 0.844 ms |

#### ID1750-XDS at 75 PSI

- **Taxa de Fluxo:** 2296 CC/min (aprox. 220.03 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.122 ms |
| 12.00V | 1.472 ms |
| 14.00V | 1.109 ms |
| 16.00V | 0.878 ms |

#### ID1750-XDS at 80 PSI

- **Taxa de Fluxo:** 2373 CC/min (aprox. 227.40 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.211 ms |
| 12.00V | 1.524 ms |
| 14.00V | 1.148 ms |
| 16.00V | 0.908 ms |

#### ID1750-XDS at 85 PSI

- **Taxa de Fluxo:** 2446 CC/min (aprox. 234.40 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.304 ms |
| 12.00V | 1.577 ms |
| 14.00V | 1.187 ms |
| 16.00V | 0.936 ms |

#### ID1750-XDS at 90 PSI

- **Taxa de Fluxo:** 2515 CC/min (aprox. 241.01 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.400 ms |
| 12.00V | 1.634 ms |
| 14.00V | 1.228 ms |
| 16.00V | 0.968 ms |

#### ID1750-XDS at 95 PSI

- **Taxa de Fluxo:** 2582 CC/min (aprox. 247.43 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.499 ms |
| 12.00V | 1.694 ms |
| 14.00V | 1.270 ms |
| 16.00V | 1.000 ms |

#### ID1750-XDS at 100 PSI

- **Taxa de Fluxo:** 2645 CC/min (aprox. 253.47 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 2.601 ms |
| 12.00V | 1.757 ms |
| 14.00V | 1.314 ms |
| 16.00V | 1.034 ms |

### ID2000

#### ID2000 at 43.5 PSI

- **Taxa de Fluxo:** 2225 CC/min (aprox. 213.22 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.455 ms |
| 10.00V | 0.950 ms |
| 12.00V | 0.680 ms |
| 14.00V | 0.495 ms |
| 16.00V | 0.375 ms |

#### ID2000 at 45 PSI

- **Taxa de Fluxo:** 2255 CC/min (aprox. 216.10 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.475 ms |
| 10.00V | 0.965 ms |
| 12.00V | 0.690 ms |
| 14.00V | 0.500 ms |
| 16.00V | 0.380 ms |

#### ID2000 at 50 PSI

- **Taxa de Fluxo:** 2365 CC/min (aprox. 226.64 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.540 ms |
| 10.00V | 1.020 ms |
| 12.00V | 0.720 ms |
| 14.00V | 0.525 ms |
| 16.00V | 0.405 ms |

#### ID2000 at 55 PSI

- **Taxa de Fluxo:** 2470 CC/min (aprox. 236.70 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.605 ms |
| 10.00V | 1.065 ms |
| 12.00V | 0.750 ms |
| 14.00V | 0.550 ms |
| 16.00V | 0.430 ms |

#### ID2000 at 60 PSI

- **Taxa de Fluxo:** 2575 CC/min (aprox. 246.76 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.680 ms |
| 10.00V | 1.105 ms |
| 12.00V | 0.780 ms |
| 14.00V | 0.580 ms |
| 16.00V | 0.455 ms |

#### ID2000 at 65 PSI

- **Taxa de Fluxo:** 2680 CC/min (aprox. 256.82 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.750 ms |
| 10.00V | 1.140 ms |
| 12.00V | 0.810 ms |
| 14.00V | 0.605 ms |
| 16.00V | 0.475 ms |

#### ID2000 at 70 PSI

- **Taxa de Fluxo:** 2780 CC/min (aprox. 266.41 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.825 ms |
| 10.00V | 1.175 ms |
| 12.00V | 0.840 ms |
| 14.00V | 0.635 ms |
| 16.00V | 0.495 ms |

#### ID2000 at 75 PSI

- **Taxa de Fluxo:** 2875 CC/min (aprox. 275.51 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.895 ms |
| 10.00V | 1.220 ms |
| 12.00V | 0.880 ms |
| 14.00V | 0.665 ms |
| 16.00V | 0.505 ms |

#### ID2000 at 80 PSI

- **Taxa de Fluxo:** 2970 CC/min (aprox. 284.62 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.965 ms |
| 10.00V | 1.270 ms |
| 12.00V | 0.925 ms |
| 14.00V | 0.690 ms |
| 16.00V | 0.515 ms |

#### ID2000 at 85 PSI

- **Taxa de Fluxo:** 3055 CC/min (aprox. 292.76 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.050 ms |
| 10.00V | 1.320 ms |
| 12.00V | 0.965 ms |
| 14.00V | 0.715 ms |
| 16.00V | 0.520 ms |

#### ID2000 at 90 PSI

- **Taxa de Fluxo:** 3140 CC/min (aprox. 300.91 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.160 ms |
| 10.00V | 1.360 ms |
| 12.00V | 0.995 ms |
| 14.00V | 0.750 ms |
| 16.00V | 0.540 ms |

#### ID2000 at 95 PSI

- **Taxa de Fluxo:** 3225 CC/min (aprox. 309.05 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.290 ms |
| 10.00V | 1.395 ms |
| 12.00V | 1.015 ms |
| 14.00V | 0.780 ms |
| 16.00V | 0.565 ms |

#### ID2000 at 100 PSI

- **Taxa de Fluxo:** 3300 CC/min (aprox. 316.24 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.410 ms |
| 10.00V | 1.430 ms |
| 12.00V | 1.035 ms |
| 14.00V | 0.810 ms |
| 16.00V | 0.590 ms |

#### ID2000 at 105 PSI

- **Taxa de Fluxo:** 3375 CC/min (aprox. 323.43 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.515 ms |
| 10.00V | 1.485 ms |
| 12.00V | 1.060 ms |
| 14.00V | 0.830 ms |
| 16.00V | 0.605 ms |

#### ID2000 at 110 PSI

- **Taxa de Fluxo:** 3445 CC/min (aprox. 330.13 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.620 ms |
| 10.00V | 1.555 ms |
| 12.00V | 1.095 ms |
| 14.00V | 0.840 ms |
| 16.00V | 0.615 ms |

#### ID2000 at 115 PSI

- **Taxa de Fluxo:** 3515 CC/min (aprox. 336.84 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.750 ms |
| 10.00V | 1.620 ms |
| 12.00V | 1.135 ms |
| 14.00V | 0.855 ms |
| 16.00V | 0.630 ms |

#### ID2000 at 120 PSI

- **Taxa de Fluxo:** 3580 CC/min (aprox. 343.07 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.935 ms |
| 10.00V | 1.675 ms |
| 12.00V | 1.175 ms |
| 14.00V | 0.875 ms |
| 16.00V | 0.665 ms |

#### ID2000 at 125 PSI

- **Taxa de Fluxo:** 3645 CC/min (aprox. 349.30 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.175 ms |
| 10.00V | 1.720 ms |
| 12.00V | 1.220 ms |
| 14.00V | 0.900 ms |
| 16.00V | 0.715 ms |

#### ID2000 at 130 PSI

- **Taxa de Fluxo:** 3710 CC/min (aprox. 355.53 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 3.435 ms |
| 10.00V | 1.755 ms |
| 12.00V | 1.265 ms |
| 14.00V | 0.925 ms |
| 16.00V | 0.755 ms |

### ID2600-XDS

#### ID2600-XDS at 43.5 PSI

- **Taxa de Fluxo:** 2600 CC/min (aprox. 249.16 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.340 ms |
| 10.00V | 0.880 ms |
| 12.00V | 0.605 ms |
| 14.00V | 0.440 ms |
| 16.00V | 0.315 ms |
| 18.00V | 0.275 ms |

#### ID2600-XDS at 45 PSI

- **Taxa de Fluxo:** 2645 CC/min (aprox. 253.47 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.365 ms |
| 10.00V | 0.895 ms |
| 12.00V | 0.620 ms |
| 14.00V | 0.450 ms |
| 16.00V | 0.325 ms |
| 18.00V | 0.285 ms |

#### ID2600-XDS at 50 PSI

- **Taxa de Fluxo:** 2780 CC/min (aprox. 266.41 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.450 ms |
| 10.00V | 0.955 ms |
| 12.00V | 0.675 ms |
| 14.00V | 0.485 ms |
| 16.00V | 0.350 ms |
| 18.00V | 0.305 ms |

#### ID2600-XDS at 55 PSI

- **Taxa de Fluxo:** 2900 CC/min (aprox. 277.91 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.540 ms |
| 10.00V | 1.010 ms |
| 12.00V | 0.730 ms |
| 14.00V | 0.520 ms |
| 16.00V | 0.370 ms |
| 18.00V | 0.325 ms |

#### ID2600-XDS at 60 PSI

- **Taxa de Fluxo:** 3025 CC/min (aprox. 289.89 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.635 ms |
| 10.00V | 1.060 ms |
| 12.00V | 0.770 ms |
| 14.00V | 0.555 ms |
| 16.00V | 0.395 ms |
| 18.00V | 0.350 ms |

#### ID2600-XDS at 65 PSI

- **Taxa de Fluxo:** 3140 CC/min (aprox. 300.91 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.730 ms |
| 10.00V | 1.115 ms |
| 12.00V | 0.800 ms |
| 14.00V | 0.590 ms |
| 16.00V | 0.420 ms |
| 18.00V | 0.380 ms |

#### ID2600-XDS at 70 PSI

- **Taxa de Fluxo:** 3255 CC/min (aprox. 311.93 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.825 ms |
| 10.00V | 1.165 ms |
| 12.00V | 0.830 ms |
| 14.00V | 0.625 ms |
| 16.00V | 0.450 ms |
| 18.00V | 0.415 ms |

#### ID2600-XDS at 75 PSI

- **Taxa de Fluxo:** 3370 CC/min (aprox. 322.95 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.935 ms |
| 10.00V | 1.225 ms |
| 12.00V | 0.870 ms |
| 14.00V | 0.660 ms |
| 16.00V | 0.485 ms |
| 18.00V | 0.445 ms |

#### ID2600-XDS at 80 PSI

- **Taxa de Fluxo:** 3485 CC/min (aprox. 333.97 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.050 ms |
| 10.00V | 1.285 ms |
| 12.00V | 0.915 ms |
| 14.00V | 0.690 ms |
| 16.00V | 0.525 ms |
| 18.00V | 0.475 ms |

#### ID2600-XDS at 85 PSI

- **Taxa de Fluxo:** 3595 CC/min (aprox. 344.51 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.175 ms |
| 10.00V | 1.350 ms |
| 12.00V | 0.955 ms |
| 14.00V | 0.745 ms |
| 16.00V | 0.585 ms |
| 18.00V | 0.520 ms |

#### ID2600-XDS at 90 PSI

- **Taxa de Fluxo:** 3680 CC/min (aprox. 352.65 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.320 ms |
| 10.00V | 1.410 ms |
| 12.00V | 0.995 ms |
| 14.00V | 0.745 ms |
| 16.00V | 0.585 ms |
| 18.00V | 0.520 ms |

#### ID2600-XDS at 95 PSI

- **Taxa de Fluxo:** 3755 CC/min (aprox. 359.84 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.485 ms |
| 10.00V | 1.465 ms |
| 12.00V | 1.030 ms |
| 14.00V | 0.765 ms |
| 16.00V | 0.605 ms |
| 18.00V | 0.540 ms |

#### ID2600-XDS at 100 PSI

- **Taxa de Fluxo:** 3810 CC/min (aprox. 365.11 LB/hora)

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.670 ms |
| 10.00V | 1.520 ms |
| 12.00V | 1.060 ms |
| 14.00V | 0.780 ms |
| 16.00V | 0.615 ms |
| 18.00V | 0.550 ms |

---

## MSD

### Peak and Hold

#### MSD 525CC

- **Taxa de Fluxo:** 525 CC/min (aprox. 50.31 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.100 ms |
| 10.00V | 1.190 ms |
| 11.00V | 0.940 ms |
| 12.00V | 0.750 ms |
| 13.00V | 0.610 ms |
| 14.00V | 0.490 ms |
| 16.00V | 0.340 ms |

#### MSD 750CC

- **Taxa de Fluxo:** 750 CC/min (aprox. 71.87 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.190 ms |
| 10.00V | 1.400 ms |
| 11.00V | 1.170 ms |
| 12.00V | 0.970 ms |
| 13.00V | 0.810 ms |
| 14.00V | 0.690 ms |
| 16.00V | 0.490 ms |

---

## Mitsubishi

### Peak and Hold

#### DSM Black (90-94 Turbo)

- **Taxa de Fluxo:** 450 CC/min (aprox. 43.12 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.540 ms |
| 10.00V | 1.110 ms |
| 11.00V | 0.950 ms |
| 12.00V | 0.820 ms |
| 13.00V | 0.670 ms |
| 14.00V | 0.530 ms |
| 16.00V | 0.300 ms |

#### DSM Blue (95-99 Turbo)

- **Taxa de Fluxo:** 450 CC/min (aprox. 43.12 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.480 ms |
| 10.00V | 1.000 ms |
| 11.00V | 0.810 ms |
| 12.00V | 0.670 ms |
| 13.00V | 0.550 ms |
| 14.00V | 0.450 ms |
| 16.00V | 0.190 ms |

#### 3000GT

- **Taxa de Fluxo:** 370 CC/min (aprox. 35.46 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.880 ms |
| 10.00V | 0.780 ms |
| 12.13V | 0.700 ms |
| 14.16V | 0.630 ms |
| 16.08V | 0.550 ms |
| 24.56V | 0.480 ms |

#### EVO III

- **Taxa de Fluxo:** 510 CC/min (aprox. 48.87 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.080 ms |
| 10.00V | 1.540 ms |
| 11.00V | 1.350 ms |
| 12.00V | 1.190 ms |
| 13.00V | 1.020 ms |
| 14.00V | 1.020 ms |
| 16.00V | 0.900 ms |

#### EVO VIII

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 0.910 ms |
| 10.00V | 0.800 ms |
| 12.13V | 0.720 ms |
| 14.16V | 0.640 ms |
| 16.08V | 0.580 ms |
| 24.56V | 0.520 ms |

### Lancer (2.4L)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 15 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.09V | 1.280 ms |
| 10.00V | 1.050 ms |
| 12.13V | 0.830 ms |
| 14.16V | 0.640 ms |
| 16.08V | 0.550 ms |
| 24.56V | 0.470 ms |

---

## Nissan

### Nismo

#### Nissan 740CC

- **Taxa de Fluxo:** 740 CC/min (aprox. 70.91 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.150 ms |
| 11.00V | 0.940 ms |
| 12.00V | 0.790 ms |
| 13.00V | 0.660 ms |
| 14.00V | 0.550 ms |
| 15.00V | 0.440 ms |

### Peak and Hold

#### Skyline GT-R

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.700 ms |
| 11.00V | 0.610 ms |
| 12.00V | 0.540 ms |
| 13.00V | 0.480 ms |
| 14.00V | 0.400 ms |

#### 180sx/Skyline (86-88)

- **Taxa de Fluxo:** 270 CC/min (aprox. 25.87 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.110 ms |
| 11.00V | 0.920 ms |
| 12.00V | 0.750 ms |
| 13.00V | 0.600 ms |
| 14.00V | 0.490 ms |

#### Pulsar GTi-R - SR20DET

- **Taxa de Fluxo:** 444 CC/min (aprox. 42.55 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.140 ms |
| 11.00V | 0.960 ms |
| 12.00V | 0.830 ms |
| 13.00V | 0.710 ms |
| 14.00V | 0.600 ms |

### Sentra/200sx/NX/G20 (2.0L ONLY)

- **Taxa de Fluxo:** 259 CC/min (aprox. 24.82 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.900 ms |
| 11.00V | 0.750 ms |
| 12.00V | 0.640 ms |
| 13.00V | 0.560 ms |
| 14.00V | 0.470 ms |
| 15.00V | 0.420 ms |

### 300zx(95-96) - SR20DET

- **Taxa de Fluxo:** 370 CC/min (aprox. 35.46 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.170 ms |
| 11.00V | 0.980 ms |
| 12.00V | 0.860 ms |
| 13.00V | 0.750 ms |
| 14.00V | 0.640 ms |

### 240SX (89-90)

- **Taxa de Fluxo:** 230 CC/min (aprox. 22.04 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.940 ms |
| 11.00V | 0.750 ms |
| 12.00V | 0.620 ms |
| 13.00V | 0.550 ms |
| 14.00V | 0.470 ms |

### 240sx (91-98)/Altima (93-01)

- **Taxa de Fluxo:** 250 CC/min (aprox. 23.96 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.000 ms |
| 11.00V | 0.830 ms |
| 12.00V | 0.690 ms |
| 13.00V | 0.570 ms |
| 14.00V | 0.470 ms |
| 15.00V | 0.400 ms |

### Skyline GTS-T

- **Taxa de Fluxo:** 380 CC/min (aprox. 36.42 LB/hora)
- **Impedância:** 11 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.100 ms |
| 11.00V | 0.880 ms |
| 12.00V | 0.730 ms |
| 13.00V | 0.610 ms |
| 14.00V | 0.520 ms |

---

## Precision Turbo (Rochester)

### Peak and Hold

#### Precision Turbo (Rochester) 680CC

- **Taxa de Fluxo:** 680 CC/min (aprox. 65.16 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.220 ms |
| 10.00V | 1.560 ms |
| 11.00V | 1.360 ms |
| 12.00V | 1.220 ms |
| 13.00V | 1.130 ms |
| 14.00V | 1.050 ms |
| 16.00V | 0.890 ms |

#### Precision Turbo (Rochester) 1000CC

- **Taxa de Fluxo:** 1000 CC/min (aprox. 95.83 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.190 ms |
| 10.00V | 1.380 ms |
| 11.00V | 1.150 ms |
| 12.00V | 0.960 ms |
| 13.00V | 0.810 ms |
| 14.00V | 0.700 ms |
| 16.00V | 0.530 ms |

#### Precision Turbo (Rochester) 756CC

- **Taxa de Fluxo:** 756 CC/min (aprox. 72.45 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.220 ms |
| 11.00V | 1.030 ms |
| 12.00V | 0.870 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.630 ms |

#### Precision Turbo (Rochester) 1008CC

- **Taxa de Fluxo:** 1008 CC/min (aprox. 96.60 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.380 ms |
| 11.00V | 1.150 ms |
| 12.00V | 0.960 ms |
| 13.00V | 0.810 ms |
| 14.00V | 0.700 ms |

### Precision Turbo (Rochester) 525CC

- **Taxa de Fluxo:** 525 CC/min (aprox. 50.31 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.470 ms |
| 10.00V | 1.330 ms |
| 11.00V | 1.050 ms |
| 12.00V | 0.840 ms |
| 13.00V | 0.660 ms |
| 14.00V | 0.540 ms |
| 16.00V | 0.380 ms |

---

## RC Engineering

### Peak and Hold

#### da phearable.net

- **Taxa de Fluxo:** 750 CC/min (aprox. 71.87 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.570 ms |
| 11.00V | 0.480 ms |
| 12.00V | 0.380 ms |
| 13.00V | 0.310 ms |
| 14.00V | 0.240 ms |

#### RC Engineering 750CC

- **Taxa de Fluxo:** 750 CC/min (aprox. 71.87 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 0.950 ms |
| 10.00V | 0.650 ms |
| 11.00V | 0.560 ms |
| 12.00V | 0.490 ms |
| 13.00V | 0.420 ms |
| 14.00V | 0.350 ms |
| 16.00V | 0.240 ms |

#### da phearable.net

- **Taxa de Fluxo:** 1000 CC/min (aprox. 95.83 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.650 ms |
| 11.00V | 0.560 ms |
| 12.00V | 0.490 ms |
| 13.00V | 0.420 ms |
| 14.00V | 0.350 ms |

#### RC Engineering 1000CC

- **Taxa de Fluxo:** 1000 CC/min (aprox. 95.83 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.460 ms |
| 10.00V | 1.700 ms |
| 11.00V | 1.480 ms |
| 12.00V | 1.310 ms |
| 13.00V | 1.160 ms |
| 14.00V | 1.060 ms |
| 16.00V | 0.830 ms |

#### RC Engineering 1200CC

- **Taxa de Fluxo:** 1200 CC/min (aprox. 115.00 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.550 ms |
| 10.00V | 2.550 ms |
| 11.00V | 2.280 ms |
| 12.00V | 2.000 ms |
| 13.00V | 1.790 ms |
| 14.00V | 1.620 ms |
| 16.00V | 1.320 ms |

#### RC Engineering 1200CC

- **Taxa de Fluxo:** 1200 CC/min (aprox. 115.00 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 0.920 ms |
| 10.00V | 0.570 ms |
| 11.00V | 0.480 ms |
| 12.00V | 0.380 ms |
| 13.00V | 0.310 ms |
| 14.00V | 0.240 ms |
| 16.00V | 0.130 ms |

#### RC Engineering 900CC

- **Taxa de Fluxo:** 900 CC/min (aprox. 86.25 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.650 ms |
| 10.00V | 1.070 ms |
| 11.00V | 0.880 ms |
| 12.00V | 0.780 ms |
| 13.00V | 0.670 ms |
| 14.00V | 0.550 ms |
| 16.00V | 0.350 ms |

#### RC Engineering 1600CC

- **Taxa de Fluxo:** 1600 CC/min (aprox. 153.33 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.550 ms |
| 10.00V | 1.800 ms |
| 11.00V | 1.460 ms |
| 12.00V | 1.230 ms |
| 13.00V | 1.050 ms |
| 14.00V | 0.920 ms |
| 16.00V | 0.700 ms |

#### RC Engineering 720CC

- **Taxa de Fluxo:** 720 CC/min (aprox. 69.00 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.460 ms |
| 10.00V | 1.700 ms |
| 11.00V | 1.480 ms |
| 12.00V | 1.310 ms |
| 13.00V | 1.160 ms |
| 14.00V | 1.060 ms |
| 16.00V | 0.830 ms |

#### RC Engineering 750CC

- **Taxa de Fluxo:** 750 CC/min (aprox. 71.87 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.600 ms |
| 10.00V | 0.880 ms |
| 11.00V | 0.660 ms |
| 12.00V | 0.480 ms |
| 13.00V | 0.320 ms |
| 14.00V | 0.180 ms |
| 16.00V | 0.010 ms |

#### RC Engineering 550CC

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.460 ms |
| 10.00V | 0.920 ms |
| 11.00V | 0.810 ms |
| 12.00V | 0.680 ms |
| 13.00V | 0.590 ms |
| 14.00V | 0.510 ms |
| 16.00V | 0.300 ms |

### RC Engineering 240CC

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.310 ms |
| 11.00V | 1.100 ms |
| 12.00V | 0.970 ms |
| 13.00V | 0.770 ms |
| 14.00V | 0.620 ms |

### RC Engineering 270CC

- **Taxa de Fluxo:** 270 CC/min (aprox. 25.87 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.470 ms |
| 10.00V | 0.890 ms |
| 11.00V | 0.760 ms |
| 12.00V | 0.610 ms |
| 13.00V | 0.490 ms |
| 14.00V | 0.320 ms |
| 16.00V | 0.150 ms |

### RC Engineering 310CC

- **Taxa de Fluxo:** 310 CC/min (aprox. 29.71 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.920 ms |
| 10.00V | 1.140 ms |
| 11.00V | 0.890 ms |
| 12.00V | 0.720 ms |
| 13.00V | 0.550 ms |
| 14.00V | 0.430 ms |
| 16.00V | 0.250 ms |

### RC Engineering 370CC

- **Taxa de Fluxo:** 370 CC/min (aprox. 35.46 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.500 ms |
| 10.00V | 0.850 ms |
| 11.00V | 0.640 ms |
| 12.00V | 0.470 ms |
| 13.00V | 0.350 ms |
| 14.00V | 0.210 ms |
| 16.00V | 0.040 ms |

### RC Engineering 440CC

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.830 ms |
| 10.00V | 1.270 ms |
| 11.00V | 1.080 ms |
| 12.00V | 0.910 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.630 ms |
| 16.00V | 0.440 ms |

### RC Engineering 440CC

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.270 ms |
| 11.00V | 1.080 ms |
| 12.00V | 0.910 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.630 ms |

### RC Engineering 440CC

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.310 ms |
| 10.00V | 0.760 ms |
| 11.00V | 0.560 ms |
| 12.00V | 0.420 ms |
| 13.00V | 0.290 ms |
| 14.00V | 0.140 ms |

### RC Engineering 550CC

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.650 ms |
| 10.00V | 1.070 ms |
| 11.00V | 0.880 ms |
| 12.00V | 0.780 ms |
| 13.00V | 0.670 ms |
| 14.00V | 0.550 ms |
| 16.00V | 0.350 ms |

### RC Engineering 650CC

- **Taxa de Fluxo:** 650 CC/min (aprox. 62.29 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.850 ms |
| 10.00V | 1.080 ms |
| 11.00V | 0.860 ms |
| 12.00V | 0.690 ms |
| 13.00V | 0.540 ms |
| 14.00V | 0.410 ms |
| 16.00V | 0.220 ms |

### RC Engineering 750CC

- **Taxa de Fluxo:** 750 CC/min (aprox. 71.87 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 2.180 ms |
| 10.00V | 1.360 ms |
| 11.00V | 1.120 ms |
| 12.00V | 0.920 ms |
| 13.00V | 0.760 ms |
| 14.00V | 0.630 ms |
| 16.00V | 0.400 ms |

---

## Sard

### Peak and Hold

#### Sard 700CC

- **Taxa de Fluxo:** 700 CC/min (aprox. 67.08 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.680 ms |
| 11.00V | 0.570 ms |
| 12.00V | 0.490 ms |
| 13.00V | 0.420 ms |
| 14.00V | 0.350 ms |

#### Sard 700CC

- **Taxa de Fluxo:** 700 CC/min (aprox. 67.08 LB/hora)
- **Impedância:** 2 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.980 ms |
| 11.00V | 0.800 ms |
| 12.00V | 0.670 ms |
| 13.00V | 0.540 ms |
| 14.00V | 0.440 ms |

#### Sard 800CC

- **Taxa de Fluxo:** 800 CC/min (aprox. 76.66 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.580 ms |
| 11.00V | 0.470 ms |
| 12.00V | 0.390 ms |
| 13.00V | 0.320 ms |
| 14.00V | 0.240 ms |

#### Sard 800CC

- **Taxa de Fluxo:** 800 CC/min (aprox. 76.66 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.900 ms |
| 11.00V | 0.750 ms |
| 12.00V | 0.620 ms |
| 13.00V | 0.520 ms |
| 14.00V | 0.420 ms |

---

## Siemens Deka

### Peak and Hold

#### Siemens Deka 756CC

- **Taxa de Fluxo:** 756 CC/min (aprox. 72.45 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.410 ms |
| 11.00V | 1.210 ms |
| 12.00V | 1.030 ms |
| 13.00V | 0.870 ms |
| 14.00V | 0.760 ms |

#### Siemens Deka 872CC

- **Taxa de Fluxo:** 872 CC/min (aprox. 83.56 LB/hora)
- **Impedância:** 3 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.460 ms |
| 11.00V | 1.200 ms |
| 12.00V | 1.000 ms |
| 13.00V | 0.850 ms |
| 14.00V | 0.730 ms |

### Siemens Deka 578CC

- **Taxa de Fluxo:** 578 CC/min (aprox. 55.39 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.310 ms |
| 11.00V | 1.130 ms |
| 12.00V | 0.960 ms |
| 13.00V | 0.830 ms |
| 14.00V | 0.710 ms |

### Siemens Deka 630CC

- **Taxa de Fluxo:** 630 CC/min (aprox. 60.37 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.830 ms |
| 11.00V | 0.640 ms |
| 12.00V | 0.500 ms |
| 13.00V | 0.380 ms |
| 14.00V | 0.280 ms |

---

## Subaru

### Impreza STI (top feed)

- **Taxa de Fluxo:** 550 CC/min (aprox. 52.71 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.230 ms |
| 11.00V | 1.040 ms |
| 12.00V | 0.870 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.620 ms |

### Impreza WRX

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 13 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.250 ms |
| 11.00V | 1.010 ms |
| 12.00V | 0.870 ms |
| 13.00V | 0.740 ms |
| 14.00V | 0.620 ms |

---

## Toyota

### (00+ 1.5L) xB/xA/Prius/Echo

- **Taxa de Fluxo:** 200 CC/min (aprox. 19.17 LB/hora)
- **Impedância:** 14 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.070 ms |
| 11.00V | 0.870 ms |
| 12.00V | 0.680 ms |
| 13.00V | 0.550 ms |
| 14.00V | 0.440 ms |

### (04+ 2.4L) tC/Solaris/Camry/RAV4

- **Taxa de Fluxo:** 330 CC/min (aprox. 31.62 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.180 ms |
| 11.00V | 0.970 ms |
| 12.00V | 0.790 ms |
| 13.00V | 0.640 ms |
| 14.00V | 0.510 ms |

---

## Ultimate Racing

### Ultimate Racing 440CC

- **Taxa de Fluxo:** 440 CC/min (aprox. 42.17 LB/hora)
- **Impedância:** 16 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 8.00V | 1.300 ms |
| 10.00V | 0.740 ms |
| 11.00V | 0.570 ms |
| 12.00V | 0.420 ms |
| 13.00V | 0.300 ms |
| 14.00V | 0.190 ms |
| 16.00V | 0.040 ms |

---

## Vennom

### Vennom 880CC

- **Taxa de Fluxo:** 880 CC/min (aprox. 84.33 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.270 ms |
| 11.00V | 1.000 ms |
| 12.00V | 0.770 ms |
| 13.00V | 0.640 ms |
| 14.00V | 0.510 ms |

---

## Volkswagen

### Passat (98-99)/Audi A4 (97-99)

- **Taxa de Fluxo:** 220 CC/min (aprox. 21.08 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 0.820 ms |
| 11.00V | 0.620 ms |
| 12.00V | 0.460 ms |
| 13.00V | 0.340 ms |
| 14.00V | 0.240 ms |

### Passat (2000)

- **Taxa de Fluxo:** 240 CC/min (aprox. 23.00 LB/hora)
- **Impedância:** 12 Ω

| Tensão | Latência (ms) |
| :---: | :---: |
| 10.00V | 1.050 ms |
| 11.00V | 0.840 ms |
| 12.00V | 0.690 ms |
| 13.00V | 0.600 ms |
| 14.00V | 0.520 ms |

---
