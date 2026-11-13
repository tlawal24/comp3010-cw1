# Wireshark filters and steps

| Filter / step | What it shows | Supports finding |
|---|---|---|
| `ip.addr == 192.168.1.96 && dns` | DNS lookups made by the host, including `matied.com` | Host behaviour before the download |
| `http.request` | HTTP requests from the host, including `GET /gerv.gun` | Payload download |
| `ip.addr == 119.28.70.207` | All traffic to and from the suspected server | Scope of the connection |
| Follow TCP Stream (`tcp.stream eq 0`) | Full request, response headers and `MZ` header | Executable download |
| Statistics > Conversations | Ethernet, IPv4, TCP and UDP conversations | Endpoint MAC and capture scale |
| `llmnr \|\| nbns \|\| dhcp` | Hostname evidence | TODO: run and record |
| File > Export Objects > HTTP | Extract `gerv.gun` for hashing | TODO: run and record |
