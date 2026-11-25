# Lab environment

This is a proposed topology, not an inventory of deployed equipment. The scenarios can be studied as tabletop exercises without buying or deploying the products.

| Component | Fictional assignment |
| --- | --- |
| Client VLAN | 10.20.10.0/24; test client 10.20.10.50 |
| Server VLAN | 10.20.20.0/24; app 10.20.20.30; file server 10.20.20.10 |
| Guest VLAN | 10.20.40.0/24; guest client 10.20.40.50 |
| Branch subnet | 10.30.20.0/24; test server 10.30.20.30 |
| AD/DNS/DHCP lab server | dc01.lab.example; 10.20.10.10 |
| Identity | Fictional account lab.user |
| FortiGate | Routed VLANs and IPsec; confirm hardware, VDOM and actual FortiOS build |

All addresses are illustrative private lab addresses. Names under lab.example are placeholders. No real Five9 or Sophos tenant endpoint is supplied.

Windows examples target Windows PowerShell 5.1 on Windows 11 or a supported Windows Server lab. AD and DHCP examples require the appropriate RSAT modules and delegated permissions. Reading Security logs may require additional rights. Audit collection must be enabled before events can be expected.

FortiGate commands use the FortiOS 7.6 troubleshooting reference as a documentation baseline, not a deployment or upgrade recommendation. Validate syntax and hardware-specific behaviour against the actual build.

Sophos cases assume a test tenant with appropriate endpoint protection and, where needed, EDR/XDR capabilities. Check both entitlement and role before using queries or response actions. Vendor documentation may now label parts of the management interface Sophos Fusion; confirm the menus visible in the actual tenant rather than assuming names are unchanged.

Five9 cases require an authorised test environment and test interactions. Record the region, browser, desktop integration, station type, installed component versions and local/VDI placement. Browser WebRTC and installed softphones have different requirements. Use the current requirements for that deployment; no universal ports, IP ranges or performance thresholds are claimed here.
