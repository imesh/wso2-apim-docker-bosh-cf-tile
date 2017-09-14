# Cloud Foundry Tile for WSO2 API Manager

This repository includes a Cloud Foundry Tile for deploying WSO2 API Manager 2.1.0 on BOSH via Pivotal Ops Manager. 

## Quick Start

1. Build the WSO2 API Manager Docker image using the below commands:

   ```
   cd dockerfiles/
   ./build.sh
   ```

2. Build the tile using the below command:
   
   ```
   tile build --cache cache/
   ```

3. Upload the product/wso2apim-tile-<versiom>.pivotal file to Pivotal Ops Manager and execute a deployment.
