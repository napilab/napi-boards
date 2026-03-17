# Example: CAN Bus (SocketCAN) on NAPI2

## Prerequisites

1. Enable CAN overlay:
   ```
   overlays=rk3568-napi2-can0
   ```
2. Reboot
3. Verify: `ip link show can0`

## Bring Up CAN Interface

```bash
# Set bitrate and bring up
ip link set can0 type can bitrate 500000
ip link set can0 up

# Check status
ip -details link show can0
```

## Send and Receive Frames

```bash
# Install can-utils
apt install can-utils

# Receive (terminal 1)
candump can0

# Send (terminal 2)
cansend can0 123#DEADBEEF
```

## Python Example

```python
import socket
import struct

CAN_FORMAT = "<IB3x8s"
CAN_INTERFACE = "can0"

sock = socket.socket(socket.AF_CAN, socket.SOCK_RAW, socket.CAN_RAW)
sock.bind((CAN_INTERFACE,))

# Send frame: ID=0x123, data=0xDEADBEEF
can_id = 0x123
data = bytes([0xDE, 0xAD, 0xBE, 0xEF])
frame = struct.pack(CAN_FORMAT, can_id, len(data), data.ljust(8, b'\x00'))
sock.send(frame)

# Receive
raw = sock.recv(16)
can_id, dlc, data = struct.unpack(CAN_FORMAT, raw)
print(f"ID: {can_id:#x}  Data: {data[:dlc].hex()}")
```
