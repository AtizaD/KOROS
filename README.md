# KOROS

KOROS (Keeper Of Remote Operating Systems) is a lightweight Python tool for managing and monitoring your VPS instances efficiently. It provides simple interfaces for resource monitoring, SSH management, and service control.

## Key Features

- Monitor VPS resources (CPU, RAM, disk usage)
- Manage SSH keys and access
- Control system services
- Track resource usage history
- Simple Python API

## Installation

```bash
git clone https://github.com/AtizaD/KOROS.git
cd KOROS
pip install -r requirements.txt
```

## Quick Usage

```python
from koros.vps_manager import VPSManager

# Connect to your VPS
vps = VPSManager(
    host='your.vps.ip',
    username='your_username',
    key_filename='path/to/key'  # or use password
)

# Get system stats
if vps.connect():
    stats = vps.get_system_stats()
    print(stats)
```

## Monitor Resources

```python
from koros.resource_monitor import ResourceMonitor

monitor = ResourceMonitor(vps)
current_stats = monitor.collect_metrics()
history = monitor.get_history(hours=24)
```

## Manage SSH Keys

```python
from koros.ssh_manager import SSHManager

ssh = SSHManager(vps)
ssh.add_ssh_key('ssh-rsa AAAA...')
keys = ssh.list_ssh_keys()
```

## Requirements

- Python 3.8+
- paramiko
- psutil
- Root/sudo access on VPS

## Development

Run tests:
```bash
pytest tests/
```

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/xyz`)
3. Commit changes (`git commit -am 'Add xyz'`)
4. Push branch (`git push origin feature/xyz`)
5. Create Pull Request

## License

MIT License

## Support

- Open an issue
- Submit a pull request
- Check documentation in `docs/`

---
Made by AtizaD
