## Criterion 1: Symbolic Memory

**Objective**:  
Evaluate the structure and coherence of symbolic representations in planning and logical reasoning.

**Justification**:  
Symbolic models such as PDDL or ontologies allow for rule-based and structured planning. However, they may face issues related to expressiveness, scalability, and robustness in dynamic environments. Both the domain and problem files (core elements of PDDL) can be modified at runtime, which may impact system behavior.

**Method**:
1. Analyze the ontology used (classes, relationships, rules).
2. Evaluate the logical consistency of the model through inference tests.
3. Measure planner efficiency in different scenarios.
4. Examine integration between symbolic and subsymbolic knowledge representations.
5. Identify risks of rule manipulation in PDDL that could affect decision-making.

---

## Criterion 2: Subsymbolic Memory

**Objective**:  
Analyze the reliability and accuracy of stored configuration data and parameters.

**Justification**:  
Robots rely on configuration files to parameterize their behavior. Poorly calibrated or corrupted data can compromise performance and safety. For example, configuration files in Nav2.

**Method**:
1. Verify coherence and format of configuration files.
2. Evaluate the system's sensitivity to parameter errors.
3. Measure the impact of variations in input data on robot behavior.
4. Implement data corruption detection strategies.
5. Apply encryption and access control techniques to knowledge bases using tools like **SROS2** to ensure only authorized nodes access data, along with classic disk encryption (LUKS), database encryption (SQLite), file encryption (GPG), or using systems like SealFS[^1] or Blockchain to safeguard long-term state consistency in cloud systems.

---

## Criterion 3: Learning Systems

**Objective**:  
Examine the robustness, accuracy, and potential vulnerabilities in trained perception models.

**Justification**:  
Machine learning models are essential for robotic perception. However, they are susceptible to adversarial attacks, data bias, and interpretability issues.

**Method**:
1. Evaluate model accuracy across different scenarios.
2. Identify biases in training data.
3. Analyze resilience against adversarial attacks.
4. Measure the model's impact on robot decision-making.
5. Implement digital signatures to ensure model integrity (e.g., for YOLO).
6. Apply adversarial training techniques to strengthen vision models.

---

## Criterion 4: Generative AI

**Objective**:  
Evaluate generalization, interpretability, and susceptibility to adversarial attacks in models based on dense representations and deep learning, including embeddings and Large Language Models (LLMs).

**Justification**:  
Language models and embeddings enhance a robot’s ability to interpret unstructured information. However, they are vulnerable to prompt injection, bias, and poor interpretability.

**Method**:
1. Evaluate coherence and accuracy of generated responses.
2. Identify vulnerabilities to instruction injection attacks.
3. Measure adaptability across different domains.
4. Analyze the model's impact on robotic autonomy.
5. Apply digital signatures to ensure LLM model integrity.
6. Implement fallback mechanisms to generate safe responses in LLMs.

---

## Criterion 5: Secure and Robust Knowledge Storage and Retrieval

**Objective**:  
Evaluate the protection of knowledge against corruption, unauthorized access, and information loss.

**Justification**:  
Knowledge stored in robots may be targeted by attacks or affected by technical failures. Securing storage mechanisms is crucial for operational reliability.

**Method**:
1. Analyze access control and authentication mechanisms.
2. Evaluate data recovery strategies.
3. Measure resilience to data corruption and external attacks.
4. Apply data sanitization measures for LLM training data.
5. Implement audit mechanisms to ensure compliance with regulations like GDPR and NIST.

---

## Criterion 6: Evaluation in Real Environments

**Objective**:  
Validate knowledge performance in operational scenarios.

**Justification**:  
A cognitive system may perform well in simulations but fail in real-world conditions due to unexpected variations. Real-world evaluation is essential.

**Method**:
1. Compare system performance in simulation vs. real tests.
2. Assess adaptability to adverse conditions.
3. Measure the impact of knowledge quality on robotic performance.
4. Implement adversarial attack detection in vision models.
5. Perform penetration testing and simulated attacks in dev environments.
6. Establish rollback mechanisms to restore safe model versions.

---

## Criterion 7: Local Infrastructure Audits and Monitoring

**Objective**:  
Ensure continuous monitoring and validation of security events within the robot’s local infrastructure.

**Justification**:  
It is necessary to supervise stored knowledge and the processes accessing it to detect anomalies and vulnerabilities that could compromise robotic safety.

**Method**:
1. Integrate SIEM tools (e.g., Wazuh) for real-time monitoring of the local knowledge base.
2. Define security metrics to evaluate robot system stability.
3. Monitor manual and automatic model/data updates (e.g., from public repositories like HuggingFace).
4. Conduct periodic audits of local knowledge storage and processing systems.

---

## Criterion 8: Cloud Infrastructure Audits and Monitoring

**Objective**:  
Monitor access, integrity, and security of knowledge stored in the cloud.

**Justification**:  
Cloud-based systems introduce additional risks due to exposure to external threats, third-party dependencies, and the need to guarantee knowledge integrity.

**Method**:
1. Monitor access and integrity of models and data stored in the cloud.
2. Conduct periodic audits to verify cloud-based knowledge integrity.
3. Monitor updates from public sources (e.g., HuggingFace) or internal developers.
4. Assess compliance with cybersecurity regulations for cloud-based knowledge management.

---

## Criterion 9: Vulnerability Management

**Objective**:  
Identify, mitigate, and manage vulnerabilities in the robot’s knowledge and models.

**Justification**:  
Vulnerabilities in the knowledge base may be exploited to manipulate robot behavior, compromise system safety, or affect decision-making.

**Method**:
1. Integrate vulnerability scanning tools for ROS 2 and the operating system.
2. Implement whitelisting and access control for all robot memory systems.
3. Validate security patches before deployment.
4. Establish response plans for detected vulnerabilities.

---

## Criterion 10: Protection of Sensitive Data and Biometrics

**Objective**:  
Ensure the security, privacy, and regulatory compliance of biometric and sensitive data storage, processing, and access.

**Justification**:  
Storing biometric data on the robot or in the cloud introduces privacy risks and regulatory obligations, particularly under EU Regulation 2024/1689 and GDPR[^2]. Exposure of such data can lead to critical vulnerabilities, thus requiring encryption, restricted access, and continuous auditing.

**Method**:
- **Data encryption at rest and in transit**: Apply end-to-end encryption for biometric data stored locally or transmitted to the cloud (e.g., TLS 1.3).
- **Identity management and access control**: Implement multi-factor authentication (MFA) and strict access roles.
- **Monitoring and auditing**: Use SIEM tools to detect unauthorized access and conduct regular audits.
- **Data minimization and anonymization**: Avoid unnecessary storage and anonymize data where possible.
- **Regulatory compliance**: Ensure processes meet EU Regulation 2024/1689, GDPR, and other relevant privacy standards.
- **Cloud security**: Apply advanced encryption (e.g., AES-256) and restrict access through IAM (Identity and Access Management) controls.

---

[^1]: Guardiola et al. (2023). SealFS v2: Secure Storage for Robotics Knowledge Bases.  
[^2]: GDPR (Regulation (EU) 2016/679) and EU AI Regulation (2024/1689).


