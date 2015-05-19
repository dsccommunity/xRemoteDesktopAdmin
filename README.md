[![Build status](https://ci.appveyor.com/api/projects/status/iwctay9q3t2c72r8/branch/master?svg=true)](https://ci.appveyor.com/project/PowerShell/xremotedesktopadmin/branch/master)

# xRemoteDesktopAdmin

The **xRemoteDesktopAdmin** module contains the **xRemoteDesktopAdmin** DSC resource for configuring remote desktop settings and the Windows firewall on a local or remote machine.

## Contributing
Please check out common DSC Resources [contributing guidelines](https://github.com/PowerShell/DscResource.Kit/blob/master/CONTRIBUTING.md).


## Description

The **xRemoteDesktopAdmin** module contains the **xRemoteDesktopAdmin** DSC Resource. 
This DSC Resource allows you to configure remote desktop settings to either allow or prevent users to setup a remote desktop connection to a specific machine. 
In addition, it can optionally leverage the xPSDesiredStateConfiguration resources **xFirewall** and **xGroup**.
This allows you to configure remote desktop settings and create the necessary firewall rules to allow a remote session and add a domain user to the local Remote Desktop Users group.


## Resources

### xRemoteDesktopAdmin

* **Ensure**: Enables or disables “remote connections to this computer”.
* **UserAuthentication**: Enables or disables “Network Level Authentication”. Valid values are:
  * Secure
  * NonSecure


## Versions

### 1.0.2.0

* Update to correct issue in Set-TargetResource when checking Ensure 

### 1.0.0.0

* Initial release with the following resources 
    * xRemoteDesktopAdmin


## Examples

### ExampleConfiguration-RemoteDesktopAdmin.ps1

This configuration configures the target system to allow for remote connections (allowing a RDP session being setup), enables Network Level Authentication and creates a Windows firewall rule to allow incoming RDP traffic.

### ExampleConfiguration-RemoteDesktopAdminWithUnEncryptedPassword.ps1

This configuration extends the previous configuration by adding a domain user to the local Remote Desktop Users group using a credential stored in clear text (for testing purposes only).

### ExampleConfiguration-RemoteDesktopAdminWithEncryptedPassword.ps1

This configuration extends the previous configuration by adding a domain user to the local Remote Desktop Users group using certificates to encrypt credentials.
