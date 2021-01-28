# RadarrSync 
RadarrSync Syncs two Radarr servers through web API. This is a modified version designed to be run in a docker container. This version supports only two servers.

## How to Run
Pull the docker image from
https://hub.docker.com/r/dmanius/radarrsync-docker

You need to pass in the following environment variables:
- RADARR_URL -> The endpoint of your radarr server
- RADARR_KEY -> The API key for your radarr server
- RADARR4K_URL -> The endpoint of your radarr server you want to sync to
- RADARR4K_KEY -> The API key for this server
- PROFILE_ID -> The profile number you want the video to transcode to

## Example docker-compose.yml  
>\# radarrsync  
> &nbsp;&nbsp;&nbsp;radarsync:  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;image:  dmanius/radarrsync-docker  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;container_name: radarrsync  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;environment:  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- RADARR_URL=https://radarr-url.com  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- RADARR4K_URL=https://radarr4k-url.com  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- RADARR_KEY=767a4a5283e0c48e39e922638f405a9  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- RADARR4K_KEY=f52de21g4e6c75ab19y34281cd84008a  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;- PROFILE_ID=5  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;restart:  
> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;always  
## Notes
 * Ensure that the root path is the same on both servers. ie /movie
