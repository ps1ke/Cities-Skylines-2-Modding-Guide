# Colossal.PSI.Common.IDlc

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDlc
{
    public Colossal.PSI.Common.DlcId id { get; }
    public System.String internalName { get; }
    public System.String backendId { get; }
    public System.String backendName { get; }
    public System.Boolean hasStoreBackend { get; }
    public Colossal.Version version { get; }

}
```


## Properties

- `public Colossal.PSI.Common.DlcId id { get }`  

```csharp
public Colossal.PSI.Common.DlcId id { get; }
```

- `public System.String internalName { get }`  

```csharp
public System.String internalName { get; }
```

- `public System.String backendId { get }`  

```csharp
public System.String backendId { get; }
```

- `public System.String backendName { get }`  

```csharp
public System.String backendName { get; }
```

- `public System.Boolean hasStoreBackend { get }`  

```csharp
public System.Boolean hasStoreBackend { get; }
```

- `public Colossal.Version version { get }`  

```csharp
public Colossal.Version version { get; }
```


