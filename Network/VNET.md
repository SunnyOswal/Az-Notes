**VNET**  
Cannot span subscriptions. Therfore you have to **connect VNets to enable communication between resources in different subscriptions**.  
+ **SUBNET**  
AZ reserves 5 Host IP's for internal use. Therefore x.x.x.x/29 will be the smallest subnet possible in AZ VNET.  
`4 at the beginning of subnet range and 1 at the end`  
+ **VPN Gateway**  
  + Type of virtual network gateway that sends **encrypted** traffic across a public connection to an On-prem location.  
  + Also can be used to send **encrypted** traffic b/w az VNets over MSFT network.
  + This is created **ON** Azure VNet.  
  + **Only 1 gateway per VNet**. But support multiple connections from the same gateway (bandwidth is shared)

+ **SITE-TO-SITE**
  + Connection over **IPSec/IKE** VPN Tunnel.
  + VPN gateway on Az VNet and VPN device(with Public IP) located on-Prem.
+ **POINT-TO-SITE**
  + Connection over **SSTP** Tunnel.
  + VPN gateway on Az VNet and VPN client(certificate based) on individual client.
+ **EXPRESS ROUTE**
  + Connection over **BGP**. **No Encryption** as it is on private msft network .
  + **3 Connectivity models** : Co-located at a cloud exchange , Point-to-point Ethernet connections , Any-to-any (IPVPN) networks .

+ **CONNECTING VNETs**:  
  + **S2S VPN** : LOW BANDWIDTH , VPN Gateway on both VNETS.  
  + **VNET Peering** : No Bandwidth limits, no need of Gateways.  
Traffic movement is private (**not encrypted**), therefore low latency,high bandwidth connection.  
No downtime when creating peering.  

+ **SERVICE CHAINING**  
Using UDR to control the flow of traffic . Example **Next Hop** from a VNet1 will go to **Virtual appliance** (can be a firewall) in the **peered VNet2**.
