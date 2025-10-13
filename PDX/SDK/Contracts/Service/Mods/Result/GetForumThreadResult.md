# PDX.SDK.Contracts.Service.Mods.Result.GetForumThreadResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class GetForumThreadResult : PDX.SDK.Contracts.Result
{
    private PDX.SDK.Contracts.Service.Mods.Models.ForumPost <FirstPost>k__BackingField;
    private PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] <Posts>k__BackingField;
    private System.Int32 <Count>k__BackingField;
    private System.Boolean <CanPost>k__BackingField;

    public PDX.SDK.Contracts.Service.Mods.Models.ForumPost FirstPost { get; set; }
    public PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] Posts { get; set; }
    public System.Int32 Count { get; set; }
    public System.Boolean CanPost { get; set; }

    public GetForumThreadResult();

}
```


## Fields

- `private PDX.SDK.Contracts.Service.Mods.Models.ForumPost <FirstPost>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.ForumPost <FirstPost>k__BackingField;
```

- `private PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] <Posts>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] <Posts>k__BackingField;
```

- `private System.Int32 <Count>k__BackingField`  

```csharp
private System.Int32 <Count>k__BackingField;
```

- `private System.Boolean <CanPost>k__BackingField`  

```csharp
private System.Boolean <CanPost>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Service.Mods.Models.ForumPost FirstPost { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.ForumPost FirstPost { get; set; }
```

- `public PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] Posts { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Models.ForumPost[] Posts { get; set; }
```

- `public System.Int32 Count { get; set }`  

```csharp
public System.Int32 Count { get; set; }
```

- `public System.Boolean CanPost { get; set }`  

```csharp
public System.Boolean CanPost { get; set; }
```


## Constructors

- `public GetForumThreadResult()`  

```csharp
public GetForumThreadResult();
```


