# Privilege Escalation Cheatsheet (Vulnhub)

This cheatsheet is aimed at the CTF Players and Beginners to help them understand the fundamentals of Privilege Escalation with examples. It is not a cheatsheet for Enumeration using Linux Commands. Privilege escalation is all about proper enumeration. There are multiple ways to perform the same tasks. We have performed and compiled this list on our experience. Please share this with your connections and direct queries and feedback to [Pavandeep Singh](https://twitter.com/pavan2318).

[1.1]: http://i.imgur.com/tXSoThF.png
[1]: http://www.twitter.com/hackinarticles
# Follow us on [![alt text][1.1]][1]

<img src="https://user-images.githubusercontent.com/23155361/93634827-dfd53700-fa0e-11ea-8110-77406a1b2661.png" alt="cheatsheet" border="0">


Table of Contents
=================

* [Abusing Sudo Rights](#sudo)
* [SUID Bit](#suid)
* [Kernel Exploit](#kernel)
* [Path Variable](#path)
* [Enumeration](#enum)
* [MySQL](#mysql)
* [Cronjob](#cronjob)
* [Wildcard Injection](#wild)
* [Capabilities](#capabilities)
* [Writable /etc/passwd file](#etc)
* [Writable files or script](#root)
* [Buffer Overflow](#buffer)
* [Docker](#docker)
* [Chkrootkit](#chkrootkit)
* [Bruteforce](#bruteforce)
* [Crack /etc/shadow](#shadow)
* [NFS](#nfs)
* [Json](#json)
* [Redis](#redis)
* [LXD](#lxd)
* [All](#all)
* [Exim](#exim)
* [Apache2 Writable](#apache2)

<a name="sudo"></a>
##  Abusing Sudo Rights [⤴](#table-of-contents)

|No.|Machine Name|Files/Binaries|
|-------|--------------|----------------|
|1.|[Ted:1](https://www.hackingarticles.in/ted1-vulnhub-walkthrough/)|apt-get|
|2.|[KFIOFan : 1](https://www.hackingarticles.in/kfiofan1-vulnhub-walkthrough/)|awk|
|3.|[21 LTR: Scene1](https://www.hackingarticles.in/hack-the-21ltr-scene-1-vm-boot-to-root/)|cat| 
|4.|[Skytower](https://www.hackingarticles.in/hack-the-skytower-ctf-chAllenge/)|cat|
|5.|[Matrix : 1](https://www.hackingarticles.in/matrix-1-vulnhub-walkthrough/)|cp|
|6.|[Sputnik 1](https://www.hackingarticles.in/sputnik-1-vulnhub-walkthrough/)|ed|
|7.|[Sunset](https://www.hackingarticles.in/sunset-vulnhub-walkthrough/)|ed|
|8.|[DC-2](https://www.hackingarticles.in/dc-2-walkthrough/)|git|
|9.|[Kioptrix : Level 1.2](https://www.hackingarticles.in/hack-the-kioptrix-level-1-2-boot2root-chAllenge/)|ht|
|10.|[Matrix-3](https://www.hackingarticles.in/matrix-3-vulnhub-walkthrough/)|manual|
|11.|[symfonos : 2](https://www.hackingarticles.in/symfonos2-vulnhub-walkthrough/)|MySQL|
|12.|[Development](https://www.hackingarticles.in/development-vulnhub-walkthrough/)|nano|
|13.|[SP ike](https://www.hackingarticles.in/sp-ike-vulnhub-lab-walkthrough/)|nmap|
|14.|[DC6](https://www.hackingarticles.in/dc6-lab-walkthrough/)|nmap|
|15.|[Dina](https://www.hackingarticles.in/hack-dina-vm-ctf-chAllenge/)|perl|
|16.|[Wakanda : 1](https://www.hackingarticles.in/hack-the-wakanda-1-ctf-chAllenge/)|pip|
|17.|[Violator](https://www.hackingarticles.in/hack-the-violator-ctf-chAllenge/)|proftpd|
|18.|[Broken: Gallery](https://www.hackingarticles.in/broken-gAllery-vulnhub-walkthrough/)|reboot/timedatectl|
|19.|[DE-ICE:S1.120](https://www.hackingarticles.in/hack-the-de-ice-s1-120-vm-boot-to-root/)|script|
|20.|[Fristileaks](https://www.hackingarticles.in/hack-fristileaks-vm-ctf-chAllenge/)|script|
|21.|[DerpNStink](https://www.hackingarticles.in/hack-the-derpnstink-vm-ctf-chAllenge/)|script|
|22.|[Digitalworld.local : JOY](https://www.hackingarticles.in/digitalworld-local-joy-vulnhub-walkthrough/)|script|
|23.|[PumpkinFestival](https://www.hackingarticles.in/mission-pumpkin-v1-0-pumpkinfestival-vulnhub-walkthrough/)|script|
|24.|[The Ether: Evil Science](https://www.hackingarticles.in/hack-ether-evilscience-vm-ctf-chAllenge/)|script|
|25.|[HA:Rudra](https://www.hackingarticles.in/ha-rudra-vulnhub-walkthrough/)|script|
|26.|[djinn:1](https://www.hackingarticles.in/djinn1-vulnhub-walkthrough/)|script|
|27.|[UA: Literally Vulnerable](https://www.hackingarticles.in/ua-literally-vulnerable-vulnhub-walkthrough/)|script|
|28.|[PumpkinRaising](https://www.hackingarticles.in/pumpkinraising-vulnhub-walkthrough/)|strace|
|29.|[Unknowndevice64 : 1](https://www.hackingarticles.in/unknowndevice64-1-vulnhub-lab-walkthrough/)|strace|
|30.|[Holynix: v1](https://www.hackingarticles.in/hack-the-holynix-v1-boot-2-root-chAllenge/)|tar|
|31.|[Breach 2.1](https://www.hackingarticles.in/hack-breach-2-1-vm-ctf-chAllenge/)|tcpdump|
|32.|[Temple of Doom](https://www.hackingarticles.in/hack-the-temple-of-doom-ctf-chAllenge/)|tcpdump|
|33.|[Web Developer : 1](https://www.hackingarticles.in/web-developer-1-vulnhub-lab-walkthrough/)|tcpdump|
|34.|[DC-4](https://www.hackingarticles.in/dc-4-vulnhub-walkthrough/)|teehee|
|35.|[Serial: 1](https://www.hackingarticles.in/serial-1-vulnhub-walkthrough/)|vim|
|36.|[Zico 2](https://www.hackingarticles.in/hack-zico2-vm-ctf-chAllenge/)|zip|
|37.|[HA: Dhanush](https://www.hackingarticles.in/ha-dhanush-vulnhub-walkthrough/)|zip|
|38.|[Sunset: Nightfall](https://www.hackingarticles.in/sunset-nightfall-vulnhub-walkthrough/)|cat|
|39.|[HA: Infinity Stones](https://www.hackingarticles.in/ha-infinity-stones-vulnhub-walkthrough/)|ftp|
|40.|[Sunset-Sunrise](https://www.hackingarticles.in/sunset-sunrise-vulnhub-walkthrough/)|wine|
|41.|[Me and My Girlfreind:1](https://www.hackingarticles.in/me-and-my-girlfreind1-vulnhub-walkthrough/)|php|
|42.|[Symfonos:5](https://www.hackingarticles.in/symfonos5-vulnhub-walkthrough/)|dpkg|
|43.|[Five86:2](https://www.hackingarticles.in/five86-2-vulnhub-walkthrough/)| service |
|44.|[Tempus Fugit:1](https://www.hackingarticles.in/tempus-fugit-1-vulnhub-walkthrough/)|Diffrent for every user|
|45.|[DevRandom CTF:1.1](https://www.hackingarticles.in/devrandom-ctf1-1-vulnhub-walkthrough/)|dpkg|
|46.|[Zion: 1.1](https://www.hackingarticles.in/zion-1-1-vulnhub-walkthrough/)|cp|
|47.|[Seppuku:1](https://www.hackingarticles.in/seppuku1-vulnhub-walkthrough/)|script|
|48.|[GitRoot: 1](https://www.hackingarticles.in/gitroot-1-vulnhub-walkthrough/)|git|
|49.|[Tre:1](https://www.hackingarticles.in/tre1-vulnhub-walkthrough/)|shutdown|
|50.|[BlackRose: 1](https://www.hackingarticles.in/blackrose-1-vulnhub-walkthrough/)|script|
|51.|[So Simple:1](https://www.hackingarticles.in/so-simple1-vulnhub-walkthrough/)|script|
|52.|[CryptoBank:1](https://www.hackingarticles.in/cryptobank-1-vulnhub-walkthrough/)|All|
|53.|[Star Wars:1](https://www.hackingarticles.in/star-wars-1-vulnhub-walkthrough/)|All|
|54.|[Mercury](https://www.hackingarticles.in/mercury-vulnhub-walkthrough/)|script|
|55.|[Durian:1](https://www.hackingarticles.in/durian-1-vulnhub-walkthrough/)|script|
|56.|[Maskcrafter:1.1](https://www.hackingarticles.in/maskcrafter-1-1-vulnhub-walkthrough/)|dpkg|


<a name="suid"></a>
##  SUID Bit [⤴](#table-of-contents)

|No.| Machine Name                 |SUID Bit|
|-------|------------------------------|-------|
|1.|[Kevgir](https://www.hackingarticles.in/hack-kevgir-vm-ctf-challenge/)|cp|
|2.|[digitalworld.local - BRAVERY](https://www.hackingarticles.in/digitalworld-local-bravery-vulnhub-walkthrough/)|cp|
|3.|[Happycorp : 1](https://www.hackingarticles.in/happycorp1-vulnhub-walkthrough/)|cp|
|4.|[FourAndSix : 2](https://www.hackingarticles.in/fourandsix-2-vulnhub-walkthrough/)|doas|
|5.|[DC-1](https://www.hackingarticles.in/dc-1-vulnhub-walkthrough/)|find|
|6.|[dpwwn:2](https://www.hackingarticles.in/dpwwn2-vulnhub-walkthrough/)|find|
|7.|[MinU: v2](https://www.hackingarticles.in/minu-v2-vulnhub-walkthrough/)|Micro Editor|
|8.|[Toppo:1](https://www.hackingarticles.in/hack-the-toppo1-vm-ctf-challenges/)|python 2.7/mawk|
|9.|[Mr. Robot](https://www.hackingarticles.in/hack-mr-robot-vm-ctf-challenge/)|nmap|
|10.|[Covfefe](https://www.hackingarticles.in/hack-covfefe-vm-ctf-challenge/)|script|
|11.|[/dev/random : K2](https://www.hackingarticles.in/hack-the-dev-random-k2-vm-boot2root-challenge/)|script|
|12.|[hackme1](https://www.hackingarticles.in/hackme-1-vulnhub-walkthrough/)|script|
|13.|[Sunset: dawn](https://www.hackingarticles.in/sunset-dawn-vulnhub-walkthrough/)|zsh|
|14.|[HA: Wordy](https://www.hackingarticles.in/ha-wordy-vulnhub-walkthrough/)|cp|
|15.|[bossplayersCTF 1](https://www.hackingarticles.in/bossplayersctf-1-vulnhub-walkthrough/)|find|
|16.|[In Plain Sight:1](https://www.hackingarticles.in/in-plain-sight1-vulnhub-walkthrough/)|script|
|17.|[Five86:1](https://www.hackingarticles.in/five861-vulnhub-walkthrough/)|script|
|18.|[Geisha:1](https://www.hackingarticles.in/geisha1-vulnhub-walkthrough/)|base32|
|19.|[Victim:1](https://www.hackingarticles.in/victim1-vulnhub-walkthrough/)|nohup|
|20.|[eLection: 1](https://www.hackingarticles.in/election-1-vulnhub-walkthorugh/)|script|
|21.|[Photographer 1](https://www.hackingarticles.in/photographer-1-vulnhub-walkthrough/)|php7.2|
|22.|[DMV :1](https://www.hackingarticles.in/dmv-1-vulnhub-walkthrough/)| script|
|23.|[ShellDredd #1 Hannah](https://www.hackingarticles.in/shelldredd-1-hannah-vulnhub-walkthrough/)| cpulimit|
|24.|[KB-Vuln:3](https://www.hackingarticles.in/kb-vuln-3-vulnhub-walkthrough/)| systemctl|

<a name="kernel"></a>
##  Kernel Exploit [⤴](#table-of-contents)

|No.| Machine Name|Kernel|Exploit|
|-------|----------------------|--------------------------------------------------------|-----------------------------------------|
|1.|[pWnOS -1.0](https://www.hackingarticles.in/hack-the-pwnos-1-0-boot-to-root/)|Linux Kernel 2.6.17 < 2.6.24.1| [5092](https://www.exploit-db.com/exploits/5092)|
|2.|[LAMPSecurity: CTF 5](https://www.hackingarticles.in/hack-the-lampsecurity-ctf-5-ctf-challenge/)|Linux Kernel 2.4/2.6|[9479](https://www.exploit-db.com/exploits/9479)|
|3.|[Kioptrix : Level 1.1](https://www.hackingarticles.in/hack-the-kioptrix-level-2-boot2root-challenge/)|CentOS 4.4/4.5 / Fedora Core 4/5/6 x86)|[9542](https://www.exploit-db.com/exploits/9542)|
|4.|[Hackademic-RTB1](https://www.hackingarticles.in/hack-the-hackademic-rtb1-vm-boot-to-root/)| RDS Protocol' Local Privilege Escalation| [15285](https://www.exploit-db.com/exploits/15285)|
|5.|[Hackademic-RTB2](https://www.hackingarticles.in/hack-the-hackademic-rtb2-boot2root/)|RDS Protocol' Local Privilege Escalation|[15285](https://www.exploit-db.com/exploits/15285)|
|6.|[ch4inrulz : 1.0.1](https://www.hackingarticles.in/hack-the-ch4inrulz-1-0-1-ctf-challenge/)|RDS Protocol' Local Privilege Escalation|[15285](https://www.exploit-db.com/exploits/15285)|
|7.|[Kioprtix: 5](https://www.hackingarticles.in/hack-the-kioptrix-5-ctf-challenge/)|FreeBSD 9.0 - Intel SYSRET Kernel Privilege Escalation|[28718](https://www.exploit-db.com/exploits/28718)|
|8.|[Simple](https://www.hackingarticles.in/hack-simple-vm-ctf-challenge/)|Apport/Abrt (Ubuntu / Fedora)| [36746](https://www.exploit-db.com/exploits/36746)|
|9.|[SecOS: 1](https://www.hackingarticles.in/hack-the-secos1-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|10.|[Droopy](https://www.hackingarticles.in/hack-droopy-vm-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|11.|[VulnOS: 2.0](https://www.hackingarticles.in/hack-the-vulnos-2-0-vm-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|12.|[Fartknocker](https://www.hackingarticles.in/hack-fartknocker-vm-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|13.|[Super Mario](https://www.hackingarticles.in/hack-super-mario-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|14.|[Golden Eye:1](https://www.hackingarticles.in/hack-the-golden-eye1-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|15.|[Typhoon : 1.02](https://www.hackingarticles.in/typhoon-1-02-vulnhub-walkthrough/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|16.|[GrimTheRipper:1](https://www.hackingarticles.in/grimtheripper-1-vulnhub-walkthrough/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|17.|[6days](https://www.hackingarticles.in/hack-6days-vm-ctf-challenge/)|Ubuntu 12.04/14.04/14.10/15.04|[37292](https://www.exploit-db.com/exploits/37292)|
|18.|[Lord of the Root](https://www.hackingarticles.in/hack-lord-root-vm-ctf-challenge/)|Ubuntu 14.04/15.10| [39166](https://www.exploit-db.com/exploits/39166)|
|19.|[Acid Reloaded](https://www.hackingarticles.in/hack-acid-reloaded-vm-ctf-challenge/)|Ubuntu 14.04/15.10|[39166](https://www.exploit-db.com/exploits/39166)|
|20.|[Stapler](https://www.hackingarticles.in/hack-stapler-vm-ctf-challenge/)|Ubuntu 16.04|[39772](https://www.exploit-db.com/exploits/39772)|
|21.|[Sidney](https://www.hackingarticles.in/hack-sydney-vm-ctf-challenge/)|Ubuntu 16.04|[39772](https://www.exploit-db.com/exploits/39772)|
|22.|[DC-3](https://www.hackingarticles.in/dc-3-walkthrough/)|Ubuntu 16.04|[39772](https://www.exploit-db.com/exploits/39772)|
|23.|[Pluck](https://www.hackingarticles.in/hack-pluck-vm-ctf-challenge/)|Dirty COW|[40616](https://www.exploit-db.com/exploits/40616)|
|24.|[Lampiao : 1](https://www.hackingarticles.in/hack-the-lampiao-1-ctf-challenge/)|Dirty COW /proc/self/mem' Race Condition|[40847](https://www.exploit-db.com/exploits/40847)|
|25.|[WinterMute : 1](https://www.hackingarticles.in/hack-the-wintermute-1-ctf-challenge/)|GNU Screen 4.5.0|[41154](https://www.exploit-db.com/exploits/41154)|
|26.|[DC-5](https://www.hackingarticles.in/dc-5-vulnhub-walkthrough/)|GNU Screen 4.5.0|[41154](https://www.exploit-db.com/exploits/41154)|
|27.|[BTRSys:dv 2.1](https://www.hackingarticles.in/hack-btrsys-v2-1-vm-boot2root-challenge/)|Linux Kernel 4.4.0 (Ubuntu) - DCCP Double-Free|[41458](https://www.exploit-db.com/exploits/41458)|
|28.|[Nightmare](https://www.hackingarticles.in/hack-the-box-nightmare-walkthrough/)|Ubuntu 14.04/16.04 (KASLR / SMEP)|[43418](https://www.exploit-db.com/exploits/43418)|
|29.|[Trollcave](https://www.hackingarticles.in/hack-the-trollcave-vm-boot-to-root/)|Linux Kernel < 4.4.0-116 (Ubuntu 16.04.4)|[44298](https://www.exploit-db.com/exploits/44298)|
|30.|[Prime: 1](https://www.hackingarticles.in/prime-1-vulnhub-walkthrough/)|Linux Kernel < 4.4.0-116 (Ubuntu 16.04.4)| [44298](https://www.exploit-db.com/exploits/44298)|
|31.|[LAMPSecurity: CTF6](https://www.hackingarticles.in/lampsecurity-ctf6-vulnhub-walkthrough/)|Linux Kernel 2.6|[8478](https://www.exploit-db.com/exploits/8478)|
|32.|[My File Server:1](https://www.hackingarticles.in/my-file-server-1-vulnhub-walkthrough/)|Dirty COW|[40616](https://www.exploit-db.com/exploits/40616)|
|33.|[VulnUni 1.0.1](https://www.hackingarticles.in/vulnuni-1-0-1-vulnhub-walkthrough/)|GUnet OpenEclass E-learning platform 1.7.3|[48106](https://www.exploit-db.com/exploits/48106)|
|34.|[Sumo: 1](https://www.hackingarticles.in/sumo-1-vulnhub-walkthrough/)|Dirty COW|[40839](https://www.exploit-db.com/exploits/40839)|
|35.|[CyberSploit: 1](https://www.hackingarticles.in/cybersploit-1-vulnhub-walkthrough/)|Linux Kernel 3.13.0 < 3.19 (Ubuntu 12.04/14.04/14.10/15.04) - 'overlayfs'|[37292](https://www.exploit-db.com/exploits/37292)|
|36.|[Loly: 1](https://www.hackingarticles.in/loly-1-vulnhub-walkthrough/)|Linux Kernel < 4.13.9 (Ubuntu 16.04 / Fedora 27) |[45010](https://www.exploit-db.com/exploits/45010)|
|37.|[Tomato: 1](https://www.hackingarticles.in/tomato-1-vulnhub-walkthrough/)|Linux Kernel < 4.13.9 (Ubuntu 16.04 / Fedora 27) |[45010](https://www.exploit-db.com/exploits/45010)|

<a name="path"></a>
##  Path Variable [⤴](#table-of-contents)

|No.| Path Variable   | Files  |
|-------|-----------------|--------|
|1.| [PwnLab](https://www.hackingarticles.in/penetration-testing-pwnlab-ctf-challenge/)| cat    |
|2.| [USV](https://www.hackingarticles.in/hack-usv-vm-ctf-challenge/)             | cat    |
|3.| [Zeus:1](https://www.hackingarticles.in/zeus1-vulnhub-walkthrough/)| date   |
|4.| [The Gemini inc](https://www.hackingarticles.in/hack-the-gemini-inc-ctf-challenge/)  | date   |
|5.| [EW-Skuzzy](https://www.hackingarticles.in/hack-ew-skuzzy-vm-ctf-challenge/)|id|
|6.| [Nullbyte](https://www.hackingarticles.in/hack-nullbyte-vm-ctf-challenge/) | ps     |
|7.| [symfonos : 1](https://www.hackingarticles.in/symfonos1-vulnhub-walkthrough/)| curl   |
|8.| [Silky-CTF: 0x01](https://www.hackingarticles.in/silky-ctf-0x01-vulnhub-walkthrough/) | whoami |
|9.| [Beast 2](https://www.hackingarticles.in/beast-2-vulnhub-walkthrough/)   | whoami |
|10.| [HA:Arsenal Avengers](https://www.hackingarticles.in/ha-avengers-arsenal-vulnhub-walkthrough/) | ifconfig |
|11.| [Inclusiveness:1](https://www.hackingarticles.in/inclusiveness-1-vulnhub-walkthrough/)|whoami|
|12.| [MuzzyBox:1](https://www.hackingarticles.in/muzzybox-1-vulnhub-walkthrough/)|ls|
|13.| [TBBT:2](https://www.hackingarticles.in/tbbt2-vulnhub-walkthrough/)|sl|
|14.| [Sunset: Midnight](https://www.hackingarticles.in/sunset-midnight-vulnhub-walkthrough/)|service|
|15.| [Healthcare:1](https://www.hackingarticles.in/healthcare-1-vulnhub-walkthrough/)|fdisk|


<a name="enum"></a>
##  Enumeration [⤴](#table-of-contents)

| No. | Machine Name                                                                                                          |
|-----|-----------------------------------------------------------------------------------------------------------------------|
| 1.   | [The Library:1](https://hackingarticles.in/the-library1-vulnhub-walkthrough/)                                         |
| 2.   | [The Library:2](https://www.hackingarticles.in/the-library2-vulnhub-walkthrough/)                                     |
| 3.   | [LAMPSecurity: CTF 4](https://www.hackingarticles.in/hack-the-lampsecurity-ctf4-ctf-challenge/)                       |
| 4.   | [LAMPSecurity: CTF 7](https://www.hackingarticles.in/hack-the-lampsecurity-ctf-7-ctf-challenge/)                      |
| 5.   | [Xerxes: 1](https://www.hackingarticles.in/xerxes-1-vulnhub-walkthrough/)                                             |
| 6.   | [pWnOS -2.0](https://www.hackingarticles.in/hack-the-pwnos-2-0-boot-2-root-challenge/)                                |
| 7.   | [DE-ICE:S1.130](https://www.hackingarticles.in/hack-the-de-ice-s1-130-boot2root-challenge/)                   |                                                | 8.   | | 8.   | [SickOS 1.1](https://www.hackingarticles.in/hack-sickos-1-1-vm-ctf-challenge/)                              |          
| 9.   | [Tommyboy](https://www.hackingarticles.in/hack-tommyboy-vm-ctf-challenge/)                                    |
| 10.  | [VulnOS: 1](https://www.hackingarticles.in/hack-the-vulnos-1-ctf-challenge/)                                          |
| 11.  | [Spyder Sec](https://www.hackingarticles.in/hack-spydersec-vm-ctf-challenge/)                                         |
| 12.  | [Acid](https://www.hackingarticles.in/hack-acid-vm-ctf-challenge/)                                                    |
| 13.  | [Necromancer](https://www.hackingarticles.in/hack-necromancer-vm-ctf-challenge/)                                      |
| 14.  | [Freshly](https://www.hackingarticles.in/hack-freshly-vm-ctf-challenge/)                                              |
| 15.  | [Fortress](https://www.hackingarticles.in/hack-fortress-vm-ctf-challenge/)                                            |
| 16.  | [Billu : B0x](https://www.hackingarticles.in/hack-billu-b0x-vm-boot2root-challenge/)                                  |
| 17.  | [Defence Space](https://www.hackingarticles.in/hack-the-defense-space-vm-ctf-challengehack-defense-vm-ctf-challenge/) |
| 18.  | [Moria 1.1](https://www.hackingarticles.in/hack-moria-1-1-ctf-challenge/)                                             |
| 19.  | [Analougepond](https://www.hackingarticles.in/hack-analougepond-vm-ctf-challenge/)                                    |
| 20.  | [Lazysysadmin](https://www.hackingarticles.in/hack-lazysysadmin-vm-ctf-challenge/)                                    |
| 21.  | [Bulldog](https://www.hackingarticles.in/hack-bulldog-vm-boot2root-challenge/)                                        |
| 22.  | [BTRSys 1](https://www.hackingarticles.in/hack-btrsys1-vm-boot2root-challenge/)                                       |
| 23.  | [G0rmint](https://www.hackingarticles.in/hack-g0rmint-vm-ctf-challenge/)                                              |
| 24.  | [Blacklight : 1](https://www.hackingarticles.in/hack-the-blacklight-1-ctf-challenge/)                                 |
| 25.  | [The blackmarket](https://www.hackingarticles.in/hack-the-blackmarket-vm-ctf-chAllenge/)  |                                     
| 26.  | [Matrix 2](https://www.hackingarticles.in/matrix-2-vulnhub-lab-walkthrough/)                                          | 
| 27.  | [Basic Pentesting : 2](https://www.hackingarticles.in/hack-the-basic-pentesting2-vm-ctf-chAllenge/)                   |
| 28.  | [Depth](https://www.hackingarticles.in/hack-depth-vm-ctf-challenge/)|
| 29.  | [Bob: 1.0.1](https://www.hackingarticles.in/hack-the-bob-1-0-1-vm-ctf-challenge/)|
| 30.  | [W34kn3ss 1](https://www.hackingarticles.in/w34kn3ss-1-vulnhub-lab-walkthrough/)|
| 31.  | [Replay: 1](https://www.hackingarticles.in/replay-1-vulnhub-lab-walkthrough/)|
| 32.  | [Born2Root: 2](https://www.hackingarticles.in/born2root-2-vulnhub-walkthrough/)|
| 33.  | [CLAMP 1.0.1](https://www.hackingarticles.in/clamp-1-0-1-vulnhub-walkthrough/)|
| 34.  | [WestWild: 1.1](https://www.hackingarticles.in/westwild-1-1-vulnhub-walkthorugh/)|
| 35.  | [64base](https://www.hackingarticles.in/hack-64base-vm-ctf-challenge/)|
| 36.  | [C0m80](https://www.hackingarticles.in/hack-c0m80-vm-boot2root-challenge/)|
| 37.  | [Gibson](https://www.hackingarticles.in/hack-gibson-vm-ctf-challenge/)|
| 38.  | [Quaoar](https://www.hackingarticles.in/hack-quaoar-vm-ctf-challenge/)|
| 39.  | [Hacker Fest: 2019](https://www.hackingarticles.in/hacker-fest-2019-vulnhub-walkthrough/)|
| 40.  | [EVM: 1](https://www.hackingarticles.in/evm-1-vulnhub-walkthrough/)|
| 41.  | [EnuBox:Mattermost](https://www.hackingarticles.in/enubox-mattermost-vulnhub-walkthrough/)|
| 42.  | [2much:1](https://www.hackingarticles.in/2much-1-vulnhub-walkthrough/)|
| 43.  | [mhz_cxf:c1f](https://www.hackingarticles.in/mhz_cxf-c1f-vulnhub-walkthrough/)|
| 44.  | [HA: Pandavas](https://www.hackingarticles.in/ha-pandavas-vulnhub-walkthrough/)|
| 45.  | [GreenOptic:1](https://www.hackingarticles.in/greenoptic-1-vulnhub-walkthrough/)|
| 46.  | [Cewlkid:1](https://www.hackingarticles.in/cewlkid-1-vulnhub-walkthrough/)|
| 47.  | [PowerGrid:1.0.1](https://www.hackingarticles.in/powergrid-1-0-1-vulnhub-walkthrough/)|
| 48.  | [Insanity:1](https://www.hackingarticles.in/insanity-1-vulnhub-walkthrough/)|
| 49.  | [Tempus Fugit:3](https://www.hackingarticles.in/tempus-fugit-3-vulnhub-walkthrough/)|
| 50.  | [HA: Forensics](https://www.hackingarticles.in/ha-forensics-vulnhub-walkthrough/)|
| 51.  | [HA: Vedas](https://www.hackingarticles.in/ha-vedas-vulnhub-walkthrough/)|
| 52.  | [HA: Sherlock](https://www.hackingarticles.in/ha-sherlock-vulnhub-walkthrough/)|

<a name="mysql"></a>
##  MySQL [⤴](#table-of-contents)

| No | Machine Name                                                                                             |
|-----|---------------------------------------------------------------------------------------------------------|
| 1.  | [Kioptrix : Level 1.3](https://www.hackingarticles.in/hack-the-kioptrix-level-1-3-boot2root-challenge/) |
| 2.  | [Raven](https://www.hackingarticles.in/hack-the-raven-walkthrough-ctf-challenge/)                       |
| 3.  | [Raven : 2](https://www.hackingarticles.in/raven-2-vulnhub-walkthrough/)                                |

<a name="cronjob"></a>
##  Cronjob [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Billy Madison](https://www.hackingarticles.in/hack-billy-madison-vm-ctf-challenge/)                     |
|2.	 |[BSides Vancuver: 2018](https://www.hackingarticles.in/hack-the-bsides-vancouver2018-vm-boot2root-challenge/)|
|3.	 |[Jarbas : 1](https://www.hackingarticles.in/hack-the-jarbas-1-ctf-challenge/)|
|4.	 |[SP:Jerome](https://www.hackingarticles.in/spjerome-vulnhub-walkthrough/)|
|5.  |[dpwwn: 1](https://www.hackingarticles.in/dpwwn-1-vulnhub-walkthrough/)|
|6.  |[Sar](https://www.hackingarticles.in/sar-vulnhub-walkthrough/)|
|7.  |[TBBT](https://www.hackingarticles.in/tbbt-funwithflags-vulnhub-walkthrough/)|
|8.  |[Glasgow Smile: 1.1](https://www.hackingarticles.in/glasgow-smile-1-1-vulnhub-walkthrough/)|
|9.  |[LemonSqueezy:1](https://www.hackingarticles.in/lemonsqueezy1-vulnhub-walkthrough/)|

<a name="wild"></a>
##  Wildcard Injection [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Milnet](https://www.hackingarticles.in/hack-milnet-vm-ctf-challenge/)|
|2.	 |[Pipe](https://www.hackingarticles.in/hack-pipe-vm-ctf-challenge/)|

<a name="capabilities"></a>
##  Capabilities [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Kuya : 1](https://www.hackingarticles.in/vulnhub-kuya-1-walkthrough/)|
|2.	 |[DomDom: 1](https://www.hackingarticles.in/domdom-1-vulnhub-walkthrough/)|
|3.  |[HA: Naruto](https://www.hackingarticles.in/ha-naruto-vulnhub-walkthrough/)|
|4.  |[Connect The Dots:1](https://www.hackingarticles.in/connect-the-dots1-vulnhub-walkthough/)|
|5.  |[Katana](https://www.hackingarticles.in/katana-vulnhub-walkthrough/)|
|6.  |[Presidential: 1](https://www.hackingarticles.in/presidential-1-vulnhub-walkthrough/)|
<a name="etc"></a>
##  Writable /etc/passwd file [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Hackday Albania](https://www.hackingarticles.in/hack-hackday-albania-vm-ctf-challenge/)|
|2.	 |[Billu Box 2](https://www.hackingarticles.in/hack-billu-b0x-vm-boot2root-challenge/)|
|3.	 |[Bulldog 2](https://www.hackingarticles.in/hack-the-bulldog2-ctf-challenge/)|
|4.  |[AI: Web: 1](https://www.hackingarticles.in/ai-web-1-vulnhub-walkthrough/)|
|5.  |[Westwild: 2](https://www.hackingarticles.in/westwild-2-vulnhub-walkthrough/)|
|6.  |[Misdirection 1](https://www.hackingarticles.in/misdirection-1-vulnhub-walkthrough/)|
|7.  |[HA: ISRO](https://www.hackingarticles.in/ha-isro-vulnhub-walkthrough/)|
|8.  |[Gears of War: EP#1](https://www.hackingarticles.in/gears-of-war-ep1-vulnhub-walkthrough/)|
|9.  |[DC:9](https://www.hackingarticles.in/dc-9-vulnhub-walkthrough/)|
|10. |[Sahu](https://www.hackingarticles.in/sahu-vulnhub-walkthrough/)|
|11. |[Sunset: Twilight](https://www.hackingarticles.in/sunset-twilight-vulnhub-walkthrough/)|
|12. |[Chili:1](https://www.hackingarticles.in/chili-1-vulnhub-walkthrough/)|

<a name="root"></a>
##  Writable files or script [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Skydog](https://www.hackingarticles.in/hack-skydog-vm-ctf-challenge/)|
|2.	 |[Breach 1.0](https://www.hackingarticles.in/hack-breach-1-0-vm-ctf-challenges/)|
|3.	 |[Bot Challenge: Dexter](https://www.hackingarticles.in/hack-bot-challenge-dexter-boot2root-challenge/)|
|4.	 |[Fowsniff : 1](https://www.hackingarticles.in/fowsniff-1-vulnhub-walkthrough/)|
|5.	 |[Mercy](https://www.hackingarticles.in/mercy-vulnhub-walkthrough/)|
|6.	 |[Casino Royale](https://www.hackingarticles.in/casino-royale-1-vulnhub-walkthrough/)|
|7.	 |[SP eric](https://www.hackingarticles.in/sp-eric-vulnhub-lab-walkthrough/)|
|8.	 |[PumpkinGarden](https://www.hackingarticles.in/pumpkingarden-vulnhub-walkthrough/)|
|9.	 |[Tr0ll: 3](https://www.hackingarticles.in/tr0ll-3-vulnhub-walkthrough/)|
|10. |[Nezuko:1](https://www.hackingarticles.in/nezuko-1-vulnhub-walkthrough/)|
|11. |[Symfonos:3](https://www.hackingarticles.in/symfonos3-vulnhub-walkthrough/)|
|12. |[Tr0ll 1](https://www.hackingarticles.in/hack-the-troll-1-vm-boot-to-root/)|
|13. |[DC:7](https://www.hackingarticles.in/dc7-vulnhub-walkthrough/)|
|14. |[View2aKill](https://www.hackingarticles.in/view2akill-vulnhub-walkthrough/)|
|15. |[CengBox:1](https://www.hackingarticles.in/cengbox-1-vulnhub-walkthrough/)|
|16. |[Broken 2020: 1](https://www.hackingarticles.in/broken-2020-1-vulnhub-walkthrough/)|
|17. |[CengBox:2](https://www.hackingarticles.in/cengbox-2-vulnhub-walkthrough/)|
|18. |[HA:Narak](https://www.hackingarticles.in/ha-narak-vulnhub-walkthrough/)|

<a name="buffer"></a>
##  Buffer Overflow [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Tr0ll 2](https://www.hackingarticles.in/hack-the-tr0ll-2-boot2root-challenge/)|
|2.	 |[IMF](https://www.hackingarticles.in/hack-imf-vm-ctf-challenge/)|
|3.	 |[BSides London 2017](https://www.hackingarticles.in/hack-the-bsides-london-vm-2017boot2root/)|
|4.	 |[PinkyPalace](https://www.hackingarticles.in/hack-the-pinkypalace-vm-ctf-challenge/)|
|5.	 |[ROP Primer](https://www.hackingarticles.in/hack-the-rop-primer-1-0-1-ctf-challenge/)|
|6.  |[CTF KFIOFAN:2](https://www.hackingarticles.in/ctf-kfiofan-2-vulnhub-walkthorugh/)|
|7.  |[Kioptrix : Level 1](https://www.hackingarticles.in/hack-the-kioptrix-level-1/)|
|8.  |[Silky-CTF: 0x02](https://www.hackingarticles.in/silky-ctf-0x02-vulhub-walkthrough/)|


<a name="docker"></a>
##  Docker [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.	 |[Donkey Docker](https://www.hackingarticles.in/hack-donkeydocker-ctf-challenge/)|
|2.	 |[Game of Thrones](https://www.hackingarticles.in/hack-game-thrones-vm-ctf-challenge/)|
|3.	 |[HackinOS : 1](https://www.hackingarticles.in/hackinos1-vulnhub-lab-walkthrough/)|
|4.  |[HA: Chakravyuh](https://www.hackingarticles.in/ha-chakravyuh-vulnhub-walkthrough/)|
|5.  |[Mumbai:1](https://www.hackingarticles.in/mumbai1-vulnhub-walkthrough/)|
|6.  |[Sunset: dusk](https://www.hackingarticles.in/sunset-dusk-vulnhub-walkthrough/)|

<a name="chkrootkit"></a>
##  Chkrootkit [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.  |[SickOS 1.2](https://www.hackingarticles.in/hack-the-sickos-1-2-vm-ctf-challenge/)|
|2.  |[Sedna](https://www.hackingarticles.in/hack-sedna-vm-ctf-challenge/)|
|3.  |[HA: Chanakya](https://www.hackingarticles.in/ha-chanakya-vulnhub-walkthrough/)|
|4.  |[Sunset: decoy](https://www.hackingarticles.in/sunset-decoy-vulnhub-walkthrough/)|

<a name="bruteforce"></a>
##  Bruteforce [⤴](#table-of-contents) 
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.  |[Rickdiculouslyeasy](https://www.hackingarticles.in/hack-rickdiculouslyeasy-vm-ctf-challenge/)|
|2.  |[RootThis : 1](https://www.hackingarticles.in/vulnhub-rootthis-1-walkthrough/)|
|3.  |[LAMPSecurity: CTF 8](https://www.hackingarticles.in/hack-the-lampsecurity-ctf8-ctf-challenge-2/)|
|4.  |[Cyberry:1](https://hackingarticles.in/hack-vm-cyberry-1boot2root-challenge/)|
|5.	 |[Born2root](https://www.hackingarticles.in/hack-born2root-vm-ctf-challenge/) |

<a name="shadow"></a>
##  Crack /etc/shadow [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.  |[DE-ICE:S1.140](https://www.hackingarticles.in/hack-the-de-ice-s1-140-boot-to-root/)|
|2.  |[Minotaur](https://www.hackingarticles.in/hack-minotaur-vm-ctf-challenge/)|
|3.  |[Moonraker:1](https://www.hackingarticles.in/moonraker1-vulnhub-walkthrough/)|
|4.  |[Basic Penetration](https://www.hackingarticles.in/hack-the-basic-penetration-vm-boot2root-challenge/)|
|5.  |[W1R3S.inc](https://www.hackingarticles.in/hack-the-w1r3s-inc-vm-ctf-challenge/)|

<a name="nfs"></a>
##  NFS [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.  |[Orcus](https://www.hackingarticles.in/hack-orcus-vm-ctf-challenge/)|
|2.  |[FourAndSix](https://www.hackingarticles.in/hack-the-fourandsix-ctf-challenge/)|

<a name="json"></a>
##  Json [⤴](#table-of-contents)
| No | Machine Name |Json|
|----|-----------------------------------------------------------------------------------------|-------|
|1.  |[MinU: 1](https://www.hackingarticles.in/hack-the-minu-1-ctf-challenge/)| Json Token|
|2.  |[Symfonos:4](https://www.hackingarticles.in/symfonos4-vulnhub-walkthrough/)| Json Pickle|

<a name="redis"></a>
##  Redis [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1. |[Gemini inc:2](https://www.hackingarticles.in/hack-the-gemini-inc2-ctf-challenge/)|

<a name="lxd"></a>
##  LXD [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1. |[AI: Web: 2](https://www.hackingarticles.in/ai-web-2-vulnhub-walkthrough/)|
|2. |[HA: Joker](https://www.hackingarticles.in/ha-joker-vulnhub-walkthrough/)|
|3. |[CyNix:1](https://www.hackingarticles.in/cynix1-vulnhub-walkthrough/)|


<a name="all"></a>
##  ALL [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.  |[Lin.Security](https://www.hackingarticles.in/hack-the-lin-security-vm-boot-to-root/)|
|2.  |[Escalate_Linux](https://www.hackingarticles.in/escalate_linux-vulnhub-walkthrough-part-1/)|
|3.  |[Jigsaw:1](https://www.hackingarticles.in/jigsaw1-vulnhub-walkthrough/)|

<a name="Exim"></a>
## Exim[⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
| 1. |[DC:8](https://www.hackingarticles.in/dc8-vulnhub-walkthrough/)                                          |

<a name="apache2"></a>
##  Apache2 Writable [⤴](#table-of-contents)
| No | Machine Name                                                                                            |
|----|---------------------------------------------------------------------------------------------------------|
|1.|[Torment](https://www.hackingarticles.in/digitalworld-localtorment-vulnhub-walkthrough/)|
|2.|[HA: Armour](https://www.hackingarticles.in/ha-armour-walkthrough/)|
|3.|[HA: Natraj](https://www.hackingarticles.in/ha-natraj-vulnhub-walkthrough/)
