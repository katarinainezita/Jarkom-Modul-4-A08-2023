# Jarkom-Modul-4-A08-2023
Praktikum Modul 4 Jaringan Komputer 2023

## Anggota Kelompok A08

| No.  | Nama Anggota       | NRP          |
|------|--------------------|--------------|
| 1    |Mohammad Zhafran Dzaky           | 5025211142   |
| 2    | Katarina Inezita Prambudi         | 5025211148   |


## Pembagian
Untuk praktikum kali ini, kelompok kami memutuskan untuk memilih kombinasi metode VLSM pada GNS3 dan metode CIDR pada Cisco Packet Tracer (CPT).

## Subnetting

![image](https://github.com/katarinainezita/school-management-system/assets/109232320/8dbda3e4-a145-42df-b48c-83b22c159c21)

| Nama Subnet  | Rute                                  | Jumlah IP    | Netmask |
|------------- |------------                           |--------------| --------| 
| A1           | Fern-Switch4-AppetitRegion-LaubHills  | 1023         | /21 |
| A2           | Flamme-Fern                           | 2            | /30 |
| A3           | Flamme-Switch5-RohrRoad               | 1001            | /22 |
| A4           | Flamme-Himmel                         | 2            | /30 |
| A5           | Himmel-Switch6-SchwerMountains        | 6            | /29 |
| A6           | Frieren-Flamme         | 2   | /30 |
| A7           | Frieren-Switch3-Lakekorridor         | 25   | /25 |
| A8           | Aura-Frieren         | 2   | /30 |
| A9           | Aura-Denken         | 2   | /30 |
| A10           | Denken-Switch2-RoyalCapital-Switch2-WilleRegion         | 127   | /24 |
| A11           | Aura-Eisen         | 2   | /30 |
| A12           | Eisen-Switch1-Richter-Switch1-Revolte         | 3   | /29 |
| A13           | Eisen-Switch0-Stark         | 2   | /30 |
| A14           | Eisen-Lugner         | 2   | /30 |
| A15           | Lugner-Switch10-TurkRegion         | 1001   | /22 |
| A16           | Lugner-Switch9-GrobeForeest         | 251   | /24 |
| A17           | Eisen-Linie         | 2   | /30 |
| A18           | Linie-Switch11-GranzChannel         | 255   | /23 |
| A19           | Linie-Lawine         | 2   | /30 |
| A20           | Lawine-Switch7-BradtRegion         | 31   | /26 |
| A21           | Heiter-Switch8-Sein-Switch8-RiegelCanyon         | 512   | /22 |
| Total           |         |  4255  | /19 |


## VLSM


### Tree VLSM
![image](https://github.com/katarinainezita/school-management-system/assets/109232320/11ea4a69-c7e7-45c7-93b7-9da674fb8462)

### Pembagian IP VLSM

| Subnet       | Network ID | Netmask   | Broadcast |
|------------- |------------|--------------| --------| 
| A1           | 10.3.24.0 |	255.255.248.0	| 10.3.31.255 |
| A2           | 10.3.0.0	| 255.255.255.252	| 10.3.0.3 |
| A3           | 10.3.8.0	| 255.255.255.252	| 10.3.11.255 |
| A4           | 10.3.0.4	| 255.255.255.252	| 10.3.0.7 |
| A5           | 10.3.0.56 |	255.255.255.248	| 10.3.0.63 |
| A6           | 10.3.0.8	| 255.255.255.252	| 10.3.0.11 |
| A7           | 10.3.1.0	| 255.255.255.128	| 10.3.1.127 |
| A8           | 10.3.0.12 | 255.255.255.252 | 10.3.0.15 |
| A9           | 10.3.0.16 | 255.255.255.252 | 10.3.0.19 |
| A10           | 10.3.2.0 | 255.255.255.0 | 10.3.2.255 |
| A11           | 10.3.0.20 | 255.255.255.252 |	10.3.0.23 |
| A12           | 10.3.0.40	| 255.255.255.248	| 10.3.0.47 |
| A13           | 10.3.0.24	| 255.255.255.252	| 10.3.0.27 |
| A14           | 10.3.0.28	| 255.255.255.252	| 10.3.0.31 |
| A15           | 10.3.12.0	| 255.255.252.0	| 10.3.15.255 |
| A16           | 10.3.3.0 | 255.255.255.0	| 10.3.3.255 |
| A17           | 10.3.0.32	| 255.255.255.252	| 10.3.0.35 |
| A18           | 10.3.4.0	| 255.255.254.0	| 10.3.5.255 |
| A19           | 10.3.0.36	| 255.255.255.252	| 10.3.0.39 |
| A20           | 10.3.0.128 |	255.255.255.192 |	10.3.0.191 |
| A21           | 10.3.16.0 |	255.255.252.0	| 10.3.19.255 |

### IP Configuration VLSM

#### Aura

```
auto eth1
iface eth1 inet static
	address 10.3.0.17
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.3.0.13
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.3.0.21
	netmask 255.255.255.252
```

#### Frieren

```
auto eth0
iface eth0 inet static
	address 10.3.0.14
	netmask 255.255.255.252
	gateway 10.3.0.13

auto eth1
iface eth1 inet static
	address 10.3.0.9
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.3.1.1
	netmask 255.255.255.128
```

#### Flamme

```
auto eth0
iface eth0 inet static
	address 10.3.0.10
	netmask 255.255.255.252
	gateway 10.3.0.9

auto eth1
iface eth1 inet static
	address 10.3.0.1
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.3.0.5
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.3.8.1
	netmask 255.255.255.252
```

#### Fern

```
auto eth0
iface eth0 inet static
	address 10.3.0.2
	netmask 255.255.255.252
	gateway 10.3.0.1

auto eth1
iface eth1 inet static
	address 10.3.24.1
	netmask 255.255.248.0
```

#### LaubHills(397host)

```
auto eth0
iface eth0 inet static
	address 10.3.25.142
	netmask 255.255.248.0
	gateway 10.3.24.1
```

#### ApetitRegion(625host)

```
auto eth0
iface eth0 inet static
	address 10.3.24.2
	netmask 255.255.248.0
	gateway 10.3.24.1
```

#### RohrRoad(1000host)

```
auto eth0
iface eth0 inet static
	address 10.3.8.2
	netmask 255.255.255.252
	gateway 10.3.8.1
```

#### Himmel

```
auto eth0
iface eth0 inet static
	address 10.3.0.6
	netmask 255.255.255.252
	gateway 10.3.0.5

auto eth1
iface eth1 inet static
	address 10.3.0.57
	netmask 255.255.255.248
```

#### SchwerMountains(5host)

```
auto eth0
iface eth0 inet static
	address 10.3.0.58
	netmask 255.255.255.248
	gateway 10.3.0.57
```

#### Eisen

```
auto eth0
iface eth0 inet static
	address 10.3.0.22
	netmask 255.255.255.252
	gateway 10.3.0.21

auto eth1
iface eth1 inet static
	address 10.3.0.33
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.3.0.29
	netmask 255.255.255.252

auto eth3
iface eth3 inet static
	address 10.3.0.25
	netmask 255.255.255.252

auto eth4
iface eth4 inet static
	address 10.3.0.41
	netmask 255.255.255.248
```

#### Richter
```
auto eth0
iface eth0 inet static
	address 10.3.0.43
	netmask 255.255.255.248
	gateway 10.3.0.41
```

#### Revolte

```
auto eth0
iface eth0 inet static
	address 10.3.0.42
	netmask 255.255.255.248
	gateway 10.3.0.41

```

#### Linie

```
auto eth0
iface eth0 inet static
	address 10.3.0.34
	netmask 255.255.255.252
	gateway 10.3.0.33

auto eth1
iface eth1 inet static
	address 10.3.0.37
	netmask 255.255.255.252

auto eth2
iface eth2 inet static
	address 10.3.4.1
	netmask 255.255.254.0
```

#### GranzChannel(254host)

```
auto eth0
iface eth0 inet static
	address 10.3.4.2
	netmask 255.255.254.0
	gateway 10.3.4.1

```


#### Lawine

```
auto eth0
iface eth0 inet static
	address 10.3.0.38
	netmask 255.255.255.252
	gateway 10.3.0.37

auto eth1
iface eth1 inet static
	address 10.3.0.129
	netmask 255.255.255.192

```


#### BredtRegion(29host)

```
auto eth0
iface eth0 inet static
	address 10.3.0.130
	netmask 255.255.255.192
	gateway 10.3.0.129
```

#### Heiter

```
auto eth0
iface eth0 inet static
	address 10.3.0.131
	netmask 255.255.255.192
	gateway 10.3.0.129

auto eth1
iface eth1 inet static
	address 10.3.16.1
	netmask 255.255.252.0
```

#### Sein

```
auto eth0
iface eth0 inet static
	address 10.3.16.2
	netmask 255.255.252.0
	gateway 10.3.16.1
```


#### RiegelCanyon(510host)

```
auto eth0
iface eth0 inet static
	address 10.3.16.3
	netmask 255.255.252.0
	gateway 10.3.16.1
```


#### Lugner

```
auto eth0
iface eth0 inet static
	address 10.3.0.30
	netmask 255.255.255.252
	gateway 10.3.0.29

auto eth1
iface eth1 inet static
	address 10.3.12.1
	netmask 255.255.252.0

auto eth2
iface eth2 inet static
	address 10.3.3.1
	netmask 255.255.255.0

```

#### GrobForest(250host)

```
auto eth0
iface eth0 inet static
	address 10.3.3.2
	netmask 255.255.255.0
	gateway 10.3.3.1
```


#### TurkRegion(1000host)
```
auto eth0
iface eth0 inet static
	address 10.3.12.2
	netmask 255.255.252.0
	gateway 10.3.12.1
```

#### Stark
```
auto eth0
iface eth0 inet static
	address 10.3.0.26
	netmask 255.255.255.252
	gateway 10.3.0.25
```

#### Denken
```
auto eth0
iface eth0 inet static
	address 10.3.0.18
	netmask 255.255.255.252
	gateway 10.3.0.17

auto eth1
iface eth1 inet static
	address 10.3.2.1
	netmask 255.255.255.0
```

#### WilleRegion(63host)
```
auto eth0
iface eth0 inet static
	address 10.3.2.65
	netmask 255.255.255.0
	gateway 10.3.2.1
```

#### RoyalCapital(63host)
```
auto eth0
iface eth0 inet static
	address 10.3.2.2
	netmask 255.255.255.0
	gateway 10.3.2.1
```

### Routing VLSM
Routing pada GNS dilakukan menggunakan script routing yang nantinya akan ditaruh ke dalam file .bashrc agar dapat dieksekusi setiap kali node dinyalakan.
#### Aura
```
#!/bin/bash
#Frieren
route add -net 10.3.0.8 netmask 255.255.255.252 gw 10.3.0.14
route add -net 10.3.0.0 netmask 255.255.255.252 gw 10.3.0.14
route add -net 10.3.0.4 netmask 255.255.255.252 gw 10.3.0.14
route add -net 10.3.24.0 netmask 255.255.248.0 gw 10.3.0.14
route add -net 10.3.8.0 netmask 255.255.255.252 gw 10.3.0.14
route add -net 10.3.1.0 netmask 255.255.255.128 gw 10.3.0.14
route add -net 10.3.0.56 netmask 255.255.255.248 gw 10.3.0.14

#Eisen
route add -net 10.3.0.40 netmask 255.255.255.248 gw 10.3.0.22
route add -net 10.3.0.32 netmask 255.255.255.252 gw 10.3.0.22
route add -net 10.3.0.28 netmask 255.255.255.252 gw 10.3.0.22
route add -net 10.3.0.24 netmask 255.255.255.252 gw 10.3.0.22
route add -net 10.3.4.0 netmask 255.255.254.0 gw 10.3.0.22
route add -net 10.3.0.36 netmask 255.255.255.252 gw 10.3.0.22
route add -net 10.3.0.128 netmask 255.255.255.192 gw 10.3.0.22
route add -net 10.3.16.0 netmask 255.255.252.0 gw 10.3.0.22
route add -net 10.3.12.0 netmask 255.255.252.0 gw 10.3.0.22
route add -net 10.3.3.0 netmask 255.255.255.0 gw 10.3.0.22

#Denken
route add -net 10.3.2.0 netmask 255.255.255.0 gw 10.3.0.18
```

#### Frieren
```
#!/bin/bash
#Flamme
route add -net 10.3.0.0 netmask 255.255.255.252 gw 10.3.0.10
route add -net 10.3.0.4 netmask 255.255.255.252 gw 10.3.0.10
route add -net 10.3.24.0 netmask 255.255.248.0 gw 10.3.0.10
route add -net 10.3.8.0 netmask 255.255.255.252 gw 10.3.0.10
route add -net 10.3.0.56 netmask 255.255.255.248 gw 10.3.0.10
```

#### Flamme
```
#!/bin/bash
#Fern
route add -net 10.3.24.0 netmask 255.255.248.0 gw 10.3.0.2

#Himmel
route add -net 10.3.0.56 netmask 255.255.255.248 gw 10.3.0.6
```

#### Eisen
```
#!/bin/bash
#Lugne
route add -net 10.3.12.0 netmask 255.255.252.0 gw 10.3.0.30
route add -net 10.3.3.0 netmask 255.255.255.0 gw 10.3.0.30

#Linie
route add -net 10.3.4.0 netmask 255.255.254.0 gw 10.3.0.34
route add -net 10.3.0.36 netmask 255.255.255.252 gw 10.3.0.34
route add -net 10.3.0.128 netmask 255.255.255.192 gw 10.3.0.34
route add -net 10.3.16.0 netmask 255.255.252.0 gw 10.3.0.34
```

#### Linie
```
#!/bin/bash
#Lawine
route add -net 10.3.0.128 netmask 255.255.255.192 gw 10.3.0.38
route add -net 10.3.16.0 netmask 255.255.252.0 gw 10.3.0.38
```

#### Lawine
```
#!/bin/bash
#Heiter
route add -net 10.3.16.0 netmask 255.255.252.0 gw 10.3.0.131
```

### Testing
#### Sein - Richter
<img width="486" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/8717ac1b-8146-4d63-a8f0-edc389ea2875">


#### GranzChannel - TurkRegion
<img width="482" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/228d43a3-c430-47e0-945a-e9f67e0b6e77">


#### RiegelCanyon - Aura
<img width="486" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/b286fbc0-fc43-4c4b-8fe9-1679f124d87f">

#### Fern - Linie
<img width="483" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/7f74b4bf-c70d-46fa-a817-6ce30bb59ae4">


#### RoyalCapital - LaubHills
<img width="478" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/fc206097-1b8f-46f1-9681-659274ce7798">


#### Heiter - Denken
<img width="482" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/261a6985-ce85-45e3-8f63-5c61e94d4f08">

#### SchwerMountains - Lugner
<img width="483" alt="image" src="https://github.com/katarinainezita/Jarkom-Modul-4-A08-2023/assets/105977864/b56093ee-d85b-49b5-8096-ecd35a4ad96b">

## CIDR

### Flow Pembagian CIDR
![Frame 42](https://github.com/katarinainezita/school-management-system/assets/109232320/2f29f4bd-28e6-4960-b7c1-391e9f10b733)
![Frame 43](https://github.com/katarinainezita/school-management-system/assets/109232320/2a2c64bc-121b-4b8c-bf2c-7119edc851b9)
![Frame 44](https://github.com/katarinainezita/school-management-system/assets/109232320/b3e1772c-bfe1-45f9-9288-4a601ff80114)
![Frame 45](https://github.com/katarinainezita/school-management-system/assets/109232320/75d60d2d-bd0c-4a85-89ba-996570a77414)
![Frame 46](https://github.com/katarinainezita/school-management-system/assets/109232320/4fc4cdb5-af54-434c-94ee-5e8281a82bcd)
![Frame 47](https://github.com/katarinainezita/school-management-system/assets/109232320/e6995cdb-e65c-4691-a6d5-8561c82b6186)
![Frame 48](https://github.com/katarinainezita/school-management-system/assets/109232320/0a346687-ac80-49f0-845f-4b218622256b)

### Pembagian CIDR

#### Penggabungan 1
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
| B1           | A21 |	/26	| A20 | /22 | /21 |

#### Penggabungan 2
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
| C1           | B1 |	/21	| A19 | /30 | /20 |
| C2           | A1 |	/21	| A2 | /30 | /20 |
| C3           | A5 |	/29	| A4 | /30 | /28 |


#### Penggabungan 3
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
|D1 |	C3 |	/20 |	A3|	/22	|C2|	/28	|/19|
|D2	|C1	|/20	| A18|	/23|		|	|/19|
|D3	|A15	|/22	| A16	|/24 | |/21|

#### Penggabungan 4
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
|E1|	D1|	/19|	A6	|/30|	/18|
|E2|	D2|	/19|	A17	|/30|	/18|
|E3|	D3|	/21|	A14	|/30|	/20|

#### Penggabungan 5
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
|F1|	E2|	/18|	E3|	/20|	A12|	/29|	A13|	/30|	/17|
|F2|	E1|	/18|	A7|	/25	|			|	  |     |      |/17|

#### Penggabungan 6
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
|G1	|F2	|/17	|A8	|/30	|/16|
|G2	|F1	|/17	|A11	|/30	|/16|
|G3	|A10	|/24	|A9	|/30	|/23|

#### Penggabungan 7
| Subnet       | Subnet 1 | Netmask 1   | Subnet 2 | Netmask 2 | Netmask Akhir |
|------------- |------------|--------------| --------| --------| --------| 
|H1	|G1	|/16	|G2	|/16	|G3	|/23	|/14|


### Tree
![image](https://github.com/katarinainezita/school-management-system/assets/109232320/5ab46705-1b65-4068-8f82-719fb365da45)

### Pembagian IP
| Subnet       | Network ID | Netmask   | Broadcast |
|------------- |------------|--------------| --------| 
|A1	|10.4.0.0	|255.255.248.0	|10.4.7.255|
|A2	|10.4.8.0	|255.255.255.0	|10.4.8.3.255|
|A3	|10.4.16.0	|255.255.252.0	|10.4.19.255|
|A4	|10.4.20.8	|255.255.255.252	|10.4.20.11|
|A5	|10.4.20.0	|255.255.255.248	|10.4.20.7|
|A6	|10.4.32.0	|255.255.255.252	|10.4.32.3|
|A7	|10.4.64.0	|255.255.255.224	|10.4.64.31|
|A8	|10.3.128.0	|255.255.255.252	|10.3.128.3|
|A9	|10.5.1.0	|255.255.255.252	|10.5.1.3|
|A10	|10.5.0.0	|255.255.255.0	|10.5.0.255|
|A11	|10.4.128.0	|255.255.255.252	|10.4.128.3|
|A12	|10.3.80.0	|255.255.255.248	|10.3.80.7|
|A13	|10.3.80.8	|255.255.255.252	|10.3.80.11|
|A14	|10.3.72.0	|255.255.255.252	|10.3.72.3|
|A15	|10.3.64.0	|255.255.252.0	|10.3.67.255|
|A16	|10.3.68.0	|255.255.255.0	|10.3.68.255|
|A17	|10.3.32.0	|255.255.255.252	|10.3.32.3|
|A18	|10.3.16.0	|255.255.254.0	|10.3.17.255|
|A19	|10.3.8.0	|255.255.255.252	|10.3.8.3|
|A20	|10.3.0.0	|255.255.252.0	|10.3.3.255|
|A21	|10.3.4.0	|255.255.255.192	|10.3.4.63|

### IP Configuration

### Routing
Routing pada CPT dilakukan secara langsung menggunakan GUI yang sudah disediakan. Namun, yang perlu diingat di CPT adalah menambahkan gateaway atau next hop di setiap router ke arah router sebelumnya agar setiap request yang diterima oleh router tersebut dapat diteruskan ke router sebelumnya. Sehingga nantinya setiap router akan saling terhubung dan dapat melakukan request dari manapun ke manapun

### Percobaan Ping IP

![image](https://github.com/katarinainezita/school-management-system/assets/109232320/a22f6473-34a7-45f5-928e-379753658146)
![image](https://github.com/katarinainezita/school-management-system/assets/109232320/fcf6aaa1-3d2f-425f-8a19-a8dd319d3288)
