# Logs Notes (Week 1)

## journalctl quick commands
- `journalctl -xe`
- `journalctl -u <service> --no-pager | tail -n 50`
- `journalctl --since "today"`
- `journalctl -p err..alert`
- `journalctl -u <service> --since "1 hour ago" --no-pager`

## /var/log common files (varies by distro)
- auth/security logs
- system logs
- kernel logs
- application/service logs

## Troubleshooting workflow
1. Identify the failing component
2. Check status: `systemctl status <service>`
3. Pull logs: `journalctl -u <service>`
4. Filter by time window
5. Capture error + context (5–10 lines)
6. Apply fix
7. Restart and verify

## Notes
- Logs are evidence—save the exact error line and nearby context.
