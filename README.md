# Static-Nat-
Static NAT is implemented using CISCO packet tracer application
Configuration:-

+ 1.Access the router's command-line interface.
+ 2.Configure the necessary interfaces with appropriate IP addresses. For example:
  + #interface Serial0/0
  + #ip address 200.200.200.1 255.255.255.0
  + #no shutdown
  + #exit
  
  + #interface FastEthernet0/0
  + #ip address 192.168.1.1 255.255.0.0
  + #no shutdown
  + #exit
+ 3.Set up static NAT mappings for internal devices:
    + #ip nat inside source static 192.168.1.10 200.200.200.3
    + #ip nat inside source static 192.168.1.11 200.200.200.4
+ 4.Define NAT Inside and Outside interfaces:
    + #interface Serial0/0
    + #ip nat outside
    + #exit

    + #interface FastEthernet0/0
    + #ip nat inside
    + #exit
+ 5.Save the configuration.

Usage:-
Make sure the router is powered on and connected to the network. The static NAT mappings should now be in effect.

Connectivity Testing:-
To test the connectivity, initiate ping tests between devices:
+ 1.From PC1, ping an external device using its public IP address.
+ 2.From an external device, ping PC1 using its private IP address.
