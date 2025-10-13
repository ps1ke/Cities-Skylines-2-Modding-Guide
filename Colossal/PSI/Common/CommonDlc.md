# Colossal.PSI.Common.CommonDlc

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.PSI.Common.IDlc`  

## Code

```csharp
public class CommonDlc : Colossal.PSI.Common.IDlc
{
    private readonly Colossal.PSI.Common.DlcId <id>k__BackingField;
    private readonly System.String <internalName>k__BackingField;
    private readonly Colossal.Version <version>k__BackingField;

    public Colossal.PSI.Common.DlcId id { get; }
    public System.String internalName { get; }
    public System.String backendId { get; }
    public System.String backendName { get; }
    public System.Boolean hasStoreBackend { get; }
    public Colossal.Version version { get; }

    public CommonDlc(Colossal.PSI.Common.DlcId id, System.String internalName, Colossal.Version version);

}
```


## Fields

- `private readonly Colossal.PSI.Common.DlcId <id>k__BackingField`  

```csharp
private readonly Colossal.PSI.Common.DlcId <id>k__BackingField;
```

- `private readonly System.String <internalName>k__BackingField`  

```csharp
private readonly System.String <internalName>k__BackingField;
```

- `private readonly Colossal.Version <version>k__BackingField`  

```csharp
private readonly Colossal.Version <version>k__BackingField;
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


## Constructors

- `public CommonDlc(Colossal.PSI.Common.DlcId id, System.String internalName, Colossal.Version version)`  

```csharp
public CommonDlc(Colossal.PSI.Common.DlcId id, System.String internalName, Colossal.Version version);
```


