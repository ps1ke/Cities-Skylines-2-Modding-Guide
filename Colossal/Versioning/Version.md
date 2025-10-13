# Colossal.Versioning.VersioningSettings+Version

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Versioning`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class Version
{
    public System.String m_Target;
    public System.Int32 m_MajorVersion;
    public System.Int32 m_MinorVersion;
    public System.Int32 m_BuildVersion;
    public Colossal.Version+ReleaseType m_ReleaseType;
    public System.Int32 m_IncrementalVersion;

    public System.String version { get; }
    public System.String microsoftPcVersion { get; }
    public System.String microsoftXboxVersion { get; }
    public System.String playStation5Version { get; }

    public Version();

}
```


## Fields

- `public System.String m_Target`  

```csharp
public System.String m_Target;
```

- `public System.Int32 m_MajorVersion`  

```csharp
public System.Int32 m_MajorVersion;
```

- `public System.Int32 m_MinorVersion`  

```csharp
public System.Int32 m_MinorVersion;
```

- `public System.Int32 m_BuildVersion`  

```csharp
public System.Int32 m_BuildVersion;
```

- `public Colossal.Version+ReleaseType m_ReleaseType`  

```csharp
public Colossal.Version+ReleaseType m_ReleaseType;
```

- `public System.Int32 m_IncrementalVersion`  

```csharp
public System.Int32 m_IncrementalVersion;
```


## Properties

- `public System.String version { get }`  

```csharp
public System.String version { get; }
```

- `public System.String microsoftPcVersion { get }`  

```csharp
public System.String microsoftPcVersion { get; }
```

- `public System.String microsoftXboxVersion { get }`  

```csharp
public System.String microsoftXboxVersion { get; }
```

- `public System.String playStation5Version { get }`  

```csharp
public System.String playStation5Version { get; }
```


## Constructors

- `public Version()`  

```csharp
public Version();
```


