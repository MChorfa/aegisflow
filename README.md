# AegisFlow

## DISCLAIMER ❗❗❗

<span style="color:red;">❗ This project is a fictional example created for educational purposes. It does not represent a real company or product. ❗</span>

## Overview

**AegisFlow** is a scalable, secure, and resilient microservices-based solution designed for efficient file conversion, artifact analysis.
Leveraging modern technologies such as .NET, Kubernetes, Dapr, OpenFeature for feature flag management, and ONNX for AI-driven anomaly detection,
AegisFlow ensures high performance and reliability.

## Table of Contents

- [AegisFlow](#aegisflow)
  - [Overview](#overview)
  - [Table of Contents](#table-of-contents)
  - [Project Structure](#project-structure)
  - [Getting Started](#getting-started)
    - [Prerequisites](#prerequisites)
    - [Installation](#installation)
    - [Microservices](#microservices)

## Project Structure

```text
AegisFlow/
├── src/
│   ├── AegisFlow.FileConversion/
│   │   ├── Controllers/
│   │   ├── Services/
│   │   ├── Models/
│   │   ├── Program.cs
│   │   └── Dockerfile
│   ├── AegisFlow.ArtifactAnalysis/
│   │   ├── Controllers/
│   │   ├── Services/
│   │   ├── Models/
│   │   ├── Program.cs
│   │   └── Dockerfile
│   └── AegisFlow.Security/
│       ├── Controllers/
│       ├── Services/
│       ├── Models/
│       ├── Program.cs
│       └── Dockerfile
├── config/
│   ├── feature-flags.json
│   └── onnx-models/
├── helm/
│   ├── fileconversion/
│   ├── artifactanalysis/
│   └── security/
├── ci-cd/
│   ├── dagger/
│   │   ├── fileconversion_pipeline.dagger
│   │   ├── artifactanalysis_pipeline.dagger
│   │   └── security_pipeline.dagger
├── scripts/
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- [Git](https://git-scm.com/)
- [Docker](https://www.docker.com/)
- [.NET 9.0 SDK](https://dotnet.microsoft.com/download/dotnet/9.0)
- [Kubernetes](https://kubernetes.io/) cluster (e.g., Minikube, EKS, AKS, GKE)
- [Helm](https://helm.sh/)
- [Dapr CLI](https://docs.dapr.io/getting-started/install-dapr-cli/)
- [OpenFeature .NET SDK Contrib](https://github.com/open-feature/dotnet-sdk-contrib)
- [ONNX Runtime](https://onnxruntime.ai/)

### Installation

1. **Clone the Repository:**

```bash
git clone https://github.com/yourusername/AegisFlow.git
cd AegisFlow
```

2. Build Microservices:

Navigate to each microservice directory and build the project.

```bash
cd src/AegisFlow.FileConversion
dotnet build

cd ../AegisFlow.ArtifactAnalysis
dotnet build

cd ../AegisFlow.Security
dotnet build
```

3. Run Microservices Locally:

Use Docker to build and run the microservices.

```bash
docker build -t aegisflow-fileconversion:latest ./AegisFlow.FileConversion
docker run -d -p 5001:80 aegisflow-fileconversion:latest
```

4. Deploy to Kubernetes:

Use Helm charts to deploy microservices to your Kubernetes cluster.

```bash
helm upgrade --install fileconversion helm/fileconversion --namespace default
helm upgrade --install artifactanalysis helm/artifactanalysis --namespace default
helm upgrade --install security helm/security --namespace default
```

### Microservices

File Conversion Service

Handles file conversion tasks, supporting various formats and ensuring efficient processing.

 • Tech Stack: .NET, Docker, Kubernetes, Dapr, OpenFeature, ONNX

Artifact Analysis Service

Performs analysis on converted artifacts, providing insights and metadata extraction.

 • Tech Stack: .NET, Docker, Kubernetes, Dapr, OpenFeature, ONNX

Security Service

Manages security aspects, including authentication, authorization, and anomaly detection.

 • Tech Stack: .NET, Docker, Kubernetes, Dapr, OpenFeature, ONNX

Feature Flags

Utilizes OpenFeature for managing feature flags, enabling dynamic control over feature rollouts.

 • Configuration File: config/feature-flags.json
 • SDK Integration: OpenFeature .NET SDK Contrib

AI Detection with ONNX

Integrates ONNX models for AI-driven anomaly detection, enhancing system resilience.

 • Model Files: config/onnx-models/
 • Runtime: Microsoft.ML.OnnxRuntime

CI/CD Pipeline

Implements CI/CD pipelines using Dagger, automating build, test, and deployment processes.

 • Pipeline Scripts: ci-cd/dagger/
 • Tools: Dagger, GitHub Actions

Deployment

Deploy microservices using Kubernetes and Helm charts, ensuring scalability and high availability.

 • Helm Charts: helm/
 • Kubernetes Configurations: config/

Contributing

Contributions are welcome! Please fork the repository and create a pull request for any enhancements or bug fixes.

 1. Fork the Project
 2. Create your Feature Branch
 3. Commit your Changes
 4. Push to the Branch
 5. Open a Pull Request

License

Distributed under the Apache License 2.0. See `LICENSE` for more information.
