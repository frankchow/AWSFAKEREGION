# AWSFAKEREGION
AWS fake region for migration region-2-region testing

### Project Overview

[Overall Project status checking] (https://www.trello.com)

Major milestone| Date | Status | Remark
--- | --- | --- | ---
*Project Start* | 2017-Dec | |
*Implementation* | 2017-Dec-12 | On progress |
*Testing & Validation* | 2017-Dec |  |
*Documentation* | 2018-Jan |  |
*Project End* | 2017-Sept-21 |  |

All are setup on Seoul region.

### Outstanding questions:  
Questions| Recorded Date | Followed by | Status
--- | --- | --- | ---
Bra Bra Bra | 2017-Dec-?? |  | XXXX
Bra Bra Bra | 2017-Dec-?? |  | XXXX

### Implementation reminders:

### Cloudformation templates used:
REHL& ami=ami-0f5a8361
Windows 2012 R2 ami=ami-231cbb4d
Windows 2016 ami=ami-e8ef4986

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/base_network.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/securitygroup.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/windows_2016_autorecovery.template
ARInstanceName=bastion
AppSubnet=PublicAZ1
ARInstanceSecurityGroupList=PublicRDPSecurityGroup
Imageid=ami-e8ef4986
InstanceType=t2.small
Keyname=faskeawsregion  

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/rhel_7_autorecovery.template
ARInstanceName=web1
AppSubnet=PrivateAz1
ARInstanceSecurityGroupList=PrivateWebSecurityGroup
Imageid=ami-0f5a8361

ARInstanceName=web2
AppSubnet=PrivateAz2
ARInstanceSecurityGroupList=PrivateWebSecurityGroup
Imageid=ami-0f5a8361

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/CLB.template
Subnets=PublicAZ1,PublicAZ2
SecurityGroups=PublicWebSecurityGroup
LoadBalancerName=extclb
ASGTargets=false
Instances=i-05cb3e650626a5f1a,i-04d645cad94c848e3

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/efs.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/elasticache_memcached.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/iam_policy.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/iam_role.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/maintenance_window_runcommand_task.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/patch_baseline_rhel.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/patch_baseline_windows.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/s3.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/systems_manager_service_role.template

https://s3.ap-northeast-2.amazonaws.com/awsfakeregion/cf/windows_2012R2_autorecovery.template
