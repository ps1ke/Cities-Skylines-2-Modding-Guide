# PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncResult

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Result`  

**Type:** class public  

**Base:** `PDX.SDK.Contracts.Result`  

**Attributes:** `Preserve`  

## Code

```csharp
public class PlaysetSyncResult : PDX.SDK.Contracts.Result
{
    private PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] <PlaysetSyncConflicts>k__BackingField;

    public PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] PlaysetSyncConflicts { get; set; }

    public PlaysetSyncResult();

}
```


## Fields

- `private PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] <PlaysetSyncConflicts>k__BackingField`  

```csharp
private PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] <PlaysetSyncConflicts>k__BackingField;
```


## Properties

- `public PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] PlaysetSyncConflicts { get; set }`  

```csharp
public PDX.SDK.Contracts.Service.Mods.Result.PlaysetSyncConflict[] PlaysetSyncConflicts { get; set; }
```


## Constructors

- `public PlaysetSyncResult()`  

```csharp
public PlaysetSyncResult();
```


