# Jarkom_Modul3_Lapres_T17 

Kelompok T17
  * Milenia Ulwan Zafira (05311840000020)
  * Bayu Trianayasa      (05311840000038)

## Topologi
```
# Switch
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,'ip_tuntap_tiap_kelompok' eth1=daemon,,,switch1 eth2=daemon,,,switch3 eth3=daemon,,,switch2 mem=256M &

# Server
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch2 mem=128M &
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch2 mem=160M &
xterm -T TUBAN -e linux ubd0=TUBAN,jarkom umid=TUBAN eth0=daemon,,,switch2 mem=128M &

# Klien
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch1 mem=64M &
xterm -T GRESIK -e linux ubd0=GRESIK,jarkom umid=GRESIK eth0=daemon,,,switch1 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch3 mem=64M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch3 mem=64M &...
```
## Interfaces UML (Setting IP)
* [Surabaya](#Surabaya)
* [Malang](#Malang)
* [Mojokerto](#Mojokerto)
* [Tuban](#Tuban)
* [Sidoarjo](#Sidoarjo)
* [Gresik](#Gresik)
* [Banyuwangi](#Banyuwangi)
* [Madiun](#Madiun)



## Table of Contents
* [Soal 1](#soal-1)
* [Soal 2](#soal-2)
* [Soal 3](#soal-3)
* [Soal 4](#soal-4)
* [Soal 5](#soal-5)
* [Soal 6](#soal-6)
* [Soal 7](#soal-7)
* [Soal 8](#soal-8)
* [Soal 9](#soal-9)
* [Soal 10](#soal-10)
---

## Surabaya
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.70.58
netmask 255.255.255.252
gateway 10.151.70.57

auto eth1
iface eth1 inet static
address 10.151.71.113
netmask 255.255.255.248

auto eth2
iface eth2 inet static
address 192.168.0.1
netmask 255.255.255.0

auto eth3
iface eth3 inet static
address 10.151.71.113
netmask 255.255.255.0
````

## Malang
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.71.114
netmask 255.255.255.248
gateway 10.151.71.113
```

## Mojokerto 
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.71.115
netmask 255.255.255.248
gateway 10.151.71.113
```

## Tuban
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.151.71.116
netmask 255.255.255.248
gateway 10.151.71.113
```

## Sidoarjo
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.0.2
netmask 255.255.255.0
gateway 192.168.0.1
```

## Gresik
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.0.3
netmask 255.255.255.0
gateway 192.168.0.1
```


## Banyuwangi
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.0.4
netmask 255.255.255.0
gateway 192.168.1.1
```

## Madiun
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 192.168.0.5
netmask 255.255.255.0
gateway 192.168.1.1
```
---

## Soal 1

- Pertama kita setting topologi.sh pada virtual machine agar menambahkan beberapa UML baru dan mengatur seluruh network interface agar sesuai dengan gambar topologi seperti berikut : 

![picture](https://cdn.discordapp.com/attachments/691272824765284362/782303302128893962/modul3_1.jpg)

- Lalu pada bye.sh juga disetting dan menambahkan UML yang baru.

- Untuk Router SURABAYA disetting dulu net.ipv4.ip_forward pada /etc/sysctl.conf lalu diaktifkan dengan command sysctl -p 

- Masing-masing UML akan disetting network interfacenya.

- Lalu masing-masing UML akan di service networking restart. Untuk UML Client, command tersebut dijalankan setelah setting DHCP server (TUBAN) selesai.

## Soal 2 

Pada router, kita install DHCP relay dengan command ''apt-get install isc-dhcp-relay''. Lalu kita buka ''/etc/default/isc-dhcp-relay" dan mengedit konfigurasi seperti berikut.



## Soal 3



## Soal 4



## Soal 5



## Soal 6



## Soal 7


## Soal 8



## Soal 9 


## Soal 10
