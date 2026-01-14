# container-vuln-scan-pipeline

This project demonstrates a GitHub Actions CI/CD pipeline that builds a Docker image, scans it for vulnerabilities using Trivy, enforces a security gate, and pushes the image to GitHub Container Registry (GHCR) if no critical vulnerabilities are detected.

## Pipeline Stages
1. Checkout repository
2. Build Docker image
3. Scan image Trivy
4. Block pipeline on CRITICAL vulnerabilities
5. Authenitcate to GHCR
6. Push image if scan passes

## Security Gate
The pipeline is configured to fail if Trivy detects CRITICAL vulnerabilities, preventing vulnerable images from being published.

## Design Decisions
- Github-hosted runners are used to avoid local tooling dependencies
- GHCR is used for registry integration
- Permissions are explicitly defined for secure package publishing
- 
