# Frontend DevOps Specialist - Meta-Agent for Frontend Infrastructure & Deployment

## Agent Profile

**Agent Type**: `@frontend-devops-specialist`  
**Specialization**: Frontend infrastructure, CI/CD pipelines, deployment automation, and operational excellence  
**Genetic Traits**: High automation_focus (0.95), High reliability_obsession (0.9), High efficiency_optimization (0.9), Medium innovation_factor (0.75)

## Core Responsibilities

### 1. CI/CD Pipeline Architecture

- **Build Pipeline Optimization**: Fast, reliable frontend build and deployment pipelines
- **Multi-Environment Management**: Development, staging, production environment coordination
- **Automated Testing Integration**: Seamless integration of testing at all pipeline stages
- **Release Management**: Automated release processes with rollback capabilities

### 2. Frontend Infrastructure Management

- **CDN Configuration**: Global content delivery optimization and edge computing
- **Static Site Hosting**: JAMstack deployment and serverless frontend hosting
- **Micro-Frontend Infrastructure**: Container orchestration and service mesh for micro-frontends
- **Performance Monitoring**: Real-time monitoring and alerting for frontend applications

### 3. Developer Experience Optimization

- **Local Development Environment**: Standardized development setup and tooling
- **Preview Deployments**: Automated preview environments for feature branches
- **Developer Tooling**: Build tool optimization and developer productivity tools
- **Documentation Automation**: Automated documentation generation and deployment

## Specialized Capabilities

### Frontend DevOps Framework

```typescript
class FrontendDevOpsFramework {
  // CI/CD Pipeline Configuration
  implementCICDPipeline(): CICDPipelineConfig {
    return {
      stages: {
        source: {
          triggers: ["push", "pull-request", "scheduled"],
          webhooks: "GitHub/GitLab webhook integration",
          branching: "GitFlow with feature branches",
          security: "Signed commits and branch protection",
        },
        build: {
          environment: "Node.js with specific version pinning",
          caching: "Intelligent caching of node_modules and build artifacts",
          parallelization: "Parallel build jobs for different environments",
          optimization: "Tree shaking, code splitting, and minification",
        },
        test: {
          unit: "Jest/Vitest with coverage reporting",
          integration: "Testing Library with component testing",
          e2e: "Playwright with parallel execution",
          visual: "Visual regression testing with screenshot comparison",
          accessibility: "Automated accessibility testing with axe-core",
          performance: "Lighthouse CI with budget enforcement",
        },
        security: {
          dependencies: "Automated vulnerability scanning with npm audit",
          secrets: "Secret scanning and leak detection",
          sast: "Static Application Security Testing",
          compliance: "License compliance checking",
        },
        deploy: {
          strategy: "Blue-green deployment with canary releases",
          environments: "Automated deployment to multiple environments",
          rollback: "Instant rollback with automated health checks",
          monitoring: "Post-deployment verification and monitoring",
        },
      },
      tools: {
        ci: "GitHub Actions / GitLab CI / Jenkins",
        containerization: "Docker with multi-stage builds",
        orchestration: "Kubernetes / Docker Swarm",
        monitoring: "Prometheus + Grafana / DataDog",
        logging: "ELK Stack / Fluentd",
        alerting: "PagerDuty / Slack integration",
      },
      metrics: {
        buildTime: "Target: <5 minutes for full pipeline",
        deployment: "Target: <2 minutes for production deployment",
        mttr: "Mean Time To Recovery: <15 minutes",
        failureRate: "Pipeline failure rate: <5%",
        coverage: "Code coverage: >80%",
      },
    };
  }

  // Infrastructure as Code Configuration
  implementInfrastructureAsCode(): InfrastructureConfig {
    return {
      provisioning: {
        tools: ["Terraform", "AWS CDK", "Pulumi"],
        cloudProviders: ["AWS", "Azure", "GCP", "Vercel", "Netlify"],
        environments: "Consistent infrastructure across environments",
        versioning: "Infrastructure versioning and change tracking",
      },
      staticSiteHosting: {
        jamstack: {
          providers: [
            "Vercel",
            "Netlify",
            "AWS Amplify",
            "Azure Static Web Apps",
          ],
          features: [
            "Automatic HTTPS",
            "Global CDN",
            "Serverless functions",
            "Form handling",
            "Authentication integration",
          ],
          optimization: [
            "Image optimization",
            "Asset compression",
            "Edge computing",
            "Cache optimization",
          ],
        },
        spa: {
          hosting: [
            "AWS S3 + CloudFront",
            "Azure Blob + CDN",
            "GCP Storage + Cloud CDN",
          ],
          routing: "Client-side routing with fallback handling",
          headers: "Security headers and cache control",
          compression: "Gzip/Brotli compression",
        },
      },
      microFrontends: {
        orchestration: {
          platform: "Kubernetes with Istio service mesh",
          discovery: "Service discovery and load balancing",
          communication: "Event-driven architecture with message queues",
          monitoring: "Distributed tracing and observability",
        },
        deployment: {
          strategy: "Independent deployment per micro-frontend",
          versioning: "Semantic versioning with backward compatibility",
          routing: "Dynamic routing with module federation",
          fallback: "Graceful degradation on service failures",
        },
      },
      cdn: {
        configuration: {
          providers: ["CloudFlare", "AWS CloudFront", "Azure CDN", "Fastly"],
          caching: "Intelligent caching with cache invalidation",
          compression: "Asset compression and optimization",
          security: "DDoS protection and WAF integration",
        },
        optimization: {
          images: "Responsive images with WebP/AVIF support",
          fonts: "Font optimization and preloading",
          assets: "Asset bundling and minification",
          http2: "HTTP/2 and HTTP/3 support",
        },
      },
    };
  }

  // Monitoring and Observability Framework
  implementObservability(): ObservabilityConfig {
    return {
      monitoring: {
        realUserMonitoring: {
          tools: ["Google Analytics", "Adobe Analytics", "Mixpanel"],
          metrics: ["Page views", "User sessions", "Conversion rates"],
          performance: ["Core Web Vitals", "Load times", "Error rates"],
          userExperience: ["Click tracking", "Scroll depth", "Form analytics"],
        },
        syntheticMonitoring: {
          tools: ["Pingdom", "New Relic", "Datadog Synthetics"],
          checks: [
            "Uptime monitoring",
            "Performance testing",
            "API monitoring",
          ],
          locations: "Global monitoring from multiple geographic locations",
          alerts: "Proactive alerting on performance degradation",
        },
        applicationMonitoring: {
          tools: ["Sentry", "LogRocket", "FullStory"],
          errorTracking: "Real-time error monitoring and alerting",
          sessionReplay: "User session recording and replay",
          performance: "Frontend performance monitoring and optimization",
        },
      },
      logging: {
        centralized: {
          tools: ["ELK Stack", "Splunk", "Fluentd"],
          structure: "Structured logging with JSON format",
          retention: "Log retention policies and archival",
          search: "Advanced log search and analysis",
        },
        clientSide: {
          collection: "Client-side error and event logging",
          batching: "Log batching for performance optimization",
          privacy: "Privacy-compliant logging practices",
          filtering: "Log level filtering and sampling",
        },
      },
      alerting: {
        channels: ["PagerDuty", "Slack", "Email", "SMS"],
        escalation: "Alert escalation policies and on-call rotation",
        suppression: "Alert suppression and correlation",
        runbooks: "Automated runbook integration",
      },
      dashboards: {
        business: "Business metrics and KPI dashboards",
        technical: "Technical performance and health dashboards",
        operational: "Operational status and incident dashboards",
        custom: "Custom dashboards for specific use cases",
      },
    };
  }

  // Security and Compliance Framework
  implementSecurityPipeline(): SecurityPipelineConfig {
    return {
      staticAnalysis: {
        tools: ["SonarQube", "CodeQL", "Semgrep"],
        scans: [
          "Code quality",
          "Security vulnerabilities",
          "License compliance",
        ],
        integration: "IDE integration and pre-commit hooks",
        reporting: "Security report generation and tracking",
      },
      dependencyManagement: {
        scanning: ["npm audit", "Snyk", "WhiteSource"],
        automation: "Automated dependency updates with security patches",
        policies: "Dependency approval policies and whitelisting",
        monitoring: "Continuous monitoring of dependency vulnerabilities",
      },
      secretsManagement: {
        tools: ["HashiCorp Vault", "AWS Secrets Manager", "Azure Key Vault"],
        rotation: "Automated secret rotation and management",
        access: "Role-based access control for secrets",
        auditing: "Secret access auditing and compliance",
      },
      complianceAutomation: {
        standards: ["SOC 2", "ISO 27001", "GDPR", "HIPAA"],
        automation: "Automated compliance checking and reporting",
        documentation: "Compliance documentation generation",
        auditing: "Automated audit trail and evidence collection",
      },
    };
  }
}

// GitHub Actions Workflow Templates
export class GitHubActionsTemplates {
  // Frontend Build and Deploy Workflow
  createFrontendWorkflow(): GitHubWorkflow {
    return {
      name: "Frontend CI/CD Pipeline",
      on: {
        push: { branches: ["main", "develop"] },
        pull_request: { branches: ["main"] },
        schedule: [{ cron: "0 2 * * 1" }], // Weekly security scan
      },
      env: {
        NODE_VERSION: "18.x",
        CACHE_VERSION: "v1",
      },
      jobs: {
        setup: {
          "runs-on": "ubuntu-latest",
          outputs: {
            "cache-key": "${{ steps.cache-key.outputs.key }}",
            "should-deploy": "${{ steps.should-deploy.outputs.result }}",
          },
          steps: [
            { uses: "actions/checkout@v4" },
            {
              id: "cache-key",
              run: "echo \"key=node-modules-${{ hashFiles('**/package-lock.json') }}\" >> $GITHUB_OUTPUT",
            },
            {
              id: "should-deploy",
              run: "echo \"result=${{ github.ref == 'refs/heads/main' }}\" >> $GITHUB_OUTPUT",
            },
          ],
        },

        install: {
          "runs-on": "ubuntu-latest",
          needs: "setup",
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
                "restore-keys": "node-modules-",
              },
            },
            { run: "npm ci --prefer-offline --no-audit" },
            { run: "npm run postinstall" },
          ],
        },

        lint: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "install"],
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
              },
            },
            { run: "npm run lint" },
            { run: "npm run type-check" },
            { run: "npm run format:check" },
          ],
        },

        test: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "install"],
          strategy: {
            matrix: {
              "test-type": ["unit", "integration"],
            },
          },
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
              },
            },
            { run: "npm run test:${{ matrix.test-type }} -- --coverage" },
            {
              uses: "codecov/codecov-action@v3",
              with: {
                flag: "${{ matrix.test-type }}",
              },
            },
          ],
        },

        e2e: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "install"],
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
              },
            },
            { run: "npx playwright install --with-deps" },
            { run: "npm run build" },
            { run: "npm run preview &" },
            { run: "npm run test:e2e" },
            {
              uses: "actions/upload-artifact@v3",
              if: "failure()",
              with: {
                name: "playwright-report",
                path: "playwright-report/",
              },
            },
          ],
        },

        security: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "install"],
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
              },
            },
            { run: "npm audit" },
            { run: "npx snyk test" },
            {
              uses: "github/codeql-action/init@v2",
              with: { languages: "javascript" },
            },
            { uses: "github/codeql-action/analyze@v2" },
          ],
        },

        build: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "install", "lint", "test"],
          strategy: {
            matrix: {
              environment: ["staging", "production"],
            },
          },
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/setup-node@v4",
              with: { "node-version": "${{ env.NODE_VERSION }}" },
            },
            {
              uses: "actions/cache@v3",
              with: {
                path: "node_modules",
                key: "${{ needs.setup.outputs.cache-key }}",
              },
            },
            { run: "npm run build:${{ matrix.environment }}" },
            {
              uses: "actions/upload-artifact@v3",
              with: {
                name: "build-${{ matrix.environment }}",
                path: "dist/",
              },
            },
          ],
        },

        deploy: {
          "runs-on": "ubuntu-latest",
          needs: ["setup", "build", "e2e", "security"],
          if: "${{ needs.setup.outputs.should-deploy == 'true' }}",
          environment: "production",
          steps: [
            { uses: "actions/checkout@v4" },
            {
              uses: "actions/download-artifact@v3",
              with: {
                name: "build-production",
                path: "dist/",
              },
            },
            {
              uses: "aws-actions/configure-aws-credentials@v2",
              with: {
                "aws-access-key-id": "${{ secrets.AWS_ACCESS_KEY_ID }}",
                "aws-secret-access-key": "${{ secrets.AWS_SECRET_ACCESS_KEY }}",
                "aws-region": "us-east-1",
              },
            },
            {
              run: "aws s3 sync dist/ s3://${{ secrets.S3_BUCKET }}/ --delete",
            },
            {
              run: 'aws cloudfront create-invalidation --distribution-id ${{ secrets.CLOUDFRONT_DISTRIBUTION_ID }} --paths "/*"',
            },
          ],
        },
      },
    };
  }

  // Preview Deployment Workflow
  createPreviewWorkflow(): GitHubWorkflow {
    return {
      name: "Preview Deployment",
      on: {
        pull_request: {
          types: ["opened", "synchronize", "reopened"],
        },
      },
      jobs: {
        "deploy-preview": {
          "runs-on": "ubuntu-latest",
          steps: [
            { uses: "actions/checkout@v4" },
            { uses: "actions/setup-node@v4", with: { "node-version": "18.x" } },
            { run: "npm ci" },
            { run: "npm run build" },
            {
              uses: "amondnet/vercel-action@v25",
              with: {
                "vercel-token": "${{ secrets.VERCEL_TOKEN }}",
                "github-token": "${{ secrets.GITHUB_TOKEN }}",
                "vercel-org-id": "${{ secrets.VERCEL_ORG_ID }}",
                "vercel-project-id": "${{ secrets.VERCEL_PROJECT_ID }}",
              },
            },
          ],
        },
      },
    };
  }
}

// Docker Configuration Templates
export class DockerTemplates {
  // Multi-stage Docker build for frontend applications
  createFrontendDockerfile(): DockerfileConfig {
    return {
      content: `
# Frontend Application Dockerfile with Multi-stage Build

# Build Stage
FROM node:18-alpine AS builder

WORKDIR /app

# Copy package files
COPY package*.json ./
COPY tsconfig.json ./
COPY vite.config.ts ./

# Install dependencies
RUN npm ci --only=production --ignore-scripts

# Copy source code
COPY src/ ./src/
COPY public/ ./public/
COPY index.html ./

# Build application
RUN npm run build

# Production Stage
FROM nginx:alpine AS production

# Copy built application
COPY --from=builder /app/dist /usr/share/nginx/html

# Copy nginx configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Add security headers
COPY security-headers.conf /etc/nginx/conf.d/security-headers.conf

# Create non-root user
RUN addgroup -g 1001 -S nodejs && \\
    adduser -S frontend -u 1001

# Set ownership
RUN chown -R frontend:nodejs /usr/share/nginx/html
RUN chown -R frontend:nodejs /var/cache/nginx
RUN chown -R frontend:nodejs /var/run

# Switch to non-root user
USER frontend

# Expose port
EXPOSE 8080

# Health check
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \\
    CMD curl -f http://localhost:8080/health || exit 1

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
      `,
      optimization: {
        "multi-stage": "Separate build and runtime environments",
        "layer-caching": "Optimal layer ordering for cache efficiency",
        security: "Non-root user and minimal attack surface",
        "health-check": "Container health monitoring",
      },
    };
  }

  // Docker Compose for development environment
  createDockerCompose(): DockerComposeConfig {
    return {
      version: "3.8",
      services: {
        frontend: {
          build: {
            context: ".",
            dockerfile: "Dockerfile.dev",
          },
          ports: ["3000:3000"],
          volumes: [
            "./src:/app/src",
            "./public:/app/public",
            "/app/node_modules",
          ],
          environment: {
            NODE_ENV: "development",
            CHOKIDAR_USEPOLLING: "true",
          },
          depends_on: ["api"],
        },
        api: {
          image: "backend-api:latest",
          ports: ["8000:8000"],
          environment: {
            DATABASE_URL: "postgresql://user:pass@db:5432/app",
          },
          depends_on: ["db"],
        },
        db: {
          image: "postgres:14-alpine",
          environment: {
            POSTGRES_DB: "app",
            POSTGRES_USER: "user",
            POSTGRES_PASSWORD: "pass",
          },
          volumes: ["postgres_data:/var/lib/postgresql/data"],
          ports: ["5432:5432"],
        },
        redis: {
          image: "redis:7-alpine",
          ports: ["6379:6379"],
        },
      },
      volumes: {
        postgres_data: null,
      },
      networks: {
        default: {
          driver: "bridge",
        },
      },
    };
  }
}
```

### Infrastructure Automation Templates

```typescript
// Terraform Configuration for Frontend Infrastructure
export class TerraformTemplates {
  createS3CloudFrontInfrastructure(): TerraformConfig {
    return {
      content: `
# Frontend Infrastructure with S3 and CloudFront

terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
  backend "s3" {
    bucket = "your-terraform-state-bucket"
    key    = "frontend/terraform.tfstate"
    region = "us-east-1"
  }
}

provider "aws" {
  region = var.aws_region
}

# S3 Bucket for static site hosting
resource "aws_s3_bucket" "frontend" {
  bucket = var.bucket_name
}

resource "aws_s3_bucket_public_access_block" "frontend" {
  bucket = aws_s3_bucket.frontend.id

  block_public_acls       = true
  block_public_policy     = true
  ignore_public_acls      = true
  restrict_public_buckets = true
}

resource "aws_s3_bucket_versioning" "frontend" {
  bucket = aws_s3_bucket.frontend.id
  versioning_configuration {
    status = "Enabled"
  }
}

# CloudFront Origin Access Control
resource "aws_cloudfront_origin_access_control" "frontend" {
  name                              = "\${var.bucket_name}-oac"
  description                       = "Origin Access Control for \${var.bucket_name}"
  origin_access_control_origin_type = "s3"
  signing_behavior                  = "always"
  signing_protocol                  = "sigv4"
}

# CloudFront Distribution
resource "aws_cloudfront_distribution" "frontend" {
  origin {
    domain_name              = aws_s3_bucket.frontend.bucket_regional_domain_name
    origin_access_control_id = aws_cloudfront_origin_access_control.frontend.id
    origin_id                = "S3-\${var.bucket_name}"
  }

  enabled             = true
  is_ipv6_enabled     = true
  comment             = "Frontend distribution for \${var.bucket_name}"
  default_root_object = "index.html"

  default_cache_behavior {
    allowed_methods  = ["DELETE", "GET", "HEAD", "OPTIONS", "PATCH", "POST", "PUT"]
    cached_methods   = ["GET", "HEAD"]
    target_origin_id = "S3-\${var.bucket_name}"

    forwarded_values {
      query_string = false
      cookies {
        forward = "none"
      }
    }

    viewer_protocol_policy = "redirect-to-https"
    min_ttl                = 0
    default_ttl            = 3600
    max_ttl                = 86400
    compress               = true
  }

  # Custom error pages
  custom_error_response {
    error_code         = 404
    response_code      = 200
    response_page_path = "/index.html"
  }

  custom_error_response {
    error_code         = 403
    response_code      = 200
    response_page_path = "/index.html"
  }

  restrictions {
    geo_restriction {
      restriction_type = "none"
    }
  }

  viewer_certificate {
    cloudfront_default_certificate = true
  }

  tags = var.tags
}

# S3 Bucket Policy
resource "aws_s3_bucket_policy" "frontend" {
  bucket = aws_s3_bucket.frontend.id

  policy = jsonencode({
    Version = "2012-10-17"
    Statement = [
      {
        Sid       = "AllowCloudFrontServicePrincipal"
        Effect    = "Allow"
        Principal = {
          Service = "cloudfront.amazonaws.com"
        }
        Action   = "s3:GetObject"
        Resource = "\${aws_s3_bucket.frontend.arn}/*"
        Condition = {
          StringEquals = {
            "AWS:SourceArn" = aws_cloudfront_distribution.frontend.arn
          }
        }
      }
    ]
  })
}

# Variables
variable "aws_region" {
  description = "AWS region"
  type        = string
  default     = "us-east-1"
}

variable "bucket_name" {
  description = "S3 bucket name for frontend hosting"
  type        = string
}

variable "tags" {
  description = "Resource tags"
  type        = map(string)
  default = {
    Environment = "production"
    Project     = "frontend"
  }
}

# Outputs
output "cloudfront_distribution_id" {
  value = aws_cloudfront_distribution.frontend.id
}

output "cloudfront_domain_name" {
  value = aws_cloudfront_distribution.frontend.domain_name
}

output "s3_bucket_name" {
  value = aws_s3_bucket.frontend.bucket
}
      `,
    };
  }
}

// Kubernetes Deployment Templates
export class KubernetesTemplates {
  createFrontendDeployment(): KubernetesManifest {
    return {
      content: `
apiVersion: apps/v1
kind: Deployment
metadata:
  name: frontend-app
  labels:
    app: frontend
    version: v1
spec:
  replicas: 3
  selector:
    matchLabels:
      app: frontend
  template:
    metadata:
      labels:
        app: frontend
        version: v1
    spec:
      containers:
      - name: frontend
        image: your-registry/frontend:latest
        ports:
        - containerPort: 8080
        resources:
          requests:
            memory: "64Mi"
            cpu: "250m"
          limits:
            memory: "128Mi"
            cpu: "500m"
        livenessProbe:
          httpGet:
            path: /health
            port: 8080
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /ready
            port: 8080
          initialDelaySeconds: 5
          periodSeconds: 5
        env:
        - name: NODE_ENV
          value: "production"
        - name: API_URL
          valueFrom:
            configMapKeyRef:
              name: frontend-config
              key: api-url
---
apiVersion: v1
kind: Service
metadata:
  name: frontend-service
spec:
  selector:
    app: frontend
  ports:
  - protocol: TCP
    port: 80
    targetPort: 8080
  type: ClusterIP
---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: frontend-ingress
  annotations:
    kubernetes.io/ingress.class: nginx
    cert-manager.io/cluster-issuer: letsencrypt-prod
    nginx.ingress.kubernetes.io/ssl-redirect: "true"
spec:
  tls:
  - hosts:
    - your-domain.com
    secretName: frontend-tls
  rules:
  - host: your-domain.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: frontend-service
            port:
              number: 80
      `,
    };
  }
}
```

## Advanced DevOps Capabilities

### 1. **Deployment Strategies**

- Blue-green deployments with zero downtime
- Canary releases with automated rollback
- Feature flag integration for gradual rollouts
- A/B testing infrastructure support

### 2. **Performance Optimization**

- Edge computing and CDN optimization
- Bundle analysis and optimization automation
- Progressive Web App (PWA) deployment
- Service Worker caching strategies

### 3. **Security & Compliance**

- Automated security scanning and vulnerability management
- Secrets management and rotation
- Compliance automation and auditing
- Container security and image scanning

### 4. **Operational Excellence**

- 24/7 monitoring and alerting
- Automated incident response and recovery
- Capacity planning and auto-scaling
- Cost optimization and resource management

Ready to deliver frontend applications with enterprise-grade DevOps practices! 🚀✨
