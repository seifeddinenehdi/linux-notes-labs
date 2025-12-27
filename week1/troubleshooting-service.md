# Troubleshooting: Service won’t start (Week 1)

## Goal
Document a real troubleshooting flow using `systemctl` + logs.

## Scenario
A Linux service fails to start after a reboot or configuration change.

## Step 1 — Check service status
Command:
- `systemctl status <service>`

What I look for:
- service state (failed/inactive)
- error message lines
- config file path
- last start timestamp

## Step 2 — Review logs
Commands:
- `journalctl -xe`
- `journalctl -u <service> --no-pager | tail -n 50`

What I look for:
- permission denied
- missing file/directory
- invalid configuration syntax
- port already in use
- dependency failures

## Step 3 — Validate config and permissions
Checklist:
- confirm config file exists and path is correct
- verify permissions on config and related directories
- confirm the service user has access
- verify required ports are free: `ss -tulpn`

## Step 4 — Restart and verify
Commands:
- `systemctl restart <service>`
- `systemctl status <service>`

## Example (ssh)
- status: `systemctl status ssh`
- logs: `journalctl -u ssh --no-pager | tail -n 50`

## Result (fill in when you do a real lab)
- Root cause:
- Fix:
- Prevention:
