# Zabbix template for Nanoleaf devices

<br />
<div align="center">
    <img src="https://raw.githubusercontent.com/amacado/zabbix-template-nanoleaf/main/docs/images/zabbix_logo.png" alt="Zabbix Server" height="60" />
    <img src="https://raw.githubusercontent.com/amacado/zabbix-template-nanoleaf/main/docs/images/nanoleaf_logo.png" alt="Nanoleaf®" height="60" />
</div>

## About
This template allows to retrieve data from a Nanoleaf device and use it for monitoring in a Zabbix environment.

## Usage
### Setup
1. Import the [`zabbix-template-nanoleaf.yaml`](/zabbix-template-nanoleaf.yaml) template into your Zabbix server (see [zabbix.com/documentation](https://www.zabbix.com/documentation/current/en/manual/xml_export_import/templates#importing)
2. Create a new `Host` (without interfaces) and assign the imported `Nanoleaf` template (see [zabbix.com/documentation](https://www.zabbix.com/documentation/6.0/en/manual/quickstart/host?hl=host%2CCreate%2Chost.)
3. Modify the Host `Macros` to your needs
    1. `{$NANOLEAF_HOST}` Enter the IP/Hostname of your Nanoleaf device
    2. `{$NANOLEAF_PORT}` Enter the port of the REST API by your Nanoleaf device (default 16021)
    3. `{$NANOLEAF_TOKEN}` Enter the generated auth token for the REST API (see [Nanoleaf REST API documentation](https://documenter.getpostman.com/view/1559645/RW1gEcCH#0fe71046-6a4b-46b7-ab05-9ea648b06c89)
    ```
    curl --location --request POST 'http://{$NANOLEAF_HOST}:{$NANOLEAF_PORT}/api/v1/new'
    ```
    4. (Optional) Enable/Disable triggers to your needs
