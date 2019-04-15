+ **SUBNET**  
AZ reserves 5 Host IP's for internal use.  
`4 at the beginning of subnet range and 1 at the end`  
Therefore x.x.x.x/29 will be the smallest subnet possible in AZ VNET.

+ **PEERING**  
Traffic movement is private, therefore low latency,high bandwidth connection.  
No downtime when creating peering.
