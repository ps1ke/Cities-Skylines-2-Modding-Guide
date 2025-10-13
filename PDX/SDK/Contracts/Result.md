# PDX.SDK.Contracts.Result

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Preserve`  

## Code

```csharp
public class Result
{
    private System.String <RequestId>k__BackingField;
    private System.Boolean <Success>k__BackingField;
    private PDX.SDK.Contracts.Error <Error>k__BackingField;

    public System.String RequestId { get; set; }
    public System.Boolean Success { get; set; }
    public PDX.SDK.Contracts.Error Error { get; set; }

    public Result();
    public Result(PDX.SDK.Contracts.Result result);

    public static PDX.SDK.Contracts.Result ResultSuccessful();
}
```


## Fields

- `private System.String <RequestId>k__BackingField`  

```csharp
private System.String <RequestId>k__BackingField;
```

- `private System.Boolean <Success>k__BackingField`  

```csharp
private System.Boolean <Success>k__BackingField;
```

- `private PDX.SDK.Contracts.Error <Error>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Error <Error>k__BackingField;
```


## Properties

- `public System.String RequestId { get; set }`  

```csharp
public System.String RequestId { get; set; }
```

- `public System.Boolean Success { get; set }`  

```csharp
public System.Boolean Success { get; set; }
```

- `public PDX.SDK.Contracts.Error Error { get; set }`  

```csharp
public PDX.SDK.Contracts.Error Error { get; set; }
```


## Constructors

- `public Result()`  

```csharp
public Result();
```

- `public Result(PDX.SDK.Contracts.Result result)`  

```csharp
public Result(PDX.SDK.Contracts.Result result);
```


## Methods

- `public static ResultSuccessful() : PDX.SDK.Contracts.Result`  

```csharp
public static PDX.SDK.Contracts.Result ResultSuccessful();
```


