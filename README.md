A reusable Apex Invocable Action for Salesforce Flow that provides rollup and aggregate functionality for relationships where standard Salesforce Roll-Up Summary fields may not be available.
Salesforce native Roll-Up Summary fields require a Master-Detail relationship. This utility can also perform aggregate calculations across Lookup relationships, making it useful for more flexible data models.

**Features**
Supports SUM, COUNT, MIN, MAX, and AVG.
Supports standard Lookup and Master-Detail relationships.
Supports relationship field paths.
Supports optional SOQL filter conditions.
Performs up to five calculations in a single Flow Action.
Returns a separate result for each configured calculation.
Returns Success and Message outputs for troubleshooting.
Designed to be reusable across different Salesforce objects and Flows.
Reduces the need for Get Records, Loops, Assignments, and multiple Action elements.
