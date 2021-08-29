## Usage

Run the command
```
python3 index.py <website>
```

For Example
```
python index.py www.facebook 
```
You get this output

```
Client Hello Begin
	 Host www.facebook.com
	 Port 443
	 Client random 61:2B:85:F7:5B:29:F1:8D:B1:6B:C4:EA:50:91:42:DD:31:E3:AB:38:FD:61:44:FF:85:28:45:3B:65:9E:81:72
	 Cipher suite suggested ECDHE-ECDSA-AES256-GCM-SHA384, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-RSA-AES256-SHA384, ECDHE-RSA-AES256-SHA, AES256-GCM-SHA384, AES256-SHA256, AES256-SHA, AES128-SHA
Client Hello End
Server Hello Begin
	 Cipher suite negotiated  ECDHE-ECDSA-AES256-GCM-SHA384(C0:2C)
	 TLS version TLSV1.2
	 Server random E4:D3:5C:56:5D:EE:16:B4:11:6C:8C:0C:33:7D:F5:36:13:62:AA:25:D3:DA:71:14:45:9C:6A:2D:C5:02:F0:3C
	 Key exchange ECDH
	 Server cert not before (UTC) 2021-07-20 00:00:00
	 Server cert not after (UTC) 2021-10-18 23:59:59
	 Server cert fingerprint (sha256) B2:B5:52:9A:3C:08:2C:5E:9B:A1:C1:25:5E:5F:FB:B9:8F:36:FE:9A:94:87:CC:9A:C6:14:19:8C:FF:91:41:AC
	 Key Exchange Server Public Key (65 bytes) 04:48:85:1F:22:E9:38:9B:E4:09:59:AE:E7:B0:60:88:BE:9A:09:4C:66:7C:35:FA:27:A2:BF:06:87:5D:78:BB:DB:0C:AB:FB:A5:E9:EF:AB:8A:6B:4D:F6:A5:C9:D2:B4:B3:61:68:F3:D1:B3:14:CF:45:2C:48:96:F6:34:44:AB:E0
Server Hello End
Client Finish Begin
	 Key Exchange Client Public Key (65 bytes) 04:8D:14:1C:DF:33:6C:BC:C7:A9:C3:12:DC:34:C7:BD:58:EC:58:AF:F0:43:3F:47:53:E5:B1:09:31:D2:4A:39:B6:E2:EB:DC:26:82:66:25:BD:87:20:32:08:2C:DC:5D:8C:EF:32:AE:2D:46:02:08:70:D3:BC:51:C7:BE:F7:B1:CB
	 Pre master secret F5:FC:6D:D6:DE:16:F9:75:4E:3F:CD:07:F2:0A:2F:19:F2:F9:26:F2:99:39:62:06:B7:53:8B:81:26:8C:5B:AA
	 Master secret C4:E5:86:66:FF:FA:DD:62:3F:FE:37:9C:7F:8A:45:8F:D4:8C:01:73:DD:C8:9F:53:74:DD:EF:F9:9F:CE:AD:21:E9:95:3F:56:6A:73:AD:95:7D:35:E0:91:D2:8F:30:30
	 Verify data B3:92:4C:B8:78:9B:91:4E:CF:E2:52:D9
Client Finish End
Server Finish Begin
	 Verify data E7:C7:6C:A6:67:55:A6:96:49:AA:61:F3
Server Finish End
Send Application Data Begin
	 Plain GET / HTTP/1.1\r\nHost: www.facebook.com\r\n\r\n
	 Encrypted 17:03:03:00:42:48:9D:2A:3E:E5:9E:D8:F1:2C:F7:53:F6:51:EB:F3:2E:05:26:C1:86:CB:7C:A6:6D:8F:0C:58:FD:8E:5F:91:F6:2C:AB:71:17:E4:5D:76:A9:E0:E7:9F:AD:12:08:3A:79:D6:F6:77:EE:31:EA:E4:E3:3F:CF:75:A3:76:B8:26:4C:5F:29
Send Application Data End
Receive Application Data Begin
Receive Application Data End
Server response  b'HTTP/1.1 302 Found\r\nLocation: https://www.facebook.com/unsupportedbrowser\r\nStrict-Transport-Security: max-age=15552000; preload\r\nContent-Type: text/html; charset="utf-8"\r\nX-FB-Debug: 5U8rs6C78i6ruj8AyC9gdPSPV0G4oyxQgnRhMHA0QjJJ65CoG6J7875b4ShkuLWdrzoD8O3FwIYDgL3WY7TU0w==\r\nDate: Sun, 29 Aug 2021 13:04:56 GMT\r\nPriority: u=3,i\r\nAlt-Svc: h3-29=":443"; ma=3600,h3-27=":443"; ma=3600\r\nConnection: keep-alive\r\nContent-Length: 0\r\n\r\n' 
```

You also get the certificate as a part of `TLS Handshake`.

1. You can specify the Cipher to use like `AES256-SHA`.
```
python3 index.py www.facebook.com -c AES256-SHA
```

You get the following output
```
Client Hello Begin
	 Host www.facebook.com
	 Port 443
	 Client random 61:2B:86:AE:84:A0:2B:FC:8E:D8:E3:E9:2A:03:86:E2:46:7C:CC:09:EB:EF:C8:43:41:41:E4:5F:92:A8:25:F7
	 Cipher suite suggested AES256-SHA
Client Hello End
Server Hello Begin
	 Cipher suite negotiated  AES256-SHA(00:35)
	 TLS version TLSV1.2
	 Server random 68:3B:C7:D9:CD:2F:31:E1:43:DD:1D:C9:6E:5B:94:15:23:C3:F0:BC:87:CB:41:A5:DC:12:48:FD:3C:0C:32:64
	 Key exchange RSA
	 Server cert not before (UTC) 2021-08-04 00:00:00
	 Server cert not after (UTC) 2021-11-02 23:59:59
	 Server cert fingerprint (sha256) A4:A9:0F:38:A1:67:98:46:25:F7:30:0A:35:73:82:CF:18:84:24:99:79:3D:B5:10:68:34:6A:97:6D:4C:62:6D
Server Hello End
Client Finish Begin
	 Encrypted pre master secret 3E:11:4B:93:FF:E9:42:B5:8E:12:D4:F4:D8:4B:0E:5F:4F:C9:4B:9D:7B:2A:55:7F:FE:F3:59:D6:88:E5:9C:11:31:E5:A6:31:2D:D0:DB:BC:71:B1:85:B4:1A:78:13:56:48:71:F1:9E:A8:19:94:E8:45:1E:7D:A3:57:74:2F:BB:76:0D:23:97:71:E0:8A:CB:8B:E8:2A:AB:51:53:06:1F:69:B7:F3:7B:DB:A9:8E:29:0B:E9:40:66:C4:BC:48:E8:39:94:34:48:CF:2C:16:38:06:B1:A7:94:7D:E7:99:A2:C6:05:42:0C:A8:35:0C:7E:80:BD:08:8F:C0:65:A4:F4:95:D0:EB:F5:09:0D:38:F8:A7:7B:83:F9:CA:F3:68:45:A5:10:3A:3D:D9:42:EE:45:5D:93:B0:1C:D7:8B:AC:88:FD:15:40:96:4A:23:D8:47:ED:DA:23:BB:3F:83:3A:E3:D2:15:CC:B4:0F:FA:CF:FE:13:EE:9C:33:30:6E:55:17:33:FC:DD:1E:02:57:76:51:67:0F:DD:D7:25:2B:E5:C5:60:B1:65:F8:0A:BE:20:6C:53:4B:2B:95:FB:E5:1E:D6:B5:4A:81:E2:81:B5:FC:7C:A6:0C:A5:CB:05:F0:5F:75:5A:33:AC:36:67:B5:4B:4E:F5:75:B8:B2:87:45:C6:A0
	 Pre master secret 03:03:26:7A:5C:10:CE:A3:AA:06:3C:14:5B:7B:24:F4:08:78:6A:F6:60:AA:87:8C:2C:D8:E7:93:E1:9A:04:0F:B3:F5:65:CB:37:D1:D5:CA:75:69:39:52:73:A7:F3:CD
	 Master secret 2B:78:C5:A9:22:35:41:B9:5A:83:FC:F2:CD:4A:4B:CB:54:1E:BC:97:DB:CF:B1:CE:35:C5:12:68:D9:10:D4:36:75:24:36:53:0F:1A:24:09:E6:B4:C7:75:C5:F9:07:00
	 Verify data 12:46:0F:48:F8:D4:3F:41:05:E8:0D:CA
Client Finish End
Server Finish Begin
	 Verify data E7:6D:FE:10:06:64:06:0B:7A:8B:76:C1
Server Finish End
Send Application Data Begin
	 Plain GET / HTTP/1.1\r\nHost: www.facebook.com\r\n\r\n
	 Encrypted 17:03:03:00:50:E5:4E:CD:F5:99:47:4B:D0:F0:EB:BE:0A:CA:E7:E3:A0:37:86:13:28:69:0D:64:CD:E3:57:10:D5:7A:A9:9D:C5:0A:E5:30:1D:48:DE:E1:6D:8F:99:2F:F5:26:DB:DF:57:3F:6E:41:9B:F9:58:4C:E0:E5:26:16:C6:FB:9C:A9:6B:9E:BC:36:58:2C:35:FB:16:DA:A3:3F:BA:CE:CC:AF:F7
Send Application Data End
Receive Application Data Begin
Receive Application Data End
Server response  b'HTTP/1.1 302 Found\r\nLocation: https://www.facebook.com/unsupportedbrowser\r\nStrict-Transport-Security: max-age=15552000; preload\r\nContent-Type: text/html; charset="utf-8"\r\nX-FB-Debug: YDV+q2/ugoN8DfF0C7kfH4wcPl3M34kTZL7bW4NPnyhf9P7kHrSYZUI94/4rocAZ4Ry7NcqYrYZQufXffZoH0Q==\r\nDate: Sun, 29 Aug 2021 13:07:58 GMT\r\nPriority: u=3,i\r\nAlt-Svc: h3-29=":443"; ma=3600,h3-27=":443"; ma=3600\r\nConnection: keep-alive\r\nContent-Length: 0\r\n\r\n' 

```