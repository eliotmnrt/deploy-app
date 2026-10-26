# Deployment Guide

## Platforms

### Vercel (Primary)
- **Production**: Auto-deploys from `master` branch
- **Preview**: Auto-generated for each PR
- **URL**:  https://deploy-app-lac.vercel.app

### Railway (Backup)
- **Production**: Manual trigger from dashboard
- **Database**: PostgreSQL included

## Deployment Flow

1. **Development** → Push to feature branch
2. **Preview** → Create PR (auto-deploys preview)
3. **Staging** → Merge to `staging` branch
4. **Production** → Merge `staging` to `master`

## Environment Variables

### Required
- `PORT` - Server port (auto-set by platform)
- `NODE_ENV` - Environment (development/production)

## Rollback Procedure

1. Go to Actions → Rollback Deployment
2. Click "Run workflow"
3. Select environment (production/staging)
4. Enter version to rollback to
5. Confirm and monitor

## Monitoring

- **Health Check**: https://deploy-app-lac.vercel.app/health
- **Logs**: Vercel Dashboard → Deployments → Logs
- **Metrics**: Check platform dashboards

## Troubleshooting

### Deployment Fails
1. Check GitHub Actions logs
2. Verify environment variables
3. Test build locally: `npm start`
4. Check platform status pages

### App Not Responding
1. Check health endpoint
2. Review platform logs
3. Verify environment variables
4. Rollback if necessary
