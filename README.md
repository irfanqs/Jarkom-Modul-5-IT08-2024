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
