---
title:  "Automating MLOps with IBM watsonx for Maintaining Trustworthy AI Agents and Agentic Systems"
categories: 
    - LLMOps
    - MLOps
    - AI governance
tags: 
    - LLMOps
    - MLOps
    - generativeAI
    - architecture
    - bias
    - drift
    - watsonx
date: 2024-06-19
---

Agentic systems consisting of multiple heterogenous agents with language models (including API calls to external agents) must be monitored for data and model (or concept) drift to ensure trustworthiness. Agentic systems that expose smaller, specialised language models to inputs from the environment (or an ecosystem) are more liable to suffer from data drift caused by out-of-distribution (OOD) inputs. The adaptive and dynamic property of agentic systems and the external environment (machine and user) requires an equally dynamic approach to detecting drift, re-tuning, evaluating and deploying models (MLOps or LLMOps) to ensure the agents and the agentic system as a whole can be trusted.

The following diagram provides an approach to automate LLMOps on the IBM watsonx platform:

![LLMOps with watson](LLMOps.png)

### Explanation of Components

Client Application: The client application is the source of incoming HTTP or API requests. These could be end-user requests or requests from another application component. 

Iter8 (Model Experiments & Progressive Rollout): Iter8 manages the traffic distribution and experiment execution. It dynamically routes traffic between different model versions or pipeline endpoints based on an experiment configuration. Iter8 collects performance metrics such as latency, accuracy, and throughput for each version, enabling comparative analysis.

Watson Pipelines (Model Pipelines): Watson Pipelines executes workflows which can include data preprocessing, model inference, and post-processing.

Watson Machine Learning (Model Deployment & Inferencing): WML hosts and serves machine learning models and pipelines. It provides the infrastructure to deploy, manage, and scale machine learning models. Each deployed model or pipeline has a unique endpoint that can be called for inferencing. WML handles the underlying compute resources and scaling needs.

Watson OpenScale (Drift Monitoring): Watson OpenScale detects performance drift by comparing current model outputs with historical data. When drift is detected, it triggers model retraining or tuning workflows in Watson Studio to update the model with new data or improved algorithms. 

DevOps Toolchain (Continuous Integration / Continuous Delivery): The DevOps toolchain automates the deployment, updates, and overall orchestration of the machine learning models and pipelines. It includes tools for version control, CI/CD pipelines, and infrastructure automation. The DevOps toolchain ensures that new model versions or pipeline configurations are tested, validated, and deployed in an automated and controlled manner. It also manages rollbacks and incremental updates, integrating with Iter8 to facilitate progressive rollouts and A/B testing.

### DevOps Toolchain Orchestrated Tuning & Deployment Workflow

1. Drift Detection: Watson OpenScale continuously monitors the models for performance drift by analysing changes in model performance over time. This is a trigger to the Toolchain.

2. Model Tuning: When drift is detected, a Watson Studio GPU Runtime is used to tune the model. The tuned models are tested and validated to ensure they meet performance and accuracy standards before being deployed for further experimentation.

3. Experiment with Iter8: an Iter8 experiment is configured with custom metrics to compare the tuned model(s) against the baseline or existing models using a specified traffic distribution strategy. Iter8 dynamically routes traffic between the different Watson Pipelines endpoints (or WML endpoints) as specified in the experiment setup, collecting metrics such as latency, accuracy, and error rates to determine which model performs better according to predefined criteria.

4. Progressive Rollout: Based on the experiment results, the winning model or pipeline configuration is selected for production deployment. Iter8, in conjunction with the Istio Service Mesh (Red Hat OpenShift Service Mesh), gradually increases the traffic to the new model configuration while monitoring its performance to ensure stability and effectiveness. Once the new model configuration has proven its reliability through the progressive rollout, it receives 100% of the traffic, completing the deployment.

Further reading:

* Iter8 Custom Metrics: https://iter8.tools/0.10/metrics/custom-metrics/