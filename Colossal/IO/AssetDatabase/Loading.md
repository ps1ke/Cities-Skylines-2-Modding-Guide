# Colossal.IO.AssetDatabase.GeometryAsset+Loading

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct Loading : System.IDisposable
{
    public System.Boolean m_HeaderLoaded;
    public System.Boolean m_AsyncLoadingStarted;
    public System.Boolean m_AsyncLoadingDone;
    public System.Boolean m_AsyncLoadingScheduled;
    public Colossal.IO.AssetDatabase.AsyncReadDescriptor m_AsyncReadDescriptor;
    public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncHeaderReadHandle;
    public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncBodyReadHandle;
    public System.UInt32 m_AsyncMask;

    public System.String FileDisplayName { get; }

    public System.Void Dispose();
}
```


## Fields

- `public System.Boolean m_HeaderLoaded`  

```csharp
public System.Boolean m_HeaderLoaded;
```

- `public System.Boolean m_AsyncLoadingStarted`  

```csharp
public System.Boolean m_AsyncLoadingStarted;
```

- `public System.Boolean m_AsyncLoadingDone`  

```csharp
public System.Boolean m_AsyncLoadingDone;
```

- `public System.Boolean m_AsyncLoadingScheduled`  

```csharp
public System.Boolean m_AsyncLoadingScheduled;
```

- `public Colossal.IO.AssetDatabase.AsyncReadDescriptor m_AsyncReadDescriptor`  

```csharp
public Colossal.IO.AssetDatabase.AsyncReadDescriptor m_AsyncReadDescriptor;
```

- `public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncHeaderReadHandle`  

```csharp
public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncHeaderReadHandle;
```

- `public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncBodyReadHandle`  

```csharp
public Unity.IO.LowLevel.Unsafe.ReadHandle m_AsyncBodyReadHandle;
```

- `public System.UInt32 m_AsyncMask`  

```csharp
public System.UInt32 m_AsyncMask;
```


## Properties

- `public System.String FileDisplayName { get }`  

```csharp
public System.String FileDisplayName { get; }
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


