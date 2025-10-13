# Colossal.IO.AssetDatabase.DisableNotificationsScoped

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct DisableNotificationsScoped : System.IDisposable
{
    private System.Boolean m_Enabled;
    private Colossal.IO.AssetDatabase.IAssetDatabase m_Database;

    public DisableNotificationsScoped(Colossal.IO.AssetDatabase.IAssetDatabase database);

    public System.Void Dispose();
}
```


## Fields

- `private System.Boolean m_Enabled`  

```csharp
private System.Boolean m_Enabled;
```

- `private Colossal.IO.AssetDatabase.IAssetDatabase m_Database`  

```csharp
private Colossal.IO.AssetDatabase.IAssetDatabase m_Database;
```


## Constructors

- `public DisableNotificationsScoped(Colossal.IO.AssetDatabase.IAssetDatabase database)`  

```csharp
public DisableNotificationsScoped(Colossal.IO.AssetDatabase.IAssetDatabase database);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


