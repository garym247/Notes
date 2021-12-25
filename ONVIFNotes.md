The are two types of ONVIF authentication:

* WS-UsernameToken
    * SOAP message level authentication.
    * Reliant on time-sync between devices and client.
* HTTP Digest
    * HTTP transport level authentication.
    * Not reliant on time-sync between devices and client.

Authentication requirements for the ONVIF Profile S specification are specified as follows:


<table>
  <tr>
   <td><strong>Authentication Scheme</strong>
   </td>
   <td><strong>Device</strong>
   </td>
   <td><strong>Client</strong>
   </td>
  </tr>
  <tr>
   <td>WS-UsernameToken
   </td>
   <td>Mandatory
   </td>
   <td>Mandatory
   </td>
  </tr>
  <tr>
   <td>HTTP Digest
   </td>
   <td>Optional
   </td>
   <td>Mandatory
   </td>
  </tr>
</table>



<table>
  <tr>
   <td><strong>ONVIF Profile</strong>
   </td>
   <td><strong>Features</strong>
   </td>
  </tr>
  <tr>
   <td>G
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>Q
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>S
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>T
   </td>
   <td>H.265
   </td>
  </tr>
  <tr>
   <td>C
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td>A
   </td>
   <td>
   </td>
  </tr>
</table>


Features for each profile can be mandatory, conditional or optional.
