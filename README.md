## Thanks

- [FuaerCN/Cloudreve-Heroku](https://github.com/FuaerCN/Cloudreve-Heroku)
- [P3TERX/aria2.conf](https://github.com/P3TERX/aria2.conf)

## Notice

 1. **Do not abuse, account ban is at your own risk. **
 2. Heroku's file system is temporary, and will be restored to the deployment state after a forced restart every 24 hours. Not suitable for long-term download and file sharing purposes.
 3. The default speed limit of Aria2 configuration file is 5MB/s.

## Overview

  This project is used to deploy Cloudreve slave nodes on Heroku and integrate Aria2 offline download function.
  
## Deployment method

 **Do not use this repository to deploy directly**

  **Heroku fixes security flaw, currently cannot deploy from private repository via web page**

 1. Click Fork in the upper right corner, and then click Create Fork.
 2. On the repository page from Fork, click Setting and check Template repository.
 3. Then click Code to return to the previous page, click the new button Use this template under Settings, and create a new library with a random name.
 4. For example, your Github username is bobby, and the new repository name is green. After logging in to heroku, visit <https://dashboard.heroku.com/new?template=https://github.com/bobby/green> to deploy.
 5. First open the Cloudreve host management panel - offline download node, click on the new node to enter the wizard.
 6. Fill the Heroku Secret variable with the slave key.
 7. After Heroku is deployed, fill in the slave address with the Heroku APP domain name, the Aria2 RPC service address is <http://127.0.0.1:61800>, and the RPC key is blank.
 8. In the warehouse content directory, conf.ini is the Cloudreve setting file, aria2.conf is the aria2 setting file, and tracker.sh is used to automatically update the BT tracker every time the dyno starts.
 9. Each deployment will use the latest version of Cloudreve.

## Cloudflare Workers Anti-Generation

- [Use different dynos alternately on single and double days to bypass the 550 hour limit per month for Heroku non-credit card verification accounts](https://github.com/wy580477/PaaS-Related/blob/main/CF_Workers_Reverse_Proxy_chs.md)
- Fill in the Workers service domain name created above for the slave address.
