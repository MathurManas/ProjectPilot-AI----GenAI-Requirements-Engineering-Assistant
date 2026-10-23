# 🚀 ProjectPilot AI
### GenAI-Powered Requirements Engineering & Project Planning Assistant

**Transform unstructured business requirements into structured, traceable, and testable software specifications using Generative AI.**

ProjectPilot AI is a GenAI-powered application designed to streamline early-stage software development by converting natural-language business requirements into structured Software Requirement Specifications (SRS), Agile user stories, acceptance criteria, and User Acceptance Testing (UAT) test cases.

Beyond document generation, the project aims to address practical challenges in requirements engineering, including ambiguity detection, requirements traceability, and change impact analysis.

The goal is to build an intelligent assistant that helps teams move from an initial business problem to a structured, testable, and maintainable set of software requirements.

**Project Status:** 🚧 In Development

**Domain:** Generative AI | Business Analysis | Requirements Engineering | Agile Project Management

---

## 📌 Table of Contents

- [Problem Statement](#-problem-statement)
- [Proposed Solution](#-proposed-solution)
- [Key Features](#-key-features)
- [Real-World Use Case](#-real-world-use-case-water-resource-management)
- [How It Works](#-how-it-works)
- [System Architecture](#-system-architecture)
- [Technology Stack](#-technology-stack)
- [Project Structure](#-project-structure)
- [Evaluation Strategy](#-evaluation-strategy)
- [Expected Impact](#-expected-impact)
- [Development Roadmap](#-development-roadmap)
- [Getting Started](#-getting-started)
- [Limitations and Responsible Use](#-limitations-and-responsible-use)
- [Future Enhancements](#-future-enhancements)

---

## 🎯 Problem Statement

Software projects frequently begin with informal, incomplete, or ambiguous business requirements.

Statements such as:

- "The system should be fast."
- "Users should receive alerts in real time."
- "The application must be secure."
- "The system should generate useful reports."

communicate general expectations but lack the detail needed for implementation and testing.

When such requirements are translated directly into software specifications, teams may encounter:

- Unclear functional and non-functional requirements.
- Missing acceptance criteria.
- Incomplete test coverage.
- Inconsistent project documentation.
- Difficulty tracing requirements to their corresponding test cases.
- Unexpected consequences when requirements change.

Traditional documentation workflows can also involve repetitive manual work when creating SRS documents, user stories, and testing artifacts.

**The challenge is not simply generating documentation. It is ensuring that requirements are clear, connected, testable, and maintainable as a project evolves.**

---

## 💡 Proposed Solution

ProjectPilot AI aims to provide a structured requirements engineering workflow powered by Generative AI.

Users will be able to submit an initial business problem, review automatically identified ambiguities, refine requirements, and generate the documentation needed to support software planning and testing.

The proposed workflow is:

**Business Problem → Requirements Analysis → Ambiguity Resolution → SRS Generation → Agile User Stories → Acceptance Criteria → UAT Test Cases → Traceability Matrix**

When requirements change, the application will also analyze their relationships with existing user stories, acceptance criteria, and test cases to identify potentially affected artifacts.

Rather than treating AI-generated outputs as automatically correct, the system is designed to support human review and validation throughout the workflow.

---

## ✨ Key Features

The following capabilities are planned for development.

### 1. 🧠 Intelligent Requirements Analysis

Convert unstructured business descriptions into organized, individually identifiable requirements.

The system will aim to:

- Extract functional requirements.
- Identify non-functional requirements.
- Organize requirements by category.
- Assign unique requirement identifiers.
- Identify incomplete or conflicting statements.
- Highlight assumptions and unresolved questions.

**Example**

Input:

> The reservoir monitoring system should be fast and reliable.

Potential findings:

- Performance expectations are undefined.
- Availability requirements have not been specified.
- Reliability needs measurable acceptance criteria.

The application will suggest clarification questions instead of silently treating vague statements as complete requirements.

### 2. 🔎 Ambiguity Detection and Clarification

Identify vague, incomplete, or difficult-to-test requirements before generating the final specification.

| Original Statement | Potential Issue | Suggested Clarification |
|---|---|---|
| The system should be fast. | No measurable performance target | What is the maximum acceptable response time? |
| Water levels should be monitored in real time. | Monitoring delay is undefined | What is the maximum acceptable delay between sensor readings and dashboard updates? |
| Officials should receive alerts. | Notification method is unspecified | Should notifications be delivered through SMS, email, or mobile push notifications? |
| The system must be secure. | Security expectations are unclear | What authentication, authorization, and access-control requirements apply? |

Users will be able to review the questions and provide additional information before proceeding.

The aim is to reduce ambiguity before it becomes a problem during implementation or testing.

### 3. 📄 Automated Software Requirement Specification (SRS)

Generate structured software requirements documentation from reviewed business requirements.

The proposed SRS structure includes:

- Introduction and purpose.
- Project scope.
- Stakeholders and user roles.
- Functional requirements.
- Non-functional requirements.
- External interface requirements.
- Assumptions and constraints.
- Acceptance criteria.
- Requirement identifiers and traceability references.

The document will follow an IEEE 830-inspired structure.

The system will distinguish confirmed requirements from assumptions and unresolved questions to avoid presenting invented details as established business facts.

### 4. 📝 Agile User Story Generation

Transform approved requirements into structured Agile user stories.

**Example**

As a reservoir monitoring officer, I want to view current reservoir water levels so that I can monitor water conditions and respond to potential risks.

Each user story will be associated with its originating requirement.

Where sufficient information is available, the system will also propose acceptance criteria that describe the expected behavior.

The objective is to produce artifacts that are understandable to both technical and non-technical stakeholders.

### 5. 🧪 Acceptance Criteria and UAT Test Case Generation

Generate testable acceptance criteria and UAT test cases from approved requirements and user stories.

**Example: Reservoir Alerting**

**Test Case ID:** TC-004

**Scenario:** Reservoir water level falls below the configured lower threshold.

- **Precondition:** A valid lower threshold has been configured.
- **Input:** A validated sensor reading falls below the threshold.
- **Expected Result:** The system generates an alert for the configured recipients and records the alert event.
- **Validation:** Verify the alert and corresponding event record.

Users will be able to review test cases and record their execution status, such as Passed, Failed, or Blocked.

Generating a test case and executing that test are separate activities; the application will not treat generated tests as automatically verified.

### 6. 🔗 Requirements Traceability Matrix

Connect requirements to their corresponding implementation and testing artifacts.

The proposed traceability matrix will link:

**Requirement → User Story → Acceptance Criteria → Test Case**

Example:

| Requirement ID | Requirement | User Story | Test Case | Coverage |
|---|---|---|---|---|
| FR-01 | Display reservoir water levels | US-01 | TC-001 | Linked |
| FR-02 | Generate alerts when upper thresholds are exceeded | US-02 | TC-002 | Linked |
| FR-03 | Generate alerts when lower thresholds are crossed | US-03 | TC-003 | Linked |
| NFR-01 | Meet the agreed dashboard response-time target | US-04 | TC-004 | Pending clarification |

The matrix will help users identify requirements that lack associated user stories, acceptance criteria, or test cases.

Coverage will be determined using explicit relationships between artifacts rather than merely matching similar words.

### 7. 🔄 Change Impact Analysis

One of the project's central planned features is identifying the potential impact of changes to existing requirements.

When a requirement is modified, ProjectPilot AI will compare its previous and updated versions and inspect their relationships with other project artifacts.

**Example**

Original requirement:

> Officials must receive an alert when the reservoir water level exceeds the configured upper threshold.

Updated requirement:

> Officials must receive an alert when the reservoir water level exceeds the configured upper threshold or falls below the configured lower threshold.

Potentially affected artifacts:

| Artifact | Potential Impact |
|---|---|
| FR-02 | Update the functional requirement |
| US-02 | Extend the user story to cover lower-threshold alerts |
| Acceptance Criteria | Add criteria for the lower-threshold condition |
| TC-002 | Retain the upper-threshold alert test |
| TC-003 | Add a lower-threshold alert test |
| SRS Document | Update the relevant requirements section |

The application will explain why an artifact may be affected and distinguish identified relationships from AI-suggested dependencies that require human verification.

The intended benefit is to help teams understand the consequences of changing requirements without manually reviewing every document from scratch.

### 8. 📤 Structured Document Export

Generate downloadable project documentation for review and collaboration.

Planned formats:

- **DOCX:** Editable Software Requirement Specification.
- **PDF:** Shareable requirements document.

The exported documents will include structured sections, requirement identifiers, tables, and traceability references.

The output will use an IEEE 830-inspired organization, adapted to the project's requirements and review process.

### 9. 📊 Evaluation Against a Reference Specification

ProjectPilot AI will be evaluated against a manually reviewed reference SRS for the selected use case.

The evaluation will examine:

- Requirement coverage.
- Ambiguity detection performance.
- Traceability completeness.
- Acceptance criteria and test case coverage.
- Change impact analysis precision.

The objective is to identify missing requirements and measure the quality of the generated artifacts instead of relying solely on subjective impressions.

Actual evaluation results will be documented after the implementation and experiments are complete.

---

## 🌊 Real-World Use Case: Water Resource Management

The primary demonstration scenario will focus on reservoir water-level monitoring and alerting.

This domain provides a practical context for exploring requirements engineering in systems involving sensors, monitoring dashboards, alerts, and operational decision-making.

### Initial Business Requirement

> A water management department wants a system to monitor reservoir water levels and alert officials when levels become too high or too low. The system should update its dashboard in real time, allow authorized users to access monitoring information, and generate reports. Officials should receive alerts on their phones. The system should be fast and reliable.

This initial description contains several unresolved questions.

- What constitutes a high or low water level?
- How frequently should sensor readings be collected?
- What is the maximum acceptable dashboard update delay?
- Which officials are authorized to access the system?
- Which notification channels are required?
- What reports are needed, and how frequently should they be generated?
- What measurable performance and availability targets should apply?

### Intended End-to-End Demonstration

The final demonstration will show how ProjectPilot AI:

1. Analyzes the initial requirement.
2. Identifies ambiguities and missing information.
3. Generates clarification questions.
4. Incorporates reviewed answers into the requirements.
5. Produces a structured SRS.
6. Generates user stories, acceptance criteria, and test cases.
7. Builds a requirements traceability matrix.
8. Analyzes the impact of a subsequent requirement change.
9. Exports the resulting documentation.
10. Evaluates the outputs against a manually reviewed reference specification.

**Important:** This scenario is a proposed demonstration case. Actual business rules, thresholds, and performance targets will need to be established or explicitly marked as assumptions.

---

## ⚙️ How It Works

The proposed processing pipeline consists of the following stages.

### Stage 1: Requirement Input

The user submits a business problem or initial requirements through the application interface.

### Stage 2: Requirement Extraction

The LLM helps transform the input into structured requirement candidates with identifiers, categories, descriptions, and relevant context.

### Stage 3: Ambiguity Analysis

The system identifies potentially vague, incomplete, contradictory, or untestable requirements and generates clarification questions.

### Stage 4: Human Review

The user reviews the extracted requirements, resolves ambiguities where possible, and approves the information to be used for subsequent generation.

### Stage 5: Artifact Generation

The system generates the SRS, user stories, acceptance criteria, and UAT test cases from the reviewed requirements.

### Stage 6: Traceability Construction

Structured relationships connect each requirement with its associated user stories, acceptance criteria, and test cases.

### Stage 7: Change Impact Analysis

When a requirement changes, the system compares versions, identifies explicitly linked artifacts, and proposes additional potential impacts for review.

### Stage 8: Export and Evaluation

The user exports the generated documentation, while the evaluation pipeline compares the outputs against a manually reviewed reference specification.

---

## 🏗️ System Architecture

The intended architecture separates the user interface, LLM-assisted processing, structured project data, and validation logic.

```text
                 ┌──────────────────────────┐
                 │       User Interface     │
                 │         Streamlit        │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │   Requirement Processing │
                 │   Input & Extraction     │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │    LLM-Assisted Analysis │
                 │ Ambiguity & Clarification│
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │   Artifact Generation    │
                 │ SRS, Stories, Test Cases │
                 └────────────┬─────────────┘
                              │
                              ▼
                 ┌──────────────────────────┐
                 │ Structured Requirements  │
                 │ IDs & Traceability Links │
                 └────────────┬─────────────┘
                              │
                 ┌────────────┴─────────────┐
                 ▼                          ▼
       ┌──────────────────┐      ┌──────────────────┐
       │ Change Impact    │      │ Document Export  │
       │ Analysis         │      │ DOCX / PDF       │
       └──────────────────┘      └──────────────────┘
                             
                 ┌──────────────────────────┐
                 │   Evaluation & Testing   │
                 │ Reference SRS Comparison │
                 └──────────────────────────┘
```

The architecture is a proposed design and will evolve as implementation decisions are finalized.

---

## 🛠️ Technology Stack

The initial implementation is planned around the following technologies.

| Technology | Intended Purpose |
|---|---|
| Python | Core application logic |
| Streamlit | Interactive application interface |
| LLM API | Natural-language analysis and artifact generation |
| Prompt Engineering | Structured, task-specific generation workflows |
| Pydantic | Structured output validation |
| Pandas | Requirements tables and evaluation analysis |
| python-docx | Editable DOCX document generation |
| ReportLab | PDF generation |
| Git and GitHub | Version control and project documentation |

Additional technologies, such as embeddings and a vector database, may be introduced if retrieval from domain-specific documents becomes necessary.

The final stack will reflect the implemented solution rather than every technology listed here.

---

## 📁 Planned Project Structure

```text
ProjectPilot-AI/
│
├── app.py
├── requirements.txt
├── README.md
├── .env.example
│
├── src/
│   ├── requirements_analyzer.py
│   ├── ambiguity_detector.py
│   ├── srs_generator.py
│   ├── user_story_generator.py
│   ├── test_case_generator.py
│   ├── traceability.py
│   ├── change_impact.py
│   └── document_exporter.py
│
├── data/
│   └── water_management_case.json
│
├── evaluation/
│   ├── reference_srs.md
│   ├── evaluation_dataset.json
│   └── evaluate.py
│
├── tests/
│   ├── test_requirements.py
│   ├── test_traceability.py
│   └── test_change_impact.py
│
└── docs/
    └── sample_outputs/
```

This structure represents the intended organization. Files will be added as their corresponding components are implemented.

---

## 📈 Evaluation Strategy

A central objective of this project is to evaluate whether the generated artifacts are complete, consistent, and useful.

A manually reviewed reference SRS will serve as the comparison baseline for a predefined set of requirements and scenarios.

### Planned Metrics

**1. Requirement Coverage**

Measures the proportion of applicable reference requirements correctly represented in the generated specification.

`Requirement Coverage = Correctly Represented Reference Requirements / Total Reference Requirements`

**2. Ambiguity Detection**

Measures how effectively the application identifies predefined ambiguities in a reviewed evaluation dataset.

Precision and recall will be calculated where the evaluation dataset provides suitable labels.

**3. Traceability Coverage**

Measures the proportion of applicable requirements with the expected links to their associated stories and test cases.

**4. Change Impact Precision**

Measures the proportion of artifacts flagged as affected that are confirmed to be affected according to the manually reviewed reference analysis.

**5. Test Case Coverage**

Measures the proportion of applicable reference requirements covered by valid, relevant test cases.

### Evaluation Methodology

The planned evaluation process is:

1. Prepare a manually reviewed reference SRS.
2. Define expected requirements, ambiguities, and artifact relationships.
3. Run the application on the same initial business scenario.
4. Compare generated artifacts against the reference.
5. Review incorrect, missing, and unsupported outputs.
6. Record metrics and document limitations.

No evaluation scores are claimed at this stage. Results will be published after the evaluation has been performed.

---

## 🎯 Expected Impact

ProjectPilot AI is intended to help teams:

- Reduce repetitive requirements documentation work.
- Identify ambiguous requirements earlier.
- Improve the consistency of generated project artifacts.
- Connect requirements with their associated testing activities.
- Identify potential consequences of changing requirements.
- Produce structured documentation for stakeholder review.
- Support more systematic project planning.

The application is intended to assist business analysts, project coordinators, software teams, and other stakeholders. It is not intended to replace business judgment or formal requirements approval.

---

## 🗺️ Development Roadmap

The project will be developed incrementally.

- [ ] Initialize repository and application structure.
- [ ] Implement the Streamlit interface.
- [ ] Integrate an LLM API.
- [ ] Implement structured requirement extraction.
- [ ] Implement ambiguity detection and clarification questions.
- [ ] Generate SRS documents.
- [ ] Generate Agile user stories and acceptance criteria.
- [ ] Generate UAT test cases.
- [ ] Build the requirements traceability matrix.
- [ ] Implement requirement versioning and change impact analysis.
- [ ] Add DOCX and PDF exports.
- [ ] Create the manually reviewed reference SRS.
- [ ] Implement automated evaluation metrics.
- [ ] Add unit and integration tests.
- [ ] Document the end-to-end demonstration.
- [ ] Deploy a live demo.
- [ ] Publish evaluation results and sample outputs.

Progress will be updated as each feature becomes functional and is tested.

---

## 🚀 Getting Started

The application is currently in development. Setup instructions will be finalized when the initial implementation and dependency list are available.

The intended setup workflow is:

### Prerequisites

- Python 3.10 or a compatible supported version.
- Git.
- An API key for the selected LLM provider.

### Installation

Clone the repository:

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd ProjectPilot-AI
```

Create a virtual environment:

```bash
python -m venv .venv
```

Activate it on macOS or Linux:

```bash
source .venv/bin/activate
```

On Windows:

```bash
.venv\Scripts\activate
```

Install dependencies after `requirements.txt` has been created:

```bash
pip install -r requirements.txt
```

Configure the required API credentials using environment variables. Keep secrets in a local `.env` file or the deployment platform's secret-management settings; never commit them to GitHub.

Once the application entry point is implemented, the expected launch command will be:

```bash
streamlit run app.py
```

These are planned setup instructions and will be verified against the actual implementation.

---

## ⚠️ Limitations and Responsible Use

Generative AI can produce incorrect, incomplete, inconsistent, or unsupported requirements.

ProjectPilot AI will therefore be designed with the following principles:

- Human review before requirements are treated as approved.
- Explicit identification of assumptions and unresolved questions.
- Structured output validation.
- Traceability checks using explicit artifact relationships.
- Clear distinction between generated test cases and executed tests.
- Review of AI-suggested change impacts before accepting them.
- Evaluation against manually reviewed reference artifacts.

The application is a decision-support tool. It cannot independently guarantee regulatory compliance, software correctness, or the completeness of a requirements specification.

The water management demonstration is a software engineering example, not a validated operational monitoring or disaster-warning system.

---

## 🔮 Future Enhancements

Potential extensions include:

- Retrieval-Augmented Generation (RAG) for organization-specific requirements and documentation.
- Support for uploading existing SRS documents.
- Comparison of multiple document versions.
- Advanced dependency graphs for change impact visualization.
- Export to project-management tools.
- Collaboration and stakeholder review workflows.
- Additional case studies involving agriculture, enterprise applications, and IoT systems.

These enhancements will be considered after the core workflow is implemented and evaluated.

---

## 👨‍💻 Project Objective

ProjectPilot AI explores how Generative AI can support practical software engineering and business analysis workflows beyond conversational question answering.

Its central focus is the relationship between requirements quality, traceability, testing, and change management.

By combining LLM-assisted analysis with structured data, explicit artifact relationships, and measurable evaluation, the project aims to demonstrate a practical approach to building more reliable AI-assisted requirements engineering tools.

---

**ProjectPilot AI — From Business Requirements to Traceable Software Specifications.**
