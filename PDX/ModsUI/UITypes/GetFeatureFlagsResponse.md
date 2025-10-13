# PDX.ModsUI.UITypes.GetFeatureFlagsResponse

**Assembly:** `PDX.ModsUI`  
**Namespace:** `PDX.ModsUI.UITypes`  

**Type:** class public  

**Base:** `PDX.ModsUI.UITypes.Response`  
**Implements:** `PDX.ModsUI.UITypes.IResponse`  

**Attributes:** `CoherentType`  

## Code

```csharp
public class GetFeatureFlagsResponse : PDX.ModsUI.UITypes.Response, PDX.ModsUI.UITypes.IResponse
{
    private PDX.ModsUI.UITypes.FeatureFlags <Result>k__BackingField;

    public PDX.ModsUI.UITypes.FeatureFlags Result { get; set; }

    public GetFeatureFlagsResponse();

}
```


## Fields

- `private PDX.ModsUI.UITypes.FeatureFlags <Result>k__BackingField`  

```csharp
private PDX.ModsUI.UITypes.FeatureFlags <Result>k__BackingField;
```


## Properties

- `public PDX.ModsUI.UITypes.FeatureFlags Result { get; set }`  

```csharp
public PDX.ModsUI.UITypes.FeatureFlags Result { get; set; }
```


## Constructors

- `public GetFeatureFlagsResponse()`  

```csharp
public GetFeatureFlagsResponse();
```


