# Changelog

## Version 2023032301

* fixing an issue where the script continues to run when sudo permission check fails
* adding SUSE Kernel check for SLES 15 SP2 and SP4 causing kernel panic (Mellanox driver issue)
* adding text searchable for GUI resource group

## Version 2023032201

* fixing an issue with ANF volumes when mounted using DNS names instead of IP addresses
* changing the way how ANF volume names are detected
* moving from ANF volume name to ANF creation token which is the export path, volume name and export path can be different
* adding execution date and time to the beginning of the report
* fixing an issue where MultiRun wouldn't run
* fixing a typo in load balancer
* fixing an issue where checks were executed even if they are not desired for this system (HA/non-HA issue)
* fixing a typo for Oracle in GUI (Oracle/ORACLE)

## Version 2022082301

* adding support for M420ixs_v2 and M832ixs_v2 (limited GA)
* adding support for Da(d)s_v5 and Ea(d)s_v5
* fix: script not stopping when not able to logon to VM
* fix: checking if global.ini exists (option -SID) and adding fallback path
* fix: /hana/data not checking for LVM or /dev/sd device like with /hana/log

## Version 2022072701

* adding automatic detection for fencing machanism based on configured SBD_DEVICE, if no device configured then it is Fencing Agent

## Version 2022072601

* adding SID parameter
* based on SID the script will autodetect which file systems are used by HANA database

## Version 2022072101

* fixing issue where links to Microsoft documentation are missing
* fixing issue with LoginWithUserSSHKey, specifying a dummy password

## Version 2022072001

* adding Logon option -UserSSHKey for users that don't require a password, just the SSH key

## Version 2022071302

* adding support to run multiple quality checks in one run, only supported with user/password authentication as of now

## Version 2022071301

* adding check for supported storage configuration on HANA Data and HANA Log

## Version 2022071202

* adding first version of GUI option with user/password authentication
* adding description for accelerated networking VMs with only one NIC allowed for accelerated networking

## Version 2022071201

* fixing SSH Key logon issues

## Version 2022070702

* adding runtime log to HTML file
* formating of log output

## Version 2022070701

* adding parameters to HTML output
* fixing an issue with RunLocally and post processing commands
* adding storage disk types to script incl performance values for RunLocally command to calculate performance and throughput
* adding internal values in JSON output for RunLocally

## Version 2022070601

* fixing issue with OS disk not part of a VG

## Version 2022070301

* add and update SAP note 3024346, HANA with Azure NetApp Files
* add RunInLocalMode option in JSON file
* moving version history from readme.md to JSON file
* updating parameters for PowerShell script to use ParameterSets
* enabling SSH keys for different combinations incl Azure Key Vault
* add runlocally to run the script on the system itself without outside connectivity to Azure, requires PowerShell to be installed on the system and needs to run as root user
* add options for GUI, will be implemented in a future release
* removing required PowerShell modules from #requires section to be able to run in RunInLocalMode, module requirements are checked within the code

## Version 2022070101

* hotfix for OSdisk VG identification
* changing information collection sg_map to lsscsi

## Version 2022062302

* fixing a typo for HANA SLES Fencing Agent configuration

## Version 2022062301

* fixing an issue with root and resource disk causing the script not to find the correct LUN ID for data disks

## Version 2022050901

* fixing parameters

## Version 2022042501

* fixing issue when customers don't have sg3_utils installed, moving to lsscsi instead of sg_map
* adding exception handling for disks that are not used, just attached
* fixing an issue where Db2 OS/DB combination wasn't working

## Version 2022041301

* adding a check if sg_map is installed

## Version 2022041102

* adding case sensitivity to parameters

## Version 2022041101

* adding sudo check
* adding version check

## Version 2022022301

* changing naming to "Quality Check for SAP workloads on Azure"

## Version 2022022201

* adding HANA support for E(d)s_v5 instances

## Version 2022021801

* fixing concurrent fencing for SLES, thanks to @1lomeno3

## Version 2022021101

* fixing issue where passwords start with a special character

## Version 2022021002

* moving to absolute paths for all executables

## Version 2022021001

* fixing an issue when PATH doesn't include e.g. the lvm command
* fixing an issue when using root user (no sudo required)

## Version 2022020301

* fixing an issue for sudo command that don't get the environment variables
* fixing a potential issue for not finding the correct disk

## Version 2022013002

* fixing an issue for tcp_retries1 (thanks @iklema)
* APP-OS-0005 only applies to SLES 12.3 as newer versions have kernel 4.12 (thanks @iklema)
* updaing systemctl to 'systemctl list-unit-files --state=enabled' (thanks @iklema)

## Version 2022013001

* adding script version to footer
* adding more checks to analyze storage errors
* updating storage API version call

## Version 2022012701

* fixing display issue for disks showing in stripe size check

## Version 2022012601

* fixing issue for /dev/sda not being rootvg

## Version 2022012401

* fixing IC checks for APP and ASCS servers

## Version 2022012101

* fixing a typo in fence_kdump check
* fixing a case there LVM is used on partitions instead of full disk (e.g. /dev/sdc1 instead of /dev/sdc)
* fixing IOPS check, only applies for Ultra Disk

## Version 2022011903

* adding softdog checks for SLES/SBD

## Version 2022011902

* adding fence_kdump as optional check

## Version 2022011901

* adding info and warning as errorcatory in json and ps1

## Version 2022011801

* adding ASCS HA checks

## Version 2022011101

* fixing description for CPU softlockup check HDB-OS-SLES-0005

## Version 2022011001

* added support for HANA multi disk scenario
* added support for /dev/sdX devices instead of LVM
* added section at the end for copy/paste data for further internal analysis
* added support for D(d)sv4 and E(d)sdv5
* added version number to script and json and compare values when script starts
* added error handling for SSH connectivity in case VM is down
* added the HDB-FS file system checks to documentation
* fixed a RedHat Cluster information collection command

## Version 2022010401

* Initial V2 version
* support for DB, ASCS and app servers
* HTML output for better user expierience
* every check has a unique check id
* updated check engine with more granular view (e.g. adding support for special OS releases)
* documented all checks on GitHub
* data collection engine to get better overview of system
* added support for Db2 and Oracle
* added support for Oracle Linux
* new kernel check function
* foundation for adding Windows support in the future
