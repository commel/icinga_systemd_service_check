# Icinga Check for system services

## Requirements
This check only requires Python 3.6 (openSUSE Leap 15.4 based) and nothing
more. Place it somewhere accessible for Icinga.

## Arguments

	./check_systemd_service -n MYSERVICE -u myservice.service 

* -n Label for this service check
* -u Unit-Name of the service to be checked
* -s sets the state when the service is not "active". Default is 2 (CRIT)

## Installation
Place the check_systemd_service somewhere where Icinga can access it (e.g. /usr/local/bin). Then append the
content of ```services.conf``` and ```commands.conf``` to your Icinga files.

## Config
Put this in your ```host.conf```:

```
        vars.systemd_services["Minecraft"] = {
                systemd_service_name = "Minecraft"
                systemd_service_unit = "gameserver@minecraft.service"
        }

```

