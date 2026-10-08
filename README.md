INX: Signal in the Noise

Challenge

Organizations receive large volumes of messages every day. Many messages are routine, while others describe the same problem in different ways. Some are urgent, and some may appear harmless individually but reveal a wider issue when considered together.

Reading every message manually is slow, and looking only at recent messages can cause important patterns to be missed.

Build a system that processes a collection of unstructured messages and turns them into signals that people can investigate and act on.

The system should help an organization understand:

* What are people talking about?
* Which issues matter most?
* Which messages are related?
* Are multiple people reporting the same underlying problem?
* Is a new issue beginning to emerge?
* Why did the system consider something important?

The core flow is:

MESSAGES
    ↓
UNDERSTAND
    ↓
CLASSIFY
    ↓
GROUP
    ↓
PRIORITIZE
    ↓
FIND PATTERNS
    ↓
ACTIONABLE SIGNALS

The system should not only answer questions about individual messages. It should help a user understand what is happening across the collection.

Choose Your Scenario

Choose the type of messages your system will analyze.

Examples include:

* Customer support messages
* Product feedback
* Campus service complaints
* Public service reports
* Internal employee requests
* Incident reports

The scenario should provide meaningful categories and priorities for the system to work with.

What to Build

1. Message Input

The system must accept unstructured text messages.

Each message should contain enough information for the system to analyze it.

For example:

I have tried resetting my password three times,
but the verification email never arrives.

The exact input format is up to your team.

2. Categorization

Messages must be assigned to one or more meaningful categories.

For example:

* Authentication
* Billing
* Delivery
* Technical Issue
* Account

Your team must define the taxonomy. The categories should make sense for the scenario you selected.

3. Priority

The system must identify high-priority messages.

The priority model may consider factors such as:

* Severity
* Impact
* Frequency
* Urgency
* Risk
* Other factors chosen by the team

The priority policy must be defined and explainable.

For example, simply displaying:

Priority: HIGH

is not sufficient if the system cannot explain why the message received that priority.

4. Similar Messages

Messages describing the same underlying issue should be discoverable as a group.

For example:

"I can't log in."
"My password works but the site keeps rejecting me."
"The login page says my credentials are invalid."

These messages may represent the same underlying issue even though they use different wording.

The system should provide a useful way for users to identify related messages.

5. Search and Filtering

Users should be able to investigate the message collection.

At minimum, provide useful ways to search or filter based on information extracted by the system.

For example:

Priority: High
Category: Authentication
Status: Unresolved

The exact interface is up to your team.

6. Find Emerging Problems

The system should help identify recurring or emerging issues.

For example:

MONITORING PERIOD
Authentication issues
██████████████████  184
Billing issues
██████████           96
Delivery issues
████                     31

The specific visualization is not required. What matters is whether the system helps a user notice that an issue is recurring or becoming more significant.

Constraints

No ARC Dataset

ARC will not provide a custom message dataset.

You may:

* Generate synthetic messages.
* Create your own test collection.
* Use legally usable public or sample data.

Do not use private or confidential messages.

Define Your Policy

Your team must document:

* Categories
* Priority logic
* Similarity and grouping approach
* What qualifies as an emerging issue

These decisions should be understandable to another developer.

AI Is Optional

You may use:

* Rules
* NLP
* Machine learning
* Embeddings
* Clustering
* LLMs
* Hybrid approaches

Using an LLM does not provide extra credit by itself. The implementation should demonstrate how the chosen approach solves the problem.

Explainability

When the system identifies an important message or issue, the user should have a basis for understanding the result.

For example:

HIGH PRIORITY
Category:
Authentication
Why:
• 47 similar reports
• Issue increased 4× this week
• Multiple users unable to access accounts

The specific explanation mechanism is up to your team.

Evaluation

The solution will be evaluated on the following areas.

Classification

Are messages categorized meaningfully for the selected scenario?

Prioritization

Does the system surface genuinely important cases?

Grouping

Can related messages be recognized when their wording differs?

Discovery

Can a user discover an issue they were not explicitly searching for?

Explainability

Can the system explain why something was prioritized or grouped?

Engineering

Can the team explain its approach, limitations, and trade-offs?

Implementation Choices

There is no prescribed implementation.

Your team decides:

* Message schema
* Domain
* Category taxonomy
* Priority model
* Similarity method
* Grouping strategy
* Trend detection
* Interface
* Storage
* Processing architecture
* AI/ML usage

Optional Enhancements

The following are optional:

* Multilingual message processing
* Sentiment analysis
* Emotion detection
* Topic discovery
* Emerging issue detection
* Response recommendations
* Trend forecasting
* Automatic summaries
* Human feedback loop
* Duplicate detection
* Issue lifecycle tracking

The quality of the core signal matters more than the number of optional features implemented.

Acceptance Criteria

Your solution must demonstrate all of the following:

* [ ]	Unstructured messages can be ingested.
* [ ]	Messages are categorized using a documented taxonomy.
* [ ]	Messages receive a defined priority or severity.
* [ ]	High-priority messages can be identified.
* [ ]	Similar messages can be grouped or discovered.
* [ ]	Users can search or filter the collection.
* [ ]	Recurring or emerging issues can be identified.
* [ ]	Important classifications or priorities have an explanation.
* [ ]	The system works on a meaningful message collection.
* [ ]	At least one non-obvious pattern can be demonstrated.
* [ ]	The complete flow can be demonstrated end-to-end.

Repository Requirements

The repository must contain enough information for another developer to understand and run the solution.

At minimum, include:

README.md
ARCHITECTURE.md
DECISIONS.md
TESTING.md

ARCHITECTURE.md

Document:

* System architecture
* Message processing pipeline
* Classification
* Grouping
* Priority calculation
* Trend or emerging-issue detection
* Storage
* User interface

Include an architecture diagram.

DECISIONS.md

Document important technical decisions and trade-offs.

For example:

* Why was this taxonomy selected?
* Why was this priority model selected?
* Why was this similarity approach selected?
* Why was this model or algorithm selected?
* How was the balance between accuracy and explainability handled?

TESTING.md

Document:

* Classification tests
* Priority tests
* Similarity and grouping tests
* Search and filter tests
* Trend detection tests
* Edge cases
* Known limitations

Demo Expectations

The demo should show the system discovering something useful from the message collection.

A recommended flow is:

1. Introduce the chosen scenario
        ↓
2. Load the message collection
        ↓
3. Show classification
        ↓
4. Show priority
        ↓
5. Open a group of similar messages
        ↓
6. Investigate an important issue
        ↓
7. Show the reason behind its priority
        ↓
8. Show a recurring or emerging pattern
        ↓
9. Demonstrate search/filtering
        ↓
10. Explain the architecture
        ↓
11. Defend the approach

A strong demonstration should reveal something that is difficult to notice by reading the raw messages individually.

Event-Day Challenge

During evaluation, judges may provide or introduce a small batch of messages containing several differently worded reports of the same underlying issue.

The system may be asked to:

* Find the related messages.
* Identify the underlying issue.
* Explain its priority.
* Show whether the issue appears to be growing.
* Distinguish it from unrelated messages.

The system should demonstrate how it reaches its conclusions rather than relying on assumptions about what the judges intended.

Rules

* Build your own solution.
* AI-assisted development is allowed.
* Public libraries and tools are allowed.
* Do not depend on an ARC-owned dataset or backend.
* Do not submit private or confidential data.
* Do not commit secrets.
* Be prepared to explain the implementation.
* Core requirements take priority over optional features.

Final Checklist

Before submission, verify the following:

* [ ]	Message ingestion works.
* [ ]	The category system is defined.
* [ ]	Messages are categorized.
* [ ]	Priority logic is defined.
* [ ]	High-priority messages are surfaced.
* [ ]	Similar messages can be investigated.
* [ ]	Search and filtering work.
* [ ]	Recurring or emerging issues can be identified.
* [ ]	Important results have explanations.
* [ ]	Test data is sufficient to demonstrate the system.
* [ ]	At least one meaningful pattern is demonstrated.
* [ ]	Edge cases have been tested.
* [ ]	No secrets are committed.
* [ ]	Architecture is documented.
* [ ]	Technical decisions are documented.
* [ ]	Testing is documented.
* [ ]	The demo is ready.

INNOVEX | ARC Club