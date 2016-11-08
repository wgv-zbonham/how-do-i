### How do I Capture a Network Trace?

The great news is that since Windows Server 2008R2, we've had the ability to capture network traces without any additional tools or utilities.  Sure.  You could install Wireshark if thats your thing.  However, if your on a customer site, or in a production environment, and you don't want to slow down/stop to ask for permission, you can reach for ```netsh```.

```netsh``` [does many things](https://technet.microsoft.com/en-us/library/bb490939.aspx).  We are interested in its ability to capture network traffic.

From an **administrator** command prompt:

```
netsh trace start capture=yes tracefile=c:\watchguardvideo\logs\network.etl

Trace configuration:
-------------------------------------------------------------------
Status:             Running
Trace File:         C:\watchguardvideo\logs\network.etl
Append:             Off
Circular:           On
Max Size:           250 MB
Report:             Off
```

That's it.  Now you've got a 250MB circular buffer of an opportunity to go reproduce the behavior.  

When your ready to stop your trace:

```
netsh trace stop

Correlating traces ... done
Merging traces ... done
Generating data collection ... done
The trace file and additional troubleshooting information have been compiled as "c:\watchguardvideo\logs\network.cab".
File location = c:\watchguardvideo\logs\network.etl
Tracing session was successfully stopped.

```

This may take a minute or so.  That's OK. 





## References

* https://blogs.msdn.microsoft.com/canberrapfe/2012/03/30/capture-a-network-trace-without-installing-anything-capture-a-network-trace-of-a-reboot/
