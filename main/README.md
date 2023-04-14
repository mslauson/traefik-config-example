You have to touch the .json file and chmod 600
1. Clone this repository onto your vm
2. Change all occurances of youremail@fake.com to your cloudflare email
3. Change all occurances of example.com to your domain
4. Update the tls.yaml to have the subdomain you would like and routers (with the proper IP of your internal VM)
5. Set up your router to send all traffic on port 80 and 443
6. run the following command in the root of this directory (this file should live next to all of these files)
```bash
    touch acme.json && chmod 600 acme.json
```
7. Start the proxy
```bash
docker compose up -d
```

If you want to make updates, run the following to restart
```bash
docker compose down
docker compose up -d
```

If you want to check logs, run the following
```bash
docker logs traefik
```
