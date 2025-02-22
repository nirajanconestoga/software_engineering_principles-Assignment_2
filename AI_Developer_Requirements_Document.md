# AI Developer Requirements Document

## Purpose
This document outlines the user, functional, and system requirements for an AI developer who generates training data using web scraping. The goal is to address the challenges of categorizing training questions, ensuring data balance, and detecting biases to improve AI model performance.

## 1. Requirements Breakdown
Each section includes the **Requirement**, **Assumptions & Validation**, **Preliminary Tasks**, and the associated **Functional** and **System Requirements** to ensure clear connection between user needs, solution functionalities, and technical implementations.
The functional requirements describe what the system should provide to fulfill the AI developer’s needs, while the system requirements describe the the underlying technical infrastructure enabling those functions.

### 1.1 Requirement: Automated Categorization of Training Data
**User Story:** As an AI developer, I want training questions to be automatically categorized by topic using metadata tagging so that I can easily organize and retrieve relevant data for model training.

#### Assumptions & Validation
- **Assumption:** The system will reduce manual sorting time through effective automated categorization.
- **Validation Methods:**
  - Conduct pilot tests with 3 sample datasets (10,000 entries each) targeting an F1-score of at least 85%.
  - Review categorization results across various question formats.
  - Analyze misclassified entries to refine the categorization model.
  - Verify categorized datasets with subject matter experts.

 #### Preliminary Tasks
- Interview AI developers to identify pain points in manual categorization.
- Review inconsistencies in previous dataset tagging methods.
- Explore existing metadata standards and tools.
- Consider a low-tech solution such as standardized spreadsheets.
- If inadequate, implement the simplest technology solution such as Python-based NLP models.

#### Functional Requirements (For AI Developers)
- The system shall allow users to upload datasets and automatically categorize training questions using metadata tags.
- The system shall provide an interface for users to review, edit, and approve categorized questions.
- Categorization shall achieve an F1-score of at least 85% on validation datasets.

#### System Requirements (Supporting Functionalities)
- The system shall use NLP libraries (e.g., spaCy) for implementing categorization models.
- Categorized data shall be stored in a relational database (e.g., PostgreSQL) for quick access by users.
- The backend shall handle batch uploads and provide retraining capabilities.

### 1.2 Requirement: Dataset Upload and Structured Storage
**User Story:** As an AI developer, I want to upload a dataset and have the system automatically structure and store categorized training questions so that I can efficiently retrieve and manage large volumes of data.

#### Assumptions & Validation
- **Assumption:** Structured storage will enhance data retrieval speeds.
- **Validation Methods:**
  - Test uploads with datasets up to 10 million entries.
  - Ensure retrieval times remain under 200ms during user queries.
  - Run concurrent upload and query stress tests.

#### Preliminary Tasks
- Interview AI developers about dataset storage challenges.
- Analyze inefficiencies in previous storage methods.
- Explore suitable indexing solutions.
- Consider a low-tech solution (e.g., structured CSV files).
- If inadequate, implement a technology solution such as Elasticsearch.

#### Functional Requirements (For AI Developers)
- Users shall be able to upload datasets through a web interface or API.
- The system shall automatically structure uploaded datasets for easy retrieval.
- Users shall retrieve categorized data with sub-200ms response times.

#### System Requirements (Supporting Functionalities)
- The system shall use Elasticsearch for fast search and retrieval.
- Data shall be stored using scalable solutions (e.g., AWS S3).
- Automatic indexing shall be triggered upon user uploads.

---

### 1.3 Requirement: Logical Separation of Questions and Answers
**User Story:** As an AI developer, I want training questions to be stored separately from answers so that I can ensure unbiased model training and independent validation of AI performance.