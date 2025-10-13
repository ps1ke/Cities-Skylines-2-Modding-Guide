# PDX.ModsUI.UITypes.Response

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `PDX.ModsUI.UITypes.IResponse`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class Response : PDX.ModsUI.UITypes.IResponse
{
    private System.String <RequestId>k__BackingField;
    private PDX.ModsUI.UITypes.Error <Error>k__BackingField;

    public System.String RequestId { get; set; }
    public PDX.ModsUI.UITypes.Error Error { get; set; }
    public System.Boolean Success { get; }

    public Response();

}
```


## Fields

- `private System.String <RequestId>k__BackingField`  

```csharp
private System.String <RequestId>k__BackingField;
```

- `private PDX.ModsUI.UITypes.Error <Error>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.Error <Error>k__BackingField;
```


## Properties

- `public System.String RequestId { get; set }`  

```csharp
public System.String RequestId { get; set; }
```

- `public PDX.ModsUI.UITypes.Error Error { get; set }`  

```csharp
public PDX.ModsUI.UITypes.Error Error { get; set; }
```

- `public System.Boolean Success { get }`  

```csharp
public System.Boolean Success { get; }
```


## Constructors

- `public Response()`  

```csharp
public Response();
```


