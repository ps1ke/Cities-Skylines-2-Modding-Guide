# Game.UI.Widgets.ISettable

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** interface abstract public  

**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface ISettable : Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable
{
    public System.Boolean shouldTriggerValueChangedEvent { get; }

    public abstract System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
}
```


## Properties

- `public System.Boolean shouldTriggerValueChangedEvent { get }`  

```csharp
public System.Boolean shouldTriggerValueChangedEvent { get; }
```


## Methods

- `public abstract SetValue(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public abstract System.Void SetValue(Colossal.UI.Binding.IJsonReader reader);
```


