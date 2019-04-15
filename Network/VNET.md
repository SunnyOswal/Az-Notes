**VNET**  
Cannot span subscriptions. Therfore you have to **connect VNets to enable communication between resources in different subscriptions**.  
+ **SUBNET**  
AZ reserves 5 Host IP's for internal use.  
`4 at the beginning of subnet range and 1 at the end`  
Therefore x.x.x.x/29 will be the smallest subnet possible in AZ VNET.

**Connecting VNETs**:  
+ **S2S VPN** : LOW BANDWIDTH , VPN Gateway on both VNETS.  
+ **VNET Peering** : No Bandwidth limits, no need of Gateways.  
Traffic movement is private (**not encrypted**), therefore low latency,high bandwidth connection.  
No downtime when creating peering.
