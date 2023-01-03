# Aras Code Templates
<div class='editDate'>Created/Updated: 2021-10-14</div>

- [Aras Code Templates](#aras-code-templates)
  - [Introduction](#introduction)
  - [Simple Template](#simple-template)
  - ["Processing" template](#processing-template)
  - [Simple VBMain template](#simple-vbMain-template)

## Introduction
The "inline" coding in Aras is great for several reasons, but it has some drawbacks. When you want to write non-trivial code the "single"-method can easily get too long with to "much going on" to be readable. So I often use different templates/boiler plates to be able to write cleaner code.
It would be more ideal to handled this with an extended "core dll", which would remove most boilerplate code. 

## Simple Template
``` c#
        Init();
        // TODO: Write code

    } // End Main Method

    private Innovator Inn;

    private void Init() {
        Inn = this.getInnovator();
    }

} // End Main Class

class fin {
    void method() {


```

## "Processing" template
``` c#
        Init(CCO);
        foreach (Item item in GetItemsToProcess()) {
            try {
                ProcessItem(item);
                // 95% of my cases I don't want to make a partial commit. 
                //But left it here in the template for the 5%
                //Commit();   
                Log($"Processed item: {item.getProperty("keyed_name")}");
            }
            catch (Exception ex) {
                LogException(item,ex);
                // TODO: rethrow/return newError or continue loop
                // depending on requirements
            }
        }
        return this;
    } // End Main Method

    private Innovator Inn;
    private const string MethodName = "MY_Process_Template"; //TODO: Replace with your method name
    private Aras.Server.Core.CallContext CC;

    private void Init(Aras.Server.Core.CallContext cco) {
        Inn = this.getInnovator();
        CC = cco;
    }

    private List<Item> GetItemsToProcess() {
        var items = new List<Item>();
        // TODO: Replace or implement
        return items;
    }
    
    private Item ProcessItem(Item item) {
        // TODO: Replace or implement
        return item;
    }

    private void Commit() {
        CC.Variables.InnDatabase.CommitTransaction();
    }
    
    private void LogException(Item sourceItem, Exception ex) {
        string keyedName = sourceItem.getProperty("keyed_name", "(No keyed name)");
        string errorMessage = $"Error updating {keyedName} : {ex.ToString()}";
        LogError(errorMessage);        
    }
    
    private void LogError(string message) {
        Log(message);
        string fileName = "ERROR_" + MethodName;
        CC.Utilities.WriteDebug(fileName,message);
    }
    
    private void Log(string message) {
        CC.Utilities.WriteDebug(MethodName,message);
    }

} // End Main Class

class fin {
    void method() {
        
```

## Simple VBMain template
``` VB
' MethodTemplateName=VBMain;

Private Inn As Innovator
Private MethodName As String = "MY_METHOD"  ' TODO: Replace with a real method name
    
Function Main() As Item
    Try
        Inn = Me.GetInnovator()
        
        ' TODO: Implment code
        
    Catch ex As Exception
        CCO.Utilities.WriteDebug("ERROR_" & MethodName, ex.ToString)
        Throw
    End Try
End Function
```
