# Colossal.IO.AssetDatabase.GdkPackageWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IPackageWriter`, `System.IDisposable`  

## Code

```csharp
public class GdkPackageWriter : Colossal.IO.AssetDatabase.IPackageWriter, System.IDisposable
{
    private readonly Colossal.IO.AssetDatabase.GdkCloudDataSource m_DataSource;
    private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager;
    private readonly System.String m_ContainerName;
    private readonly System.String m_ContainerGuidName;
    private readonly Colossal.Hash128 m_ContainerGuid;
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.GdkPackageWriter+Entry> m_Entries;
    private System.Boolean m_IsDirty;

    public GdkPackageWriter(Colossal.Hash128 id, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.PSI.MicrosoftGdk.GdkPlatform platformManager, Colossal.IO.AssetDatabase.GdkCloudDataSource dataSource);

    public System.Void Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp);
    private System.Boolean CheckPerUserQuota();
    public System.Boolean Commit();
    public System.Void Dispose();
}
```


## Fields

- `private readonly Colossal.IO.AssetDatabase.GdkCloudDataSource m_DataSource`  

```csharp
private readonly Colossal.IO.AssetDatabase.GdkCloudDataSource m_DataSource;
```

- `private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager`  

```csharp
private readonly Colossal.PSI.MicrosoftGdk.GdkPlatform m_PlatformManager;
```

- `private readonly System.String m_ContainerName`  

```csharp
private readonly System.String m_ContainerName;
```

- `private readonly System.String m_ContainerGuidName`  

```csharp
private readonly System.String m_ContainerGuidName;
```

- `private readonly Colossal.Hash128 m_ContainerGuid`  

```csharp
private readonly Colossal.Hash128 m_ContainerGuid;
```

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.GdkPackageWriter+Entry> m_Entries`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.GdkPackageWriter+Entry> m_Entries;
```

- `private System.Boolean m_IsDirty`  

```csharp
private System.Boolean m_IsDirty;
```


## Constructors

- `public GdkPackageWriter(Colossal.Hash128 id, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.PSI.MicrosoftGdk.GdkPlatform platformManager, Colossal.IO.AssetDatabase.GdkCloudDataSource dataSource)`  

```csharp
public GdkPackageWriter(Colossal.Hash128 id, Colossal.IO.AssetDatabase.GdkCloudDataSource+EntryInfo fi, Colossal.PSI.MicrosoftGdk.GdkPlatform platformManager, Colossal.IO.AssetDatabase.GdkCloudDataSource dataSource);
```


## Methods

- `public Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp = False) : System.Void`  

```csharp
public System.Void Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp);
```

- `private CheckPerUserQuota() : System.Boolean`  

```csharp
private System.Boolean CheckPerUserQuota();
```

- `public Commit() : System.Boolean`  

```csharp
public System.Boolean Commit();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


## Nested types

- `Colossal.IO.AssetDatabase.GdkPackageWriter+Entry`  

