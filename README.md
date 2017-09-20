## Intro

Tool to parse the output of clagctl (cumuluslinux mlag implementation)
into Prometheus text-file format.

The number returned for each metric correspond to the number of 
interfaces present inside the portchannel.

```console
  cumulus:~$ python clagctl_parser.py

  # HELP clag_interfaces_count (0=absent on both peers, 1=single connected, 2=dual connected)
  # TYPE clag_interfaces_count gauge
  clag_interface_count{name="storage02"} 2
  clag_interface_count{name="storage03"} 2
  clag_interface_count{name="storage01"} 2
  clag_interface_count{name="storage04"} 2
  clag_interface_count{name="compute02"} 2
  clag_interface_count{name="compute03"} 2
  clag_interface_count{name="compute01"} 2
  clag_interface_count{name="compute06"} 2
  clag_interface_count{name="compute07"} 2
  clag_interface_count{name="compute04"} 2
  clag_interface_count{name="compute05"} 2
  clag_interface_count{name="compute08"} 2
  clag_interface_count{name="compute09"} 2
  # HELP clag_peer_status (0=Peer absent, 1=Peer connected)
  # TYPE clag_peer_status gauge
  clag_peer_status 1
  # HELP clag_peer_backup_active
  # TYPE clag_peer_backup_active gauge
  clag_peer_backup_active 1
  # HELP clag_peer_our_role (1=primary, 2=secondary)
  # TYPE clag_peer_our_role gauge
  clag_peer_our_role 2
  # HELP clag_peer_peer_role (1=primary, 2=secondary)
  # TYPE clag_peer_peer_role gauge
  clag_peer_peer_role 1
```

## Usage

`$ clagctl_parser.py
