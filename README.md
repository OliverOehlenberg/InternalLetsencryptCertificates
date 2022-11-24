# How to use Lets Encrypt internally?
During development but also in test or lab environments, we're facing the problem, that we need an SSL certificate to encrypt the traffic and to ensure that the build functionality is working via an SSL connection too. In the past, we used mostly an own certification authority (CA) e.g. based on a OpenSSL capability on Linux.

### New security guidelines should not be ignored
In parallel, Google has introduced the  secure DNS service on Android to prevent man-in-the-middle attacks. If you don't do a modification on your Androids settings, Google will automatically use the Google DNS server instead of your local (private) DNS. 
Both evolutions make the development of mobile applications and the related testing more complicated, and we don't replicate the outside world in these environments. Unfortunately, not every development environment can fully represent the outside world. Sometimes this is cost driven, but depending on the used technology, there are additional challenges. The best example is, when you develop an extension/application for Nextcloud. Instead of installing the Nextcloud environment into the real internet, I prefer to use a local virtual environment which cannot be access from the internet because I enable further services like debugging or tracing tools. Both could be a risk, when we're using them into a public accessible system.  

### Where is the problem?
If I'm using a test system, we must use an internal DNS Server to get a proper name resolution and in addition, I must leverage a web server certificate from my local CA, which is not installed by default non-cooperate devices. This means we're running in to issues: Android will normally not use my internal DNS server to perform the name resolution (secure DNS service) and the used web server certificate isn't trusted by default too. Sure, we can work around this when we change settings on the device, but by the same token, we're moving away from the real-world scenarios. The better approach is to use a public (trusted) DNS and a by-default trusted web server certificate.

## Prerequisites
What is needed when we're building an internal development environment with a public trusted DNS and trusted web server certificate?
- An public registered domain (such as mindfabrik.de)
- An virtual Linux server which can request the Let's encrypt certificate and act, when needed, as a Reverse Proxy service.

## How to set up the environment?





