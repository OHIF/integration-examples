# Secure DICOMWeb OHIF / dcm4che Example

## Setup
1. Create /opt/docker
2. Copy app.json and site.conf to /opt/docker
3. Edit /etc/hosts. Add the IP you get from ifconfig en0 inet to your hosts file and alias it to the name 'dockerhost'
3. Run docker-compose up
4. [Add the OpenID Connect Client for dcm4chee](https://github.com/dcm4che/dcm4chee-arc-light/wiki/Run-all-archive-services-with-secured-UI-on-a-single-host#register-the-archive-ui-as-oidc-client-in-keycloak)
5. Add an OpenID Connect Client for OHIF. Follow the same instructions as for dcm4chee, but use the root URL of just http://dockerhost/

## Testing
* Log in to the OHIF Viewer at http://dockerhost using the 'Login with Keycloak' button.
* Log in to the dcm4chee Archive at http://dockerhost/dcm4chee-arc/ui2
* Upload or push (e.g. STOW-RS or C-MOVE) some studies into dcm4chee. These will become visible and loadable in the OHIF Viewer.
* Load Keycloak's administration console at http://dockerhost/auth/admin/dcm4che/console. Now you can create Users and assign them Roles.
* Logging into one service will give you access to the other services.
* Try using curl http://dockerhost/dcm4chee-arc/aets/DCM4CHEE/rs/studies