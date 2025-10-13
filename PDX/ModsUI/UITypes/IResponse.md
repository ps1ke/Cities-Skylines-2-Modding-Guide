# PDX.ModsUI.UITypes.IResponse

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IResponse
{
    public System.String RequestId { get; }
    public PDX.ModsUI.UITypes.Error Error { get; set; }
    public System.Boolean Success { get; }

}
```


## Properties

- `public System.String RequestId { get }`  

```csharp
public System.String RequestId { get; }
```

- `public PDX.ModsUI.UITypes.Error Error { get; set }`  

```csharp
public PDX.ModsUI.UITypes.Error Error { get; set; }
```

- `public System.Boolean Success { get }`  

```csharp
public System.Boolean Success { get; }
```


