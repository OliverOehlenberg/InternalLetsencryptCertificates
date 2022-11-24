 # Name Resolution - external DNS Server
To receive a Let's encrypt certificate for a server how is inaccessible from the internet, we muse the [dehydrated](https://github.com/dehydrated-io/dehydrated) tool. Dehydrated can perform a DNS Challenge, but this means that you must use a DNS Services how is providing an API for the DNS management. 
Our provider doesn't offer an API to add programmatically the required TXT entry into the DNS settings of our domain. Dehydrated is calling this "Hooks" and provides a list of supported provider: (https://github.com/dehydrated-io/dehydrated/wiki)

## Your domain is at a non-supported DNS provider?
Don't worry. We had the same issue. You must not transfer the domain to a different provider. You can simply use e.g. Cloudflare with a free account. 
