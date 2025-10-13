# PDX.SDK.Contracts.AggregateResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class AggregateResult : PDX.SDK.Contracts.Result
{
    private readonly System.Collections.Generic.List<PDX.SDK.Contracts.Result> _subResults;

    public System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Result> SubResults { get; }

    public AggregateResult();

    public System.Void Add(PDX.SDK.Contracts.Result result);
}
```


## Fields

- `private readonly System.Collections.Generic.List<PDX.SDK.Contracts.Result> _subResults`  

```csharp
private readonly System.Collections.Generic.List<PDX.SDK.Contracts.Result> _subResults;
```


## Properties

- `public System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Result> SubResults { get }`  

```csharp
public System.Collections.Generic.IEnumerable<PDX.SDK.Contracts.Result> SubResults { get; }
```


## Constructors

- `public AggregateResult()`  

```csharp
public AggregateResult();
```


## Methods

- `public Add(PDX.SDK.Contracts.Result result) : System.Void`  

```csharp
public System.Void Add(PDX.SDK.Contracts.Result result);
```


