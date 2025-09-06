# My Zabbix Templates

A small collection of Zabbix templates I maintain/use.

## Templates
- **See the sub folders in this repository**

## Quick start (generic)
1. Download the template YAML you need from the folder above.
2. In Zabbix, go to **Data collection → Templates → Import** and import the YAML.
3. Link the template to a host (usually no interface is required for HTTP-agent based templates).
4. Adjust macros (connection/auth, thresholds) as needed.
5. Run the template’s discovery rules (**Execute now**) to populate items faster.

## Feedback / Issues
Open an issue or discussion at: **https://github.com/snis/ZabbixTemplates**

## License
MIT (unless stated otherwise in a template folder).

— @snis

