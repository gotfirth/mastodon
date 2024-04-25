# mastodon
This is my configuration for a Mastodon setup via Docker Compose that uses Valkey and OpenSearch.

I run a few small (single digit users) instances of Mastodon for myself and friends. I wanted to see what it would take to move away from Redis and Elasticsearch. As I was looking for samples and examples, I realized there weren't many of them available so I decided to share my configuration in case anyone else finds it helpful.

There were a number of iterations of this I went through as I swapped over to Valkey and OpenSearch to get it all working. These are small instances, so OpenSearch is running as a single node. I have this all running on a small server running cloudflared and sitting behind nginx and running certbot to keep the certificates up to date.

.env, .env.production and nginx.domain.name all require modification to work in your environment. I've tried to make the changes as obvious as possible, but I'm happy to help if you have questions.

I need to add a bit of documentation around the setup process, but I wanted to get the configuration out there first. I'll add more details as I have time.

## Files

.env - Environment variables for the Docker Compose setup; this is where I update the versions of things so I don't have to type them more than once.
.env.production - Environment variables for the Mastodon setup; this is where I put the configuration for the Mastodon instance.
docker-compose.yml - The Docker Compose file that sets up the Mastodon instance.
nginx.domain.name - The nginx configuration file that sets up the reverse proxy for the Mastodon instance.
