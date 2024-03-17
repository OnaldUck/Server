# Server

### Alle Gruppen eines Benutzer auflisten

`dsquery user -samid MUSTERMANN | dsget user -memberof -expand`

https://www.medic-daniel.de/active-directory/2012/10/active-directory-mitglieder-einer-gruppe-auslesen

### Mitglieder einer Gruppe auslesen

#Nun listen wir uns alle DNs der Mitglieder in der Gruppe

`dsquery group -samid "Domain Users" |dsget group -members`

#Da man meist die Login Namen benötigt wandeln wir nun die DNs in SAMAccountNames um

`dsquery group -samid "Domain Users" |dsget group -members -expand |dsget user -samid`

#Mit der Powershell verkuerzt sich der Befehl enorm

`get-adgroupmember "Domain Users" |ft name`

S.M.A.R.T. Werte auslesen
`wmic diskdrive get model,name,serialnumber,status`
```
Model                                  Name                SerialNumber          Status  
Samsung SSD 860 PRO 256GB              \\.\PHYSICALDRIVE0  S42VNX0N503966F       OK      
SanDisk Extreme 55AE SCSI Disk Device  \\.\PHYSICALDRIVE3  2350AE400782          OK      
Samsung SSD 990 PRO with Heatsink 2TB  \\.\PHYSICALDRIVE1  0025_3846_3141_0BB8.  OK      
Samsung SSD 990 PRO with Heatsink 2TB  \\.\PHYSICALDRIVE2  0025_384C_3141_1DE7.  OK      
```
