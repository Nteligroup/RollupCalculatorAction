Salesforce Flow Rollup Summary - Multiple Calculations

Description

A reusable Apex Invocable Action for Salesforce Flow that performs rollup and aggregate calculations on related records.

Salesforce’s standard Roll-Up Summary fields are primarily available for Master-Detail relationships. This utility provides a flexible alternative that can also work with Lookup relationships, allowing aggregate calculations to be performed directly from Flow.

The Action supports SUM, COUNT, MIN, MAX, and AVG and can perform up to five independent calculations in a single Flow Action.

This helps keep Flows simple by reducing the need for multiple Get Records, Loops, Assignments, and calculation elements.

Features

* Supports SUM, COUNT, MIN, MAX, and AVG
* Supports Lookup and Master-Detail relationships
* Perform up to 5 calculations in a single Flow Action
* Supports a different filter condition for each calculation
* Supports direct fields and relationship field paths
* Supports optional SOQL filter conditions
* Returns individual results for each configured calculation
* Returns Success and Message outputs for error handling and troubleshooting
* Can be reused across different Salesforce objects
* Helps reduce unnecessary Get Records, Loops, and Assignments in Flow
* Designed to provide a reusable alternative when native Roll-Up Summary fields cannot be used

How It Works ? 

The Action requires three common inputs that define the relationship:

Parent Record Id
Child Object API Name
Parent Lookup Field API 

You can then configure up to five independent calculations:

Calculation 1
    Calculation Type
    Aggregate Field
    Filter

Calculation 2
    Calculation Type
    Aggregate Field
    Filter

...

Calculation 5
    Calculation Type
    Aggregate Field
    Filter

Each calculation returns its own result:

Calculation 1 → Result 1
Calculation 2 → Result 2
Calculation 3 → Result 3
Calculation 4 → Result 4
Calculation 5 → Result 5
