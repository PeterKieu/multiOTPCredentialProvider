multiOTPCredentialProvider
==========================
multiOTP Credential Provider for multiOTP is a free and open source implementation of a V2 Credential Provider for the multiOTP strong two-factor authentication solution (Apache License, Version 2.0)

(c) 2016-2018 SysCo systemes de communication sa (enhancements since 2016 and simple installer with configuration options)
(c) 2015-2016 ArcadeJust ("RDP only" enhancement)  
(c) 2013-2015 Last Squirrel IT  

Current build: 5.1.0.3 (2018-02-19)

Binary download: https://download.multiotp.net/credential-provider/

[![Donate via PayPal](https://img.shields.io/badge/donate-paypal-87ceeb.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&currency_code=USD&business=paypal@sysco.ch&item_name=Donation%20for%20multiOTP%20project)
*Please consider supporting this project by making a donation via [PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&currency_code=USD&business=paypal@sysco.ch&item_name=Donation%20for%20multiOTP%20project)*

Visit http://forum.multiotp.net/ for additional support.


multiOTP Credential Provider for multiOTP supporting Windows 7/8/8.1/10/2012(R2)/2016.
- supports both local and domain users
- forced OTP check for RDP
- forced or disabled check of OTP for local logons
- client executable of multiOTP is automatically installed and configured
- multiOTP Credential Provider is only activated if the authentication test is passed successfully
- DLL and EXE files are digitally signed
- the first strong two factor authentication solution that have cache support in order to work also offline!

![multiOTPCredentialProvider setup1](https://raw.githubusercontent.com/multiOTP/multiOTPCredentialProvider/master/screenshots/multiOTPCredentialProvider-setup1.png)

![multiOTPCredentialProvider setup2](https://raw.githubusercontent.com/multiOTP/multiOTPCredentialProvider/master/screenshots/multiOTPCredentialProvider-setup2.png)

![multiOTPCredentialProvider test](https://raw.githubusercontent.com/multiOTP/multiOTPCredentialProvider/master/screenshots/multiOTPCredentialProvider-test.png)

![multiOTPCredentialProvider login](https://raw.githubusercontent.com/multiOTP/multiOTPCredentialProvider/master/screenshots/multiOTPCredentialProvider-login.png)


PREREQUISITES
=============
- installed multiOTP server(s)
- configured multiOTP user (multiOTP username = [domain user name] or [windows local account name] or [microsoft account name])


INSTALLATION
============
- Launch the installer (in the installer directory) and configure the various parameters during the detup. You must have administrator access.


UNINSTALLATION
==============
- Uninstall the multiOTP Credential Provider using the regular uninstallation procedure, or launch the file multiOTPCredentialProvider-unregister.reg (you must have administrator access).


TECHNICAL DETAILS
=================
- the credential provider DLL (multiOTPCredentialProvider.dll) is installed in the system folder \Windows\System32
- the credential provider options are stored in the following registry key : HKEY_CLASSES_ROOT\CLSID\{FCEFDFAB-B0A1-4C4D-8B2B-4FF4E0A3D978}
  - multiOTPCacheEnabled : [1|0]
  - multiOTPDisplaySmsLink : [0|1]
  - multiOTPLoginTitle : [Login title, default is '', which displays multiOTP Login]
  - multiOTPOptions : [configuration options used directly by multiOTP, tab separated, default is '']
  - multiOTPPath : [X:\Path\to\multiotp\folder]
  - multiOTPPrefixPass : [0|1]
  - multiOTPRDPOnly : [0|1]
  - multiOTPServers : [multiOTP server(s) to contact, default is 'https://192.168.1.88']
  - multiOTPServerTimeout : [timeout in seconds before switching to the next server, default is 5]
  - multiOTPSharedSecret : [secret to connect this client to the server, default is 'ClientServerSecret']
  - multiOTPTimeout : [timeout in seconds, default is 10]
  - multiOTPUPNFormat : [0|1]
- the multiOTP options are also stored in the file [multiOTPPath]\config\multiotp.ini, but registry has the priority
- if the tile file [multiOTPPath]\multiotp.bmp exists, it will replace the default 128x128 tile image


THANKS TO
=========
- ArcadeJust ("RDP only" enhancement)
- LastSquirrelIT (initial implementation)


Report if you have any problems or questions regarding this app.


CHANGE LOG OF RELEASED VERSIONS
===============================
```
2018-02-19 5.1.0.3 SysCo/al Setup wizard has one more page for better layout
                            Options stored in the multiOTPOptions registry are read and have more priorities than config file
                            Login title can be customized using the multiOTPLoginTitle registry
                            Tile image can be customized by saving a 128x128 bmp in the file [multiOTPPath]\multiotp.bmp
2017-12-11 5.0.6.2 SysCo/al [Receive an OTP by SMS] link can be displayed or not (option during installation)
                            UPN username format can be sent to the multiOTP server (by default, legacy username)
                            Better documentation
2017-12-04 5.0.6.1 SysCo/al Default domain name support
                            User can request an SMS code using a command link
                            [Synchronize OTP] link removed (useless, synchronization is done automatically by typing OTP1 + [space] + OTP2)
2017-11-10 5.0.6.0 SysCo/al Specific Credential Provider mode in the CLI version
2017-11-05 5.0.5.9 SysCo/al Full support for login@domain.name UPN notation (AD/LDAP should be synchronized using the userPrincipalName instead of sAMAccountName identifier)
2017-11-04 5.0.5.6 SysCo/al Removed digit OTP only check for the OTP field
                            Friendly name of the second factor field renamed from PIN to OTP
2017-06-02 5.0.4.6 SysCo/al Fixed default folder detection for the multiotp.exe file
2016-11-04 5.0.2.6 SysCo/al First public release with an installer, based on hard work done by Last Squirrel IT and ArcadeJust
```
