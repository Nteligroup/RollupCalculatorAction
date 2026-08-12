Built a reusable Rollup/Aggregate Invocable Action for Flow with help from Claude. It allows us to perform SUM, COUNT, MAX, MIN, and AVG on child records—for example, summing Purchase Order Line quantities related to an Opportunity.
The main benefit is that we can do this using just one Action element in Flow, without needing Get Records, Loops, or Assignments. It also works with regular Lookup relationships, not just Master-Detail.
Sharing the code and setup steps below in case anyone else finds it useful or wants to reuse it. Thanks

Configuration Steps

1. Setup → Apex Classes → New. Or through Developer Console.
2. In Flow Builder, add an Action and search for “Rollup Calculator (Object/Field/Operation)”.
3. Configure the inputs:

Object API Name: Purchase_Order_Line__c
Field API Name: Quantity__c
Operation: SUM
        (It also supports COUNT, MAX, MIN, and AVG.)
 Filter Condition ,  For example:
        Purchase_Order__r.Opportunity__c = '{!$Record.Id}'
4. Under Store Output Values, map the output values to Flow variables:

Result Value
Record Count
Success
Error
