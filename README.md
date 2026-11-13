# COMP3010 CW1: Network Forensic Evidence

Evidence repository supporting my investigation report on `COMP3010CW1.pcap`.

## Case summary
| Item | Value | Evidence |
|---|---|---|
| Compromised host IP | 192.168.1.96 | `evidence/01-host-identification/02-frame1-dns-query-mac-ip.png` |
| Host MAC | 00:15:c5:de:c7:3b (Dell) | same as above |
| Hostname | FlashGordon-PC | TODO: add evidence (NBNS / LLMNR / DHCP) |
| Suspicious download | `GET /gerv.gun` from `matied[.]com` (119[.]28[.]70[.]207) | `evidence/02-dns-and-download/01-follow-tcp-stream-gerv-gun-mz-header.png` |
| Time of download | 27 Jun 2017 13:38:33 GMT | HTTP `Date` header, same screenshot |
| Payload | 241,664 bytes, `application/octet-stream`, begins with `MZ` (Windows executable) | same screenshot |
| Malware family | Pushdo (per IDS alerts) | TODO: add Snort/Suricata alert evidence + hash validation |

## Analysis environment
- Ubuntu VM on VMware (`evidence/04-environment/`)
- Wireshark for packet analysis; Snort and Suricata for IDS alerts
- The PCAP was analysed offline

## How to reproduce
See `filters.md` for every Wireshark filter and what it shows. SHA256 of the PCAP is in `hashes.txt`.

## Files
- `filters.md`: filters and steps used
- `iocs.md`: indicators (defanged)
- `hashes.txt`: file hashes
- `ai-use-log.md`: AI use log

> The PCAP and any extracted malware samples are not included in this repository.
