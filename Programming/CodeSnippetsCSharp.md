# Code Snippets
<div class='editDate'>Created: 2021-10-27</div>
<div class='editDate'>Edited: 2021-11-17</div>

Some code snippets I don't frequently enough to remember but needs every know an then.
- [Code Snippets](#code-snippets)
  - [C Sharp](#c-sharp)
    - [Init List](#init-list)
    - [List To Comma Separated string](#list-to-comma-separated-string)

## C Sharp


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