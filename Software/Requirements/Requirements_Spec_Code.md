<style>
    td {
        border-bottom-style: solid;
        border-color:grey;
    }
    .strike {
        text-decoration: line-through; color:red;
    }
    
</style>

# Requirements, Specifications and Implementation
Created/Updated: 2020-10-15

## Introduction
As a software developer I struggle with getting the requirements from customers. The requirements are often absent, which is bad. Because requirements helps to fill the gaps in the specification and makes it possible to find better alternatives than handed specification.

I will illustrate this with a simple example. And make a summary with some conclusions on why I value requirements so much more than specifications.

## Example

To start with a typical request will be written like: "I need 10 roses, can you fix this?" 

If I would be able to extract the requirement and try to break it down, the initial result could be something like the table below. 


### Initial setup 
<table>
    <th>Type</th><th>Description</th>
    <tr>
        <td>Requirement</td><td> On Valentines Day I want to show my appreciation for my wife</td>
    </tr>
    <tr>
        <td>Specification</td><td>Buy 10 roses at Greta's flower shop and deliver to wife</td>
    </tr>
    <tr>
        <td>Code/Interface</td><td>1. Go to store<br />2. Pick up product<br />3. Pay for product<br />4. Deliver product</td>
    </tr>
    <tr>
        <td>Implementation</td><td>1. Take bike to Greta's store<br />2. Pickup roses<br />3. Pay with cash<br />4. Deliver flowers</td>
    </tr>
</table>



I will run this through a scenario to show the volatility of the different types, when changes occur.

### Change due to bad quality

The first change comes when the first delivery is done and the roses are ruined, due to it was delivered with a bike.

You could say that the implementation does not satisfy the requirement even though the specification was fulfilled.
<table>
<th>Type</th><th>Description</th>
<tr><td>Implementation</td><td><strong>1. Take <span class ='strike'>bike</span> taxi to Greta's store</strong><br />2. Pickup roses<br />3. Pay with cash<br />4. Deliver flowers</td></tr>
</table>


### Change due to high cost

Now there will be complaint of the high cost, due to that biking was replaced with a taxi ride.

Change requirement, spec, and implementation. Buy at a closer store with walking distance.
That it was specified at Greta's was not important really, it was just a suggestion to the implementation by the customer.

|Type   | Description                                                  |
|---|---|
|Requirement | On Valentines Day I want to show my appreciation for my wife. <span class='new'>Budget $50</span> |
|Specification   |  Buy 10 roses at <span class='strike'>Greta's</span> flower shop and deliver to wife  |
|Implementation | 1. **Walk to Penny's** <span class='strike'>Greta's</span> store<br />2. Pickup roses<br />3. Pay with cash<br />4. Deliver flowers |


### Change due to change in payment method



### Change due to new vehicle available





### Change due to cat eating flowers

Note: This is what my initial suggestion would have been. Due to the benefit that it would also be enjoyed by the customer and not only the customers wife. :)

TODO: Change Spec and implementation. Buy chocolate

### Change due to kids eating chocolate



TODO: Change Spec, Code and implementation. Buy a spa treatment/massage

### Summary number of changes of each type

## Conclusion
As you can see; well defined requirements rarely changes, specifications change from time to time and implementations change frequently.
Implementation/Code are - should always be - managed with Version Controls System (VCS) such as git. This keeps control of the changes and the "truth". Specifications and Requirements does not have common system to keep them up to date. Specifications often rot - which makes them full of lies. The documentation for the example would typically look something like the list below.

<table>
    <th>Type</th><th>Description</th>
    <tr>
        <td>Requirement</td><td> On Valentines Day I want to show my appreciation for my wife</td>
    </tr>
    <tr>
        <td>Specification</td><td>Buy 10 roses at Greta's flower shop and deliver to wife</td>
    </tr>
    <tr>
        <td>Code/Interface</td><td>1. Go to store<br />2. Pick up and deliver product<br />3. Pay for product</td>
    </tr>
    <tr>
        <td>Implementation</td><td>1. Check spa treatment in customers vicinity.<br />2. Order gift voucher to customer address<br />3. Pay bill</td>
    </tr>
</table>

Code/Implementation is the most truthful documentation. But it - normally - does not answer the WHY question, while it accurate answers the WHAT an HOW questions. The requirement is the best to answer the WHY question.
So the code/implementation combined with requirements answers the WHY, WHAT and HOW.

### How to write good requirements
Writing good requirements may not be as easy as it seems, so I try to start with the User Story format.
As I would start this user story:
**As a software developer** I most of the time need more information in order to implement a request.

With this start you could continue to break it down/be more specific. How I get the information can have several different solution. E.g. 1. talking to the requester, 2. being handed a more specific specification (to this day I have not seen a complete non-trivial specification), 3. being handed requirements. 
* Alternative 1 is the one requiring least amount of work with the probable drawback the documentation will be lacking.
* Alternative 2 is the hardest and slowest, since there often requires a few iterations before all needed specification are in place. 
* Alternative 3 seems to be hard to accomplish since most of the times requirements and specifications are mixed together. But if accomplished the WHY question will be documented - which is good to have in the future when someone wonder why something was implemented. With alternative 1 you need to rely on that someone remember why. (The invention of the IT-tool writing 5000 years ago was a very good invention). Alternative 2 does not answer the WHY, and the specification might have been tainted with lies.
