# Jarkom-Modul-5-IT08-2024

| Nama          | NRP          |
| ------------- | ------------ |
| Irfan Qobus Salim | 5027221058 |
| Aisha Ayya Ratiandari | 5027231056 |

## Topologi
![A1](https://github.com/user-attachments/assets/4cdaed88-2e8f-44cc-a042-5356c9e0908b)

## Pembagian Rute Subnet
| Nama Subnet | Rute | Jumlah IP | Netmask |
|-------------|------|------------|---------|
| A1          | NewEridu > LuminaSquare | 2   | /30     |
| A2          | LuminaSquare > Ofc.Mewmew > HIA > Ofc.Mewmew > BalletTwins | 3   | /29     |
| A3          | LuminaSquare > PubSec > Jane(200-Host) > PubSec > Policeboo(30-Host) | 231 | /24     |
| A4          | BalletTwins > Victoria > Lycaon(20-Host) > Victoria > Ellen(100-Host) | 121 | /25     |
| A5          | NewEridu > SixStreet | 2   | /30     |
| A6          | SixStreet > RandomPlay > Fairy > HDD | 3   | /29     |
| A7          | SixStreet > Metro > OuterRing > Metro > ScootOutpost | 3   | /29     |
| A8          | ScootOutpost > HollowZero | 2   | /30     |
| A9          | OuterRing > SoC > Burnice(5-Host) > SoC > Caesar(50-Host) | 56  | /26     |
| **Total**   |                          | **423** | **/23** |

## Pembagian IP VLSM
| Subnet | Network ID        | Netmask          | Broadcast       | Range IP                     |
|--------|-------------------|------------------|-----------------|------------------------------|
| A3     | 192.237.0.0       | 255.255.255.0    | 192.237.0.255   | 192.237.0.1 - 192.237.0.254 |
| A4     | 192.237.1.0       | 255.255.255.128  | 192.237.1.127   | 192.237.1.1 - 192.237.1.126 |
| A9     | 192.237.1.128     | 255.255.255.192  | 192.237.1.191   | 192.237.1.129 - 192.237.1.190 |
| A2     | 192.237.1.192     | 255.255.255.248  | 192.237.1.199   | 192.237.1.193 - 192.237.1.198 |
| A6     | 192.237.1.200     | 255.255.255.248  | 192.237.1.207   | 192.237.1.201 - 192.237.1.206 |
| A7     | 192.237.1.208     | 255.255.255.248  | 192.237.1.215   | 192.237.1.209 - 192.237.1.214 |
| A1     | 192.237.1.216     | 255.255.255.252  | 192.237.1.219   | 192.237.1.217 - 192.237.1.218 |
| A5     | 192.237.1.220     | 255.255.255.252  | 192.237.1.223   | 192.237.1.221 - 192.237.1.222 |
| A8     | 192.237.1.224     | 255.255.255.252  | 192.237.1.227   | 192.237.1.225 - 192.237.1.226 |

## Konfigurasi
- NewEridu
```
auto lo
iface lo inet loopback

auth eth0
iface eth0 inet dhcp

#A5
auto eth1
iface eth1 inet static
	address 192.237.1.221
	netmask 255.255.255.252

#A1
auto eth2
iface eth2 inet static
	address 192.237.1.217
	netmask 255.255.255.252
```

- SixStreet
```
auto lo
iface lo inet loopback

#A5
auto eth0
iface eth0 inet static
    address 192.237.1.222
    netmask 255.255.255.252
    gateway 192.237.1.221

#A6
auto eth2
iface eth2 inet static
    address 192.237.1.201
    netmask 255.255.255.248

#A7
auto eth1
iface eth1 inet static
    address 192.237.1.209
    netmask 255.255.255.252
```

- HDD
```
#A6
auto eth0
iface eth0 inet static
    address 192.237.1.202
    netmask 255.255.255.248
    gateway 192.237.1.201
```

- Fairy
```
#A6
auto eth0
iface eth0 inet static
    address 192.237.1.203
    netmask 255.255.255.248
    gateway 192.237.1.201
```

- ScootOutpost
```
auto lo
iface lo inet loopback

#A7
auto eth0
iface eth0 inet static
    address 192.237.1.210
    netmask 255.255.255.248
    gateway 192.237.1.209

#A8
auto eth1
iface eth1 inet static
    address 192.237.1.225
    netmask 255.255.255.252
```

- HollowZero
```
#A8
auto eth0
iface eth0 inet static
    address 192.237.1.226
    netmask 255.255.255.252
    gateway 192.237.1.225
```

- OuterRing
```
auto lo
iface lo inet loopback

#A7
auto eth0
iface eth0 inet static
    address 192.237.1.211
    netmask 255.255.255.248
    gateway 192.237.1.209

#A9
auto eth1
iface eth1 inet static
    address 192.237.1.129
    netmask 255.255.255.192
```

- Caesar (50 Host)
```
#A9
auto eth0
iface eth0 inet static
    address 192.237.1.130
    netmask 255.255.255.192
    gateway 192.237.1.129
```

- Burnice (5 Host)
```
#A9
auto eth0
iface eth0 inet static
    address 192.237.1.131
    netmask 255.255.255.192
    gateway 192.237.1.129
```

- LuminaSquare
```
auto lo
iface lo inet loopback

#A1
auto eth0
iface eth0 inet static
    address 192.237.1.218
    netmask 255.255.255.252
    gateway 192.237.1.217

#A3
auto eth1
iface eth1 inet static
    address 192.237.0.1
    netmask 255.255.255.0

#A2
auto eth2
iface eth2 inet static
    address 192.237.1.193
    netmask 255.255.255.248
```
  
- Jane (200 Host)
```
#A3
auto eth0
iface eth0 inet static
    address 192.237.0.2
    netmask 255.255.255.0
    gateway 192.237.0.1
```

- Policeboo (30 Host)
```
#A3
auto eth0
iface eth0 inet static
    address 192.237.0.3
    netmask 255.255.255.0
    gateway 192.237.0.1
```

- HIA
```
#A2
auto eth0
iface eth0 inet static
    address 192.237.1.194
    netmask 255.255.255.248
    gateway 192.237.1.193
```

- BalletTwins
```
auto lo
iface lo inet loopback

#A2
auto eth0
iface eth0 inet static
    address 192.237.1.195
    netmask 255.255.255.248
    gateway 192.237.1.193

#A4
auto eth1
iface eth1 inet static
    address 192.237.1.1
    netmask 255.255.255.128
```

- Lycaon (20 Host)
```
#A4
auto eth0
iface eth0 inet static
    address 192.237.1.2
    netmask 255.255.255.128
    gateway 192.237.1.1
```

- Ellen (100 Host)
```
#A4
auto eth0
iface eth0 inet static
    address 192.237.1.3
    netmask 255.255.255.128
    gateway 192.237.1.1
```
## Misi 1 Nomor 4
**Testing web server HollowZero dan HIA**
![image](https://github.com/user-attachments/assets/36779bd4-a3b5-4546-b3b9-4b7ffa2d596b)
![image](https://github.com/user-attachments/assets/37ea6c27-fe05-4d4e-acfc-1e6b55ffacfd)

**Testing IP Client mendapatkan IP dari DHCP server**
![image](https://github.com/user-attachments/assets/85bf7fcb-fc5c-4257-9415-4d309ae507fa)
![image](https://github.com/user-attachments/assets/24e5bdf6-0e25-4dd5-803b-a7274ef4576d)
![image](https://github.com/user-attachments/assets/e1f941ee-71a4-4942-ab38-a5e4da35bc46)
![image](https://github.com/user-attachments/assets/768aa94d-afaa-4952-a2fa-261abb05ce9c)
![image](https://github.com/user-attachments/assets/c707b073-810f-42a1-a90d-f0ed5ab64ef6)
![image](https://github.com/user-attachments/assets/2b471053-941e-4e4e-9761-0ebd278c4803)



