Role Name
=========

This role will install Kong, onto a Redhat or Debian based operating system

Requirements
------------

No requirments

Role Variables
--------------

|Variable|Description|Default|
|--|--|--|--|
|`kong_package_url`|The URL to install the Kong package from|[url](https://download.konghq.com/gateway-2.x-centos-8/Packages/k/kong-enterprise-edition-2.4.1.0.el8.noarch.rpm)|
|`kong_table_count`|When this value equals 0 and the target role is not a data
 plane the database bootstrap script is called | none |
|`deck_rpm_url`|The URL to install the Kong DecK package from|[url](https://github.com/Kong/deck/releases/download/v1.6.0/deck_v1.6.0_amd64.rpm)|
|`license_data`|The string content of the Kong license file|-|

All the remaining variables are described in the [kong configuration property reference](https://docs.konghq.com/enterprise/2.4.x/property-reference/).

Example Playbook

----------------

```yaml
    - hosts: data_planes 
      roles:
         - { role: srb3.ansible-role-kong_enterprise, role: "data_plane" }
```

License
-------

MIT
