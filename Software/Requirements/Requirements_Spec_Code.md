<style>
    tr,td {
        border-bottom-style: solid;
    }
    .strike {
        text-decoration: line-through; color:red;
    }
    
</style>

# Requirements, Specifications and Implementation

## Introduction
As a software developer I struggle with get the requirements from customers. The requirements are often absent, which is bad. Because requirements helps to fill in the gaps in the specification and makes it possible to find better alternatives than handed specification.

I will illustrate this with a simple example. 

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
|Requirement | On Valentines Day I want to show my appreciation for my wife. **Budget $50** |
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


