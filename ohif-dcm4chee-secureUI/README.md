1. Create /opt/docker
2. Copy app.json and site.conf to /opt/docker
3. Edit /etc/hosts. Add the IP you get from ifconfig en0 inet to your hosts file and alias it to the name 'dockerhost'
3. Run docker-compose up
4. [Add the OpenID Connect Client for dcm4chee](https://github.com/dcm4che/dcm4chee-arc-light/wiki/Run-all-archive-services-with-secured-UI-on-a-single-host#register-the-archive-ui-as-oidc-client-in-keycloak)