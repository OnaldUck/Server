# Server


dsquery user -samid MUSTERMANN | dsget user -memberof -expand

https://www.medic-daniel.de/active-directory/2012/10/active-directory-mitglieder-einer-gruppe-auslesen

Mitglieder einer Gruppe auslesen

#Nun listen wir uns alle DNs der Mitglieder in der Gruppe
`dsquery group -samid "Domain Users" |dsget group -members`

#Da man meist die Login Namen benötigt wandeln wir nun die DNs in SAMAccountNames um
`dsquery group -samid "Domain Users" |dsget group -members -expand |dsget user -samid`

#Mit der Powershell verkuerzt sich der Befehl enorm
`get-adgroupmember "Domain Users" |ft name`

