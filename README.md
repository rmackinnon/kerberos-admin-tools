kerberos-admin-tools
====================

Collection of Bash scripts to ease administration of a Kerberos v5 realm on a KDC. The following files help with the creation of users, hosts, and services. It expects the following:

Predefined Policies: user, host, host_MS, service

Usage
=====
```
kaddprinc <principal> ["<options>"]
```
Runs kadmin.local with command "addprinc \[\<options\>] \<principal\>"
```
kaddkeytab <principal> <keytabFile>
```
Runs kadmin.local with command "ktadd -k \<keytabFile\> \<principal\>"
```
kadduser <principal> [<keytabFile>]
```
Scripted process to create a user with defined principal with the policy "user". Optionally writes user credentials to keytab file if defined. 
```
kaddhost <fqdn> [<keytabFile>]
```
Scripted process to create hostname iterations principals with the policy "host".  Optionally adds keys to a keytab file if defined.
```
kaddhostsrv <service> <fqdn> [<keytabFile>]
```
Scripted process to create hostname iterations principals for the defined service (e.g. cifs, nfs, imap, etc.) with the policy "host".  Optionally adds keys to a keytab file if defined.
```
kaddmshost <fqdn> [<keytabFile>]
```
Similar to ''kaddhost'', but defines the policy as "host_MS" and performs a user defined password after creation of principal.
```
kaddmshostsrv <service> <principal> [<keytabFile>]
```
Similar to ''kaddhostsrv'', but performs a user defined password after creation of principal. 
```
kaddlocalhost <fqdn>
```
Scripted process to create hostname iterations principals with the policy "host", with the output to ''/etc/krb5.keytab''.
```
kaddlocalsrv <service> <fqdn>
```
Scripted process to create hostname iterations principals for the defined service (e.g. cifs, nfs, imap, etc.) with the policy "host", with the output to ''/etc/krb5.keytab''.
