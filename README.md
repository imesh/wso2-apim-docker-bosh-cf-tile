# Cloud Foundry Tile for WSO2 API Manager 2.1.0

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

3. Upload the product/wso2apim-tile-<versiom>.pivotal file to Pivotal Ops Manager and apply changes.

## Known Issues

The docker-boshrelease seems to have an issue in specifying the docker storage paths and a fix has been done in [#91](https://github.com/cloudfoundry-community/docker-boshrelease/pull/91). To apply this fix follow below steps:

 - Run tile build command once

 - Extract ```product/releases/docker-30.1.3.tgz``` file:

   ```
   mkdir product/releases/docker-30.1.3/
   tar -xvf product/releases/docker-30.1.3.tgz -C product/releases/docker-30.1.3/
   ```
   
 - Extract ```product/releases/docker-30.1.3/jobs/docker.tgz```:

   ```
   mkdir product/releases/docker-30.1.3/jobs/docker/
   tar -xvf product/releases/docker-30.1.3/jobs/docker.tgz -C product/releases/docker-30.1.3/jobs/docker/
   ```

 - Apply the above fix to ```product/releases/docker-30.1.3/jobs/docker/templates/bin/ctl``` file.

 - Tar the files again and copy docker-30.1.3.tgz to cache/ folder with the file name docker-boshrelease.tgz
