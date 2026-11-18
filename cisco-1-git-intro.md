# **Essential Cisco Switch Commands**

### 1. Navigation & General Commands

Elevates session from User EXEC to Privileged EXEC mode.

    enable (en)

Enters Global Configuration mode from Privileged EXEC.

    configure terminal (conf t)

Exits any configuration sub-mode straight back to Privileged EXEC mode.

    end or Ctrl + Z

Steps back out of the current mode by one level.

    exit

Drops back down from Privileged EXEC to User EXEC mode.

    disable

### 2. Basic Configuration & Saving

Sets the name/identifier of the switch in Global Configuration mode.

    hostname [name]

Set a console password.

    line console 0
    password [YourConsolePassword]
    login
    exit

Set VTY Lines

    line vty 0 15
    password [SSHpassword]
    login
    exit
    
Sets an encrypted password for entering Privileged EXEC mode.

    enable secret [password]

Encrypts all plaintext passwords stored in the configuration file.

    service password-encryption

MOTD

    banner motd "MOTD"

Saves your active RAM configuration into NVRAM so it survives a reboot.

    copy running-config startup-config (wr or copy run start)

### 3. Verification & Troubleshooting Commands

Displays the active configuration currently loaded in RAM.

    show running-config (sh run)

Displays the saved configuration stored in NVRAM.

    show startup-config (sh start)

Gives a quick tabular summary of all switch/router interfaces, IP assignments, and line/protocol statuses.

    show ip interface brief (sh ip int br)

Displays the switch's learned MAC address-to-VLAN-to-port mapping table.

    show mac address-table (sh mac add)

Lists all configured VLANs and the ports assigned to them.

    show vlan (sh vlan)

Shows active trunk ports and which VLANs are allowed across them.

    show interfaces trunk (sh int trunk)

Displays IOS software version, uptime, hardware model, and license info.

    show version (sh ver)

Tests basic layer-3 reachability to another network device.

    ping [ip-address]

### 4. VLAN & Interface Configuration Commands

Creates or accesses a specific VLAN configuration sub-mode (e.g., vlan 10).

    vlan [vlan-id]

Assigns a descriptive label to the active VLAN.

    name [vlan-name]

 (e.g., interface GigabitEthernet0/1): Enters configuration mode for a specific physical port.

    interface [type slot/port]

Sets the switch port to act as a standard access port for a single VLAN.

    switchport mode access

Assigns the access port to a specific VLAN number.

    switchport access vlan [id]

Configures the port to carry multiple VLANs (trunk link).

    switchport mode trunk

Administratively enables a physical interface (turns the port on).

    no shutdown (no shut)