# Code Snippets
<p class='editDate'>Created: 2021-10-27</p>
<p class='editDate'>Edited: 2021-11-17</p>

Some code snippets I don't frequently enough to remember but needs every know an then.

## C#

### Init List
``` cs
private List<string> MyCars = new List<string>()
{
    "BMW",
    "Volkswagen",
    "Volvo"
};
```

### List To Comma Separated string
``` cs
List<string> MyCars = new List<string>(){ "BMW", "Volkswagen", "Volvo"};

string cars = string.Join(",", MyCars);
// "BMW,Volkswagen,Volvo"

```