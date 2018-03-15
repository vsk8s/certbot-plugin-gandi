# Certbot plugin for authentication using Gandi LiveDNS

This is a plugin for [Certbot](https://certbot.eff.org/) that uses the Gandi
LiveDNS API to allow [Gandi](https://www.gandi.net/)
customers to prove control of a domain name.

1. Obtain a Gandi API token (see [Gandi LiveDNS API](https://doc.livedns.gandi.net/))
 
2. Install the plugin:
   ```
   pip install 'git+https://gitlab.com/cspublic/certbot-plugin-gandi.git'
   ```

3. Create a `gandi.ini` config file with the following contents:
   ```
   certbot_plugin_gandi:dns_api_key=APIKEY
   ```
   Replace `APIKEY` with your Gandi API key and ensure permissions are set
   to disallow access to other users.

4. Run `certbot` and direct it to use the plugin for authentication and to use
   the config file created in (3): 
   ```
   certbot certonly -a certbot-plugin-gandi:dns --certbot-plugin-gandi:dns-credentials gandi.ini -d domain.com
   ```
   Add additional options as required to specify an installation plugin etc.
   

   
