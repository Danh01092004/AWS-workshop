# Requirements Document

## Introduction

This specification addresses the need to fix missing Hugo index files in the Workshop section so that when running locally, all Workshop subsections are displayed properly without 404 errors or missing navigation.

## Glossary

- **Hugo**: A static site generator used to build the documentation website
- **Workshop**: A hands-on tutorial section with 11 subsections covering AWS CDK deployment
- **Content Directory**: The `content/` folder containing all markdown source files for Hugo
- **Index File**: A `_index.md` or `_index.vi.md` file that defines a section in Hugo
- **Front Matter**: YAML metadata at the top of markdown files (title, weight, date, etc.)

## Requirements

### Requirement 1

**User Story:** As a developer, I want all Workshop subsection folders to have proper index files, so that Hugo can build and display the Workshop section correctly.

#### Acceptance Criteria

1. WHEN the Workshop directory is scanned THEN the system SHALL verify that the main `_index.md` and `_index.vi.md` files exist in `content/5-Workshop/`
2. WHEN each Workshop subsection folder is checked THEN the system SHALL confirm both `_index.md` and `_index.vi.md` files are present
3. WHEN any missing index file is detected THEN the system SHALL create it with appropriate front matter and placeholder content
4. WHEN all index files are created THEN the system SHALL ensure proper weight ordering from 5.1 to 5.11

### Requirement 2

**User Story:** As a content creator, I want all Workshop index files to have valid front matter, so that Hugo can properly parse and display the navigation structure.

#### Acceptance Criteria

1. WHEN an index file is created THEN the system SHALL include required front matter fields: title, date, weight, chapter, and pre
2. WHEN the weight field is set THEN the system SHALL ensure it matches the subsection number for proper ordering
3. WHEN the pre field is configured THEN the system SHALL follow the pattern " <b> 5.X. </b> " where X matches the subsection number
4. WHEN the chapter field is set THEN the system SHALL use false for subsections and true for the main Workshop index

### Requirement 3

**User Story:** As a site visitor, I want the Workshop section to display all 11 subsections in order, so that I can follow the tutorial step by step.

#### Acceptance Criteria

1. WHEN the Hugo site is built THEN the system SHALL include all 11 Workshop subsections in the navigation
2. WHEN a subsection link is clicked THEN the system SHALL navigate to the correct page without 404 errors
3. WHEN the Workshop index is viewed THEN the system SHALL display links to all subsections in numerical order
4. WHEN bilingual content is enabled THEN the system SHALL display both English and Vietnamese versions correctly
