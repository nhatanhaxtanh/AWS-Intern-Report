---
title: "PixelGuard: Enhance medical data privacy with an AI-based de-identification system for imaging research"
date: 2025-07-09
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

Published: 2025-07-09 - Authors: Shashank Tanksali, Steve Fu, Abhijit Gaonkar, and Javeed Shaik.

Medical imaging plays a critical role in clinical research, offering insights that improve our understanding of health, disease management, and treatment outcomes. Researchers rely on imaging to study organs, tissues, and cells in healthy and pathological states. These datasets also power education programs, training resources, workshops, and workforce enablement. However, protecting patient privacy within medical imagery is essential to maintain confidentiality, adherence to ethical and legal standards such as HIPAA and HITRUST, and continued patient trust. Images frequently contain sensitive details about conditions, diagnoses, or prognoses. Safeguarding personally identifiable information (PII) and protected health information (PHI) prevents unauthorized disclosure and reinforces trust in healthcare systems.

Regulations including the Health Insurance Portability and Accountability Act (HIPAA), the Health Information Trust Alliance Common Security Framework (HITRUST CSF) in the United States, and the European Union General Data Protection Regulation (GDPR) dictate how medical data must be processed, stored, anonymized, and shared. Violations can result in substantial penalties and reputational damage, while clinicians shoulder an ethical responsibility to protect patient privacy.

---

## Understanding DICOM

Digital Imaging and Communications in Medicine (DICOM) is the industry standard for storing, transmitting, and sharing medical images along with structured metadata. A DICOM file consists of pixel data and metadata fields that describe patient demographics, study parameters, imaging devices, acquisition protocols, clinical notes, and more. Because these fields often contain PII, DICOM files cannot be used for research or training until sensitive information is removed. De-identification must preserve data utility, and optimized file sizes lower storage and processing costs. Organizations may also need to export anonymized assets in DICOM or JPEG formats. AWS HealthImaging, a scalable, high-performance cloud archive for DICOM, delivers sub-second access globally. Storage and transfer TCO can be reduced by using High Throughput JPEG 2000 (HTJ2K), an industry-standard codec.

---

## Solution guide

PixelGuard is a secure de-identification platform built on Amazon Web Services (AWS) by Dr. Adrienne Kline, Assistant Professor at Northwestern University and founder of Xtasis, LLC. PixelGuard de-identifies medical images while preserving clinical value. The software leverages more than 75 AI models capable of detecting and removing multilingual, multi-oriented burned-in text across formats such as DICOM, JPEG, PNG, and NIfTI. It also supports customizable metadata anonymization. With an intuitive UI, enterprise-grade single sign-on (SSO), and on-premises deployment (no data leaves the customer environment), PixelGuard delivers compliant, high-throughput de-identification. The product is available on AWS Marketplace, and AWS Partner ScaleCapacity contributed to the UI, cloud infrastructure, and marketplace launch.

### Ingestion layer

The ingestion layer provides a UI and API to submit studies for de-identification. Medical device manufacturers can also integrate through the API to automate redaction. Before upload, the web experience and API endpoints can be protected using enterprise identity providers to enforce authorization. Alongside ingesting images, the layer records de-identification profiles that specify which fields to remove. Common configurations, such as HIPAA-compliant field sets, are predefined and stored for reuse.

### Pre de-identification layer

This staging layer stores images (or archives containing multiple images) prior to processing. It tracks metadata such as job ID, submission timestamp, field-removal profiles, and file formats. This data helps orchestrate downstream processing steps and auditing.

### Processing layer

The processing layer detects the source image format and applies de-identification according to configuration. Operations span metadata scrubbing (for DICOM tags) and pixel-level redaction. Output images can be compressed to optimize storage, and a crosswalk file is generated to map each anonymized object to a unique identifier. The crosswalk must be protected and stored separately from the anonymized images to prevent re-identification.

### De-identification pipeline output

Post-processing storage keeps the anonymized imagery ready for research. Outputs can be prepared in multiple formats to match study requirements. When images are delivered, they are optionally accompanied by the crosswalk file, which maintains the association between anonymized IDs and original IDs. The crosswalk remains encrypted and is only accessible to authorized personnel for legitimate re-identification needs.

### Auditing, monitoring, and observability layer

This layer captures access logs to record who accessed data, what they accessed, and when. Detailed error logs support troubleshooting when images cannot be de-identified automatically. These telemetry streams enable governance and simplify compliance reporting.

*Figure 1: PixelGuard logical architecture*

De-identifying medical images requires cleaning both metadata and pixel content. Some metadata fields must be anonymized rather than deleted to maintain research value. For instance, changing a 20-year-old patient's age to 80 would skew research conclusions. OCR techniques can detect burned-in text, and machine learning (ML) models identify regions to blur or redact. ML models can also produce confidence scores; images that fall below thresholds can be routed to a manual review queue.

---

## Tools and frameworks

- **Ingestion**: Implement the UI and API through Amazon API Gateway with request validation, authentication, authorization, and security policy enforcement. Integrate with Amazon Cognito to deliver fine-grained access control.
- **Pre de-identification storage**: Store predefined de-identification profiles (for example HIPAA) in Amazon Simple Storage Service (Amazon S3) or a combination of S3 and Amazon DynamoDB.
- **De-identification workflow**: Create multi-step pipelines with DICOM parsing libraries such as `pydicom` and scrubbing utilities such as `dicom-anonymizer`. Use Amazon Textract and Amazon Comprehend Medical to detect and remove embedded text within images.
- **Output storage**: After processing, compress and convert medical images as needed. Store anonymized assets and identifiers in S3 buckets or file systems, with or without compression, ensuring crosswalk data is isolated.
- **Supporting services**: Amazon API Gateway enforces organization-specific AuthN/AuthZ policies. AWS Key Management Service (AWS KMS) safeguards encryption keys. AWS Fargate runs containers at scale without managing servers. Amazon Macie adds another layer of protection by discovering sensitive data. AWS CloudFormation enables infrastructure as code (IaC) so you can declaratively define, create, and manage AWS resources.

The following screenshots show the PixelGuard experience:

*Figure 2: Configure redaction fields for medical images*

*Figure 3: Redaction job completion report*

*Figure 4: Side-by-side preview of original and redacted images*

---

## Conclusion

De-identifying medical imagery is essential for research and training. A robust technical architecture ensures anonymized images cannot be traced back to individuals while preserving scientific utility. PixelGuard, powered by AWS, enables flexible de-identification that upholds privacy laws, enhances security, and lowers risk. At the same time, it accelerates data sharing and collaboration, fueling faster AI-driven discoveries that advance public health while honoring ethical and legal obligations.

---

## Next steps

1. Access PixelGuard on AWS Marketplace.
2. Explore how the AWS Cloud helps solve medical mysteries: **Medical data-sharing innovation through the Undiagnosed Diseases Network**.
3. Learn how to build an enterprise medical imaging inference pipeline with **MONAI Deploy on AWS**.
4. Read about optimizing medical imaging AI deployments with **NVIDIA NIMs and AWS services**.
5. Contact your AWS representative to design a similar system for healthcare innovation.

---

## About the authors

**Shashank Tanksali** is a Solutions Architect at AWS who helps customers realize the full value of AWS technologies through architectural guidance and hands-on support. He collaborates closely with customers to design scalable, secure, cost-optimized cloud solutions that align with business context.

**Steve Fu** is a Principal Solutions Architect at AWS. He holds a PhD in Pharmaceutical Science from the University of Mississippi and has more than a decade of experience in technology and biomedical research. Steve is passionate about the positive impact technology can deliver to healthcare and life sciences.

**Abhijit Gaonkar** is a Senior DevOps Engineer and AWS Solutions Architect at ScaleCapacity. He specializes in building secure, scalable cloud platforms for public- and private-sector customers, focusing on healthcare, data privacy, and AI workloads. His expertise in infrastructure as code, automation, and AWS-native services has been crucial for compliant, high-performance deployments in regulated environments.

**Javeed Shaik** is Head of Cloud Platform Engineering at ScaleCapacity. Over 25 years, he has led data center modernization, cloud migration, and application modernization programs for Fortune 100 and Fortune 500 enterprises as well as major public-sector organizations. His ability to devise innovative solutions for complex business challenges has been instrumental to customer success.
