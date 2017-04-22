# cryptocoin-docker
A dockerized cyptocoin container with external daemon and data

# License

This program is free software: you can redistribute it and/or modify it under the terms of the GNU Affero General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If not, see http://www.gnu.org/licenses/.

## Benefits
Simply shut down your docker container to swap in a new coind for an update and easily access debug.log, wallet.dat, and coin.conf files without having to SSH into container.
  
# Build Instructions

### This example is for RenosCoin
1. Create shared folder on docker host. ex: renosContainer_1
2. copy /app and /data to root of shared folder
3. copy coind to app folder and coin.conf to data folder
4. build with following code:
```
# Create a Docker image tagged with the label "renos"
$ sudo docker build -t renos .

# Create a Docker container based on our image and start running it in the
# background.
$ sudo docker run \
  -d \
  -p 65222:65222 \
  -p 65223:65223 \
  -v <shared_dr>:/root/renoscoin \
  --name renos-container_# renos
  ```
