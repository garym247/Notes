**Windows Explorer**

The following can be typed into the Windows Explorer folder bar:


<table>
  <tr>
   <td><code>%APPDATA%</code>
   </td>
   <td>goes to your application data <code>Roaming</code> directory
   </td>
  </tr>
  <tr>
   <td><code>%LOCALAPPDATA%</code>
   </td>
   <td>goes to your application data <code>Local</code> directory
   </td>
  </tr>
  <tr>
   <td><code>cmd</code>
   </td>
   <td>to open a command prompt in the currently selected directory
   </td>
  </tr>
</table>


**UNICODE characters**

 

To get the euro symbol (€) press `Ctrl-Alt-4`.

 

Alternatively for the snowman symbol go for http://unicodesnowmanforyou.com

**To delete a partition via the command line:**

Run `diskpart` application


    rescan


    list disk


    select disk &lt;disk number>


    list partition


    select partition &lt;partition number>


    delete partition override

**To set up network drives via a .bat file**


```
net use <drive letter>: <unc path> /savecred /persistent:yes /y
```


**<span style="text-decoration:underline;">Microsoft Outlook</span>**

Ctrl-K to see a list of suggestions that match a given string pattern.

**<span style="text-decoration:underline;">Handy Tools</span>**

NEWT

clumsy

WireShark

To see what status of the ports on a PC:


```
netstat -an
```


Piping this into the find command is a handy way to find particular ports, e.g. to find ports in the listening state, `netstat -an|find /i "listening"`
