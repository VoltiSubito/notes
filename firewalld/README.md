# Firewalld

## Get All Zones

  + `firewall-cmd --get-zones`

## Get Active Zones

  + `firewall-cmd --get-active-zones`

## Temporarily add a port to current zone

  + `firewall-cmd --add-port=2888/tcp`

## Permanently add a port

  + `firewall-cmd --zone=SomeZone --add-port=8080/tcp --permanent`

## Reload

  + `firewall-cmd --reload`