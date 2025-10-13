# Colossal.Versioning.VersioningSettings

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Versioning`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class VersioningSettings
{
    public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_AssembliesToProcess;
    public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_ContentsToProcess;
    public static const System.String kVersioningJSONAssetPath;

    public VersioningSettings();

    public System.Boolean FindAssembly(System.String assemblyName, Colossal.Versioning.VersioningSettings+Version& version);
    public static Colossal.Versioning.VersioningSettings Load(System.String path);
    public System.Void Save(System.String path);
}
```


## Fields

- `public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_AssembliesToProcess`  

```csharp
public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_AssembliesToProcess;
```

- `public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_ContentsToProcess`  

```csharp
public System.Collections.Generic.List<Colossal.Versioning.VersioningSettings+Version> m_ContentsToProcess;
```

- `public static const System.String kVersioningJSONAssetPath`  

```csharp
public static const System.String kVersioningJSONAssetPath;
```


## Constructors

- `public VersioningSettings()`  

```csharp
public VersioningSettings();
```


## Methods

- `public FindAssembly(System.String assemblyName, Colossal.Versioning.VersioningSettings+Version& version) : System.Boolean`  

```csharp
public System.Boolean FindAssembly(System.String assemblyName, Colossal.Versioning.VersioningSettings+Version& version);
```

- `public static Load(System.String path = null) : Colossal.Versioning.VersioningSettings`  

```csharp
public static Colossal.Versioning.VersioningSettings Load(System.String path);
```

- `public Save(System.String path = null) : System.Void`  

```csharp
public System.Void Save(System.String path);
```


## Nested types

- `Colossal.Versioning.VersioningSettings+Version`  

