# Colossal.IO.AssetDatabase.SourceMeta

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SourceMeta
{
    public System.String extension;
    public System.String displayName;
    public System.String fileName;
    public System.String path;
    public System.String subPath;
    public System.Int64 size;
    public System.Boolean priorityAsset;
    public System.Int32 platformID;
    public System.String platformVersion;
    public System.DateTime creationTime;
    public System.DateTime lastAccessTime;
    public System.DateTime lastWriteTime;
    public System.Boolean persistent;
    public System.Boolean belongsToCurrentUser;
    public System.String packageName;
    public Colossal.Hash128 package;
    public System.String remoteStorageSourceName;

    public System.Boolean packaged { get; }
    public Colossal.IO.AssetDatabase.AssetDataPath assetDataPath { get; }

}
```


## Fields

- `public System.String extension`  

```csharp
public System.String extension;
```

- `public System.String displayName`  

```csharp
public System.String displayName;
```

- `public System.String fileName`  

```csharp
public System.String fileName;
```

- `public System.String path`  

```csharp
public System.String path;
```

- `public System.String subPath`  

```csharp
public System.String subPath;
```

- `public System.Int64 size`  

```csharp
public System.Int64 size;
```

- `public System.Boolean priorityAsset`  

```csharp
public System.Boolean priorityAsset;
```

- `public System.Int32 platformID`  

```csharp
public System.Int32 platformID;
```

- `public System.String platformVersion`  

```csharp
public System.String platformVersion;
```

- `public System.DateTime creationTime`  

```csharp
public System.DateTime creationTime;
```

- `public System.DateTime lastAccessTime`  

```csharp
public System.DateTime lastAccessTime;
```

- `public System.DateTime lastWriteTime`  

```csharp
public System.DateTime lastWriteTime;
```

- `public System.Boolean persistent`  

```csharp
public System.Boolean persistent;
```

- `public System.Boolean belongsToCurrentUser`  

```csharp
public System.Boolean belongsToCurrentUser;
```

- `public System.String packageName`  

```csharp
public System.String packageName;
```

- `public Colossal.Hash128 package`  

```csharp
public Colossal.Hash128 package;
```

- `public System.String remoteStorageSourceName`  

```csharp
public System.String remoteStorageSourceName;
```


## Properties

- `public System.Boolean packaged { get }`  

```csharp
public System.Boolean packaged { get; }
```

- `public Colossal.IO.AssetDatabase.AssetDataPath assetDataPath { get }`  

```csharp
public Colossal.IO.AssetDatabase.AssetDataPath assetDataPath { get; }
```


