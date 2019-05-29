ContinuousMove Vuln of Axis 5514 Camera 

This page show the details of the vulnerability found in AXIS 5514 Camera. I found AXIX-P5514 were not on sale now, but maybe some of them are still in use. 


Description

Attacker can remotely make Axis 5514 camera turn around on Pan&Tilt without permission by a customized message. In order to customize and inject attacking messages, a PoC with C++ Language was developed to modify captured request messages with function “ContinuousMove” in <Soap:Body> under the ONVIF specification and then send the modified message to the AXIS-P5514 camera in real networks. The real message was captured on line by Wireshark. And I got the SOAP packets from client to the  AXIS-P5514 camera, and filter out the authentication information in SOAP head. Such as: <wsse:UsernameToken><wsse:Username> username </wsse:Username><wsse:Password Type="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0#PasswordDigest">keys</wsse:Password><wsse:Nonce>8eVIq85lxOn5IcBPVdiyvQ==</wsse:Nonce><wsu:Created>20XX-03-12T09:12:15Z</wsu:Created></wsse:UsernameToken>. After capturing such packets, use the authentication information above to customize a message with function “ContinuousMove” in <Soap:Body> and then send the modified message to the AXIS-P5514 camera. Then the Axis 5514 camera can continually move on Pan&Tilt. 



References

https://www.axis.com/products/axis-p5514-e
