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


Configuration

1. Deploy the Apex Class

Deploy the Apex class to your Salesforce org using VS Code, Salesforce CLI, Developer Console, or your preferred deployment method.

⸻

2. Create or Open a Flow

Navigate to:

Setup → Flows

Create a new Flow or open an existing Flow where you want to perform the rollup calculation.

⸻

3. Add the Apex Action

Add an Action element to the Flow.

Search for:

Rollup Summary - Multiple Calculations

Select the Action.

⸻

4. Configure the Parent and Child Relationship

Configure the following common inputs:

Parent Record Id

Provide the Id of the parent record for which the rollup is being calculated.

Example:
{!$Record.Parent_Lookup__c}
Child Object API Name

Enter the API name of the object containing the records that should be included in the calculation.

Example:
Child_Object__c

Parent Lookup Field API Name

Enter the API name of the Lookup or Master-Detail field on the child object that references the parent.

Example:
Parent__c

The Action automatically uses this relationship to retrieve only records related to the specified parent.

⸻

Configure Calculation 1

Calculation 1 is required.

Calculation Type

Enter one of the supported operations:
SUM
COUNT
MIN
MAX
AVG

Aggregate Field

Enter the API name of the numeric field that should be calculated.

Example:
Amount__c

Relationship field paths are also supported where applicable:
Relationship__r.Amount__c

For COUNT, this field can be left blank.

Filter

Optionally provide an additional SOQL condition.

For example:
Status__c = 'Active'
Do not include the WHERE keyword.

The Action automatically combines the parent relationship condition with your additional filter.
