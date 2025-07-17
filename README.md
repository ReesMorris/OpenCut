# OpenCut (Containerized)

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.com/deploy/opencut?referralCode=rees)

A containerized version of [OpenCut](https://github.com/OpenCut-app/OpenCut) - the free, open-source video editor. This template is designed for easy deployment on Railway, but can run anywhere Docker is supported.

## What is OpenCut?

OpenCut is a privacy-focused, browser-based video editor that keeps your videos on your device. No watermarks, no subscriptions, just free video editing.

**Features:**
- Timeline-based editing
- Multi-track support  
- Real-time preview
- Client-side processing (files never leave your browser)
- No watermarks or subscriptions

## What This Template Provides

This fork makes a few key modifications to the original OpenCut project to enable easy deployment in a containerized environment:

1. **Auth Configuration** - Fixed runtime environment variable handling for `BETTER_AUTH_URL`
2. **Migration Support** - Added Drizzle migration files and dependencies to Docker image  
3. **Build Optimization** - Configured standalone Next.js build for containerization

## Quick Deploy

Click the button above or use this template URL:
```
https://railway.com/deploy/opencut?referralCode=rees
```

Railway will automatically:
1. Create a PostgreSQL database
2. Run database migrations
3. Deploy the containerized application
4. Provide you with a public URL

## Environment Variables

The template configures these automatically, but for reference:

| Variable | Description | Default |
|----------|-------------|---------|
| `DATABASE_URL` | PostgreSQL connection string | *Set by Railway* |
| `BETTER_AUTH_URL` | Base URL for authentication | *Your Railway domain* |
| `BETTER_AUTH_SECRET` | Auth encryption secret | *Generated randomly* |
| `UPSTASH_REDIS_REST_URL` | Redis connection URL | *Set by Railway* |
| `UPSTASH_REDIS_REST_TOKEN` | Redis auth token | *Set by Railway* |

## Local Development

To run this containerized version locally:

```bash
# Clone this repository
git clone https://github.com/ReesMorris/OpenCut.git
cd OpenCut

# Build the Docker image
docker build -t opencut -f apps/web/Dockerfile .

# Run with environment variables
docker run -p 3000:3000 \
  -e BETTER_AUTH_URL=http://localhost:3000 \
  -e BETTER_AUTH_SECRET=your-secret-here \
  -e DATABASE_URL=your-db-url \
  opencut
```

## Upstream Sync

This template stays synchronized with the main OpenCut repository. Major updates are merged regularly to ensure you get the latest features and fixes.

**Original Repository:** [OpenCut-app/OpenCut](https://github.com/OpenCut-app/OpenCut)

## Support

- **Template Issues:** Post on the [template discussion board](https://station.railway.com/templates/open-cut-01b73deb)
- **OpenCut Issues:** Report to the [main OpenCut repository](https://github.com/OpenCut-app/OpenCut/issues)
- **Railway Issues:** Check [Railway's documentation](https://docs.railway.app/)

## License

This project maintains the same [MIT License](LICENSE) as the original OpenCut project.