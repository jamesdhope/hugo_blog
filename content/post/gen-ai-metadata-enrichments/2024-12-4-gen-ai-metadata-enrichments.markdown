---
title:  "AI Generated Metadata Enrichments for Unstructured Data with IBM Spectrum Discover & watsonx.ai"
categories: 
    - generativeAI
    - architecture
    - big data
tags: 
    - data science
    - big data
    - IBM Fusion
    - IBM Spectrum
    - generativeAI
    - llms
    - watsonx
    - ibm
    - architecture
date: 2024-12-04
---

Generative AI has high utility for generating metadata for both structured and unstructured data and is especially applicable in the storage domain where the discoverability and useability of data is a primary concern in driving value from data across the enterprise.

In a recent IBM Client Engineering project we extended IBM Fusion with the Spectrum Discover Fusion SDK to create a data pipeline for AI generated metadata. We created a metadata policy in IBM Fusion to filter images with missing metadata tags and published the image reference to a Kafka topic for the Spectrum Discover Application to consume. We used the watson machine learning SDK with a basic prompt to generate metadata tags associated with the image that catalogued in IBM Fusion. We integrated IBM Knowledge Catalog for enterprise wide data cataloging and watsonx.ai for querying and to enable downstream AI building.

We deployed the IBM Spectrum Discover Application to OpenShift for a highly scalable, high-throughput data pipeline.

![system view](gen-ai-metadata-enrichments.png)

Example Spectrum Fusion Discover Application: https://github.com/IBM/Spectrum_Discover_Example_Application


