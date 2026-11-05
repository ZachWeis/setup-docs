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

Sets an encrypted password for entering Privileged EXEC mode.

    enable secret [password]

Encrypts all plaintext passwords stored in the configuration file.

    service password-encryption

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

# Cisco 1 Intro Codes

analyst@secOps ~]$ 1s
Desktop Downloads lab.support.files second drive
[analyst@secOps ~]$

User Exec Mode: Limited basic commands, veiw only ish - Switch>, Router>
Privileged: Access to all commands - Switch#, Router#

Various commands are used to move in and out of command prompts. To move from user EXEC mode to privileged EXEC mode, use the.
‘enable command. Use the disable privileged EXEC mode command to return to user EXEC mode.
Note: Privileged EXEC mode is sometimes called enable mode.
To move in and out of global configuration mode, use the configure terminal privileged EXEC mode command. To return to the privileged
EXEC mode, enter the exit global config mode command.
There are many different subconfiguration modes. For example, to enter line subconfiguration mode, you use the line command followed
by the management line type and number you wish to access. Use the exit command to exit a subconfiguration mode and return to
global configuration mode.

    Switch(config)# line console 0
    Switch(config-line)# exit
    Switch(config)#

To move from any subconfiguration mode of the global configuration mode to the mode one step above it in the hierarchy of modes,
enter the exit command.
To move from any subconfiguration mode to the privileged EXEC mode, enter the end command or enter the key combination Ctrl+Z.

    Switch(config-line)# end
    Switch

You can also move directly from one subconfiguration mode to another. Notice how after selecting an interface, the command prompt
changes from (config-fine)t to (config-if)#.

    Switch(config-line)# interface FastEthernet 0/1
    Switch(config-if)#

Enter privileged EXEC mode using the enable command.

    Switch> enable

Return to user EXEC mode using the disable command.
    
    Switch# disable

Re-enter privileged EXEC mode.

    Switch> enable

Enter global configuration mode using the configure terminal command.

    Switch# configure terminal

Exit global configuration mode and return to privileged EXEC mode using the exit command.

    switch(config)# exit

Re-enter global configuration mode.

    Switch> enable

Enter global configuration mode using the configure terminal command.

    Switch configure terminal

Exit global configuration mode and return to privileged EXEC mode using the exit command.

    switch(config)# exit

Re-enter global configuration mode.

    Switch(config)# line vty © 15

Return to global configuration mode.

    Switch(config-line)# exit

Enter the VLAN 1 interface subconfiguration mode using the interface vian 1 command.

    Switch(config)# interface vlan 1

From interface configuration mode, switch to line console subconfiguration mode using the line console 0 global configuration command.

    Switch(config-if)# line console 8

Retum to privileged EXEC mode using the end command.

    Switch(config-line)# end

You successfully navigated between the various I0S command line modes.

    Switch(config-if)# switchport port-security aging {  static | time time |     type   {absolute | inactivity}

    Switch# configure terminal
    Switch(config)# hostname Sw-Floor-1
    Sw-Floor-1(config)#

    Switch# configure terminal
    Switch(config)# hostname Sw-Floor-1
    Sw-Floor-1(config)#

    Switch# configure terminal
    Switch(config)# hostname Sw-Floor-1
    Sw-Floor-1(config)#

    Switch# configure terminal
    Switch(config)# hostname Sw-Floor-1
    Sw-Floor-1(config)#

    Switch# configure terminal
    Switch(config)# hostname Sw-Floor-1
    Sw-Floor-1(config)#

    Sw-Floor-1(config)# end
    Sw-Floor-1# show running-config
            !
            (Output omitted)
            !
            line con ©
            password 7 094F471A1A0A
            login
            1
            line vty 0 4
            password 7 094F471A1A0A
            login
            line vty 5 15
            password 7 094F471A1A0A
            login
            !
            !
            end

    Sw-Floor-1# configure terminal
    Sw-Floor-1(config)# banner motd #Authorized Access Only#

Example
    Sw-Floor-1# show running-config
    Building configuration...
    Current configuration : 1351 bytes
    !
    ! Last configuration change at 00:01:20 UTC Mon Mar 1 1993
    !
    version 15.0
    no service pad
    service timestamps debug datetime msec
    service timestamps log datetime msec
    service password-encryption
    !
    hostname Sw-Floor-1
    !
    (output omitted)
    


Cisco Switch CLI Modes

Cisco switches use hierarchical command-line modes. You must enter specific modes to run different types of commands:

Mode	Prompt Example	Purpose
User EXEC Mode	Switch>	Basic monitoring, viewing status, and running non-destructive show commands.
Privileged EXEC Mode	Switch#	Full administrative control, debugging, and saving configurations (entered via enable).
Global Configuration Mode	Switch(config)#	Changing system-wide device settings (entered via configure terminal).
Interface Configuration Mode	Switch(config-if)#	Configuring specific ports/interfaces (entered via interface [type] [number]).


