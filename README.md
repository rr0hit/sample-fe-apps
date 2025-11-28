# Sample Frontend Apps

A collection of sample frontend applications deployed using [Raptor CLI](https://github.com/Facets-cloud/raptor).

## Apps

- **hello-world** - A simple animated hello world page
- **hello-everyone** - A community-themed page with confetti animation

## Deployment

This repository uses GitHub Actions to automatically deploy the frontend apps when changes are pushed to the `main` branch.

### Manual Deployment

You can also trigger a manual deployment via the Actions tab, selecting which app to deploy.

### Prerequisites

The following secrets and variables must be configured in your GitHub repository:

**Secrets:**
- `FACETS_USERNAME` - Your Facets Control Plane username
- `FACETS_TOKEN` - Your Facets API token

**Variables:**
- `CONTROL_PLANE_URL` - Your Facets Control Plane URL
- `PROJECT_NAME` - The target project name

### Local Development

To deploy locally using Raptor CLI:

```bash
# Install Raptor
curl -L -o raptor https://github.com/Facets-cloud/raptor-releases/releases/latest/download/raptor-darwin-arm64
chmod +x raptor

# Set environment variables
export FACETS_USERNAME=your-username
export FACETS_TOKEN=your-token
export CONTROL_PLANE_URL=https://your-control-plane.facets.cloud

# Deploy hello-world
cd hello-world && zip -r ../hello-world.zip . && cd ..
./raptor set artifact-zip hello-world -p your-project -e dev -f hello-world.zip

# Deploy hello-everyone
cd hello-everyone && zip -r ../hello-everyone.zip . && cd ..
./raptor set artifact-zip hello-everyone -p your-project -e dev -f hello-everyone.zip
```
