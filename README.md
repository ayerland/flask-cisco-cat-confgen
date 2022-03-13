# flask-cisco-cat-confgen

Simple Flask Web App: generate a Cisco IOS config from a config template

How does this work?
Fill out the Web App form with some basic switch configuration information, and that will
generate a config to copy paste into the switch. The output will be based on a template config file 
located under: templates/cisco_cat_ios_15

The concept applies to when wanting to generate any type of config file from a template.
For illustration purposes and to keep it simple, this sample web app only handles one template. 

The following variables "##variable##" in the template file, are replaced the the variables in the web form
when generating the output.


```
hostname ##hostname##
vlan ##mgmt_vlan##
vlan ##voip_vlan##
vlan ##general_vlan##
vlan ##auth_vlan##
switchport access vlan ##general_vlan##
switchport voice vlan ##voip_vlan##
interface Vlan##mgmt_vlan##
ip address ##ip_add## ##mask_add##
ip default-gateway ##gw_add##
snmp-server location ##location##
```


## Screenshot Sample
<p align="center">
<img src="https://github.com/ayerland/flask-cisco-cat-confgen/blob/master/static/demo-image.png" width="400" />


## Prerequisites
```
git

pipenv
```


## How-To 

```
$ pipenv install

$ pipenv shell


$ flask run                                                                
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)

```

## Demo

https://flask-cisco-cat-confgen.herokuapp.com


