# Setup
```
# Add certbot PPA
# For amazon linux use yum instead of apt-get

sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository universe
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update

# Install certbot
sudo apt-get install certbot python-certbot-nginx

# Get certificate and update Nginx config
sudo certbot --nginx -d <yourdomain>.com -d www.<yourdomain>.com
```

## For Amazon Linux
```
sudo yum install certbot python-certbot-nginx
sudo certbot --nginx -d <yourdomain>.com -d www.<yourdomain>.com
```

## Output
```
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator nginx, Installer nginx
Enter email address (used for urgent renewal and security notices)
 (Enter 'c' to cancel): <your_email_here>

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Please read the Terms of Service at
https://letsencrypt.org/documents/LE-SA-v1.2-November-15-2017.pdf. You must
agree in order to register with the ACME server at
https://acme-v02.api.letsencrypt.org/directory
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(A)gree/(C)ancel: A

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Would you be willing to share your email address with the Electronic Frontier
Foundation, a founding partner of the Let's Encrypt project and the non-profit
organization that develops Certbot? We'd like to send you email about our work
encrypting the web, EFF news, campaigns, and ways to support digital freedom.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: N
Obtaining a new certificate
Performing the following challenges:
http-01 challenge for bombaybrew.in
http-01 challenge for www.bombaybrew.in
Waiting for verification...
Cleaning up challenges
Deploying Certificate to VirtualHost /etc/nginx/conf.d/bombaybrew.conf
Deploying Certificate to VirtualHost /etc/nginx/conf.d/bombaybrew.conf
Redirecting all traffic on port 80 to ssl in /etc/nginx/conf.d/bombaybrew.conf
Redirecting all traffic on port 80 to ssl in /etc/nginx/conf.d/bombaybrew.conf

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Congratulations! You have successfully enabled https://bombaybrew.in and
https://www.bombaybrew.in

You should test your configuration at:
https://www.ssllabs.com/ssltest/analyze.html?d=bombaybrew.in
https://www.ssllabs.com/ssltest/analyze.html?d=www.bombaybrew.in
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/bombaybrew.in/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/bombaybrew.in/privkey.pem
   Your cert will expire on 2020-09-11. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot again
   with the "certonly" option. To non-interactively renew *all* of
   your certificates, run "certbot renew"
 - Your account credentials have been saved in your Certbot
   configuration directory at /etc/letsencrypt. You should make a
   secure backup of this folder now. This configuration directory will
   also contain certificates and private keys obtained by Certbot so
   making regular backups of this folder is ideal.
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le


```

## Test config
```
https://www.ssllabs.com/ssltest/analyze.html?d=<yourdomain>.com
https://www.ssllabs.com/ssltest/analyze.html?d=www.<yourdomain>.com
```

# Add new subdomain to existing domain
```
# adding cms.<yourdomain>.com to existing root and www domain.
sudo certbot --nginx -d <yourdomain>.com -d www.<yourdomain>.com -d cms.<yourdomain>.com

# output
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator nginx, Installer nginx

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
You have an existing certificate that contains a portion of the domains you
requested (ref: /etc/letsencrypt/renewal/bombaybrew.in.conf)

It contains these names: bombaybrew.in, www.bombaybrew.in

You requested these names for the new certificate: bombaybrew.in,
www.bombaybrew.in, ghost.bombaybrew.in.

Do you want to expand and replace this existing certificate with the new
certificate?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(E)xpand/(C)ancel: E
Renewing an existing certificate
Performing the following challenges:
http-01 challenge for ghost.bombaybrew.in
Waiting for verification...
Cleaning up challenges
Deploying Certificate to VirtualHost /etc/nginx/conf.d/bombaybrew.conf
Deploying Certificate to VirtualHost /etc/nginx/conf.d/bombaybrew.conf
Deploying Certificate to VirtualHost /etc/nginx/conf.d/bombaybrew.conf
Traffic on port 80 already redirecting to ssl in /etc/nginx/conf.d/bombaybrew.conf
Traffic on port 80 already redirecting to ssl in /etc/nginx/conf.d/bombaybrew.conf
Redirecting all traffic on port 80 to ssl in /etc/nginx/conf.d/bombaybrew.conf

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Your existing certificate has been successfully renewed, and the new certificate
has been installed.

The new certificate covers the following domains: https://bombaybrew.in,
https://www.bombaybrew.in, and https://ghost.bombaybrew.in

You should test your configuration at:
https://www.ssllabs.com/ssltest/analyze.html?d=bombaybrew.in
https://www.ssllabs.com/ssltest/analyze.html?d=www.bombaybrew.in
https://www.ssllabs.com/ssltest/analyze.html?d=ghost.bombaybrew.in
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

IMPORTANT NOTES:
 - Congratulations! Your certificate and chain have been saved at:
   /etc/letsencrypt/live/bombaybrew.in/fullchain.pem
   Your key file has been saved at:
   /etc/letsencrypt/live/bombaybrew.in/privkey.pem
   Your cert will expire on 2020-09-11. To obtain a new or tweaked
   version of this certificate in the future, simply run certbot again
   with the "certonly" option. To non-interactively renew *all* of
   your certificates, run "certbot renew"
 - If you like Certbot, please consider supporting our work by:

   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
   Donating to EFF:                    https://eff.org/donate-le
```


# Reference
https://certbot.eff.org/lets-encrypt/ubuntubionic-nginx
