# Linux

## Services

### 1. Systemctl basics commands

- To run a service : `systemctl start [service_name]`
- To restart a service : `systemctl restart [service_name]`
- To stop a service : `systemctl stop [service_name]`
- To reload a service : `systemctl reload [service_name]`

Restart a service means stop and start again while reload a service means reload the configuration while the service is still running.

- To enable a service during the booting phase : `systemctl enable [service_name]`
- To disable a service during the booting phase : `systemctl disable [service_name]`

### 2. Journalisation

- To display the service logs : `journalctl -u [service_name]`

### 3. Task management with cron rules

The syntax to periodize a script : `0 0 * * *` _/path/to/script.sh_

- To open the cron editor : `crontab -e`
- To display the actual crontab : `crontab -l`
