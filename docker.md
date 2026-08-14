# Registry
- Login to a registry: `docker login <registry_url> -u <username>` e.g. `docker login <company_url>:5050 -u <gitlab_username>`

# Image
- Load tar.gz Docker image: `docker load < image.tar.gz`
- Export Docker image: `docker save <image_name>:<tag> | gzip > image_name.tar.gz`
