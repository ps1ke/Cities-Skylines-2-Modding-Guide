# PDX.ModsUI.UITypes.GetUIStatusResponse

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Response`  
**Implements:** `PDX.ModsUI.UITypes.IResponse`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class GetUIStatusResponse : PDX.ModsUI.UITypes.Response, PDX.ModsUI.UITypes.IResponse
{
    private PDX.ModsUI.UITypes.UIStatus <Result>k__BackingField;

    public PDX.ModsUI.UITypes.UIStatus Result { get; set; }

    public GetUIStatusResponse();

}
```


## Fields

- `private PDX.ModsUI.UITypes.UIStatus <Result>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.UIStatus <Result>k__BackingField;
```


## Properties

- `public PDX.ModsUI.UITypes.UIStatus Result { get; set }`  

```csharp
public PDX.ModsUI.UITypes.UIStatus Result { get; set; }
```


## Constructors

- `public GetUIStatusResponse()`  

```csharp
public GetUIStatusResponse();
```


