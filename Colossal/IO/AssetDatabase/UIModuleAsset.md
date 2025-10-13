# Colossal.IO.AssetDatabase.UIModuleAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class UIModuleAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo m_ModuleInfo;
    private System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean> onActivePlaysetChanged;
    private System.Boolean m_IsInActivePlayset;
    private Colossal.PSI.Common.Mod <mod>k__BackingField;
    public static const System.String kExtension;
    private static const System.String kModuleIdentifier;

    public System.String name { get; }
    public Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo moduleInfo { get; }
    public System.Boolean isValidModule { get; }
    public System.Boolean isLocal { get; }
    public System.String couiPath { get; }
    public System.Boolean isInActivePlayset { get; set; }
    public System.Boolean isEnabled { get; }
    public Colossal.PSI.Common.Mod mod { get; private set; }

    public UIModuleAsset();

    private static Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo ParseModuleInfo(System.IO.StreamReader reader);
    public virtual System.Void PostCreate();
    private static System.Boolean ProcessLine(System.String line, Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo& moduleInfo);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo m_ModuleInfo`  

```csharp
private Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo m_ModuleInfo;
```

- `private System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean> onActivePlaysetChanged`  

```csharp
private System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean> onActivePlaysetChanged;
```

- `private System.Boolean m_IsInActivePlayset`  

```csharp
private System.Boolean m_IsInActivePlayset;
```

- `private Colossal.PSI.Common.Mod <mod>k__BackingField`  

```csharp
private Colossal.PSI.Common.Mod <mod>k__BackingField;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `private static const System.String kModuleIdentifier`  

```csharp
private static const System.String kModuleIdentifier;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo moduleInfo { get }`  

```csharp
public Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo moduleInfo { get; }
```

- `public System.Boolean isValidModule { get }`  

```csharp
public System.Boolean isValidModule { get; }
```

- `public System.Boolean isLocal { get }`  

```csharp
public System.Boolean isLocal { get; }
```

- `public System.String couiPath { get }`  

```csharp
public System.String couiPath { get; }
```

- `public System.Boolean isInActivePlayset { get; set }`  

```csharp
public System.Boolean isInActivePlayset { get; set; }
```

- `public System.Boolean isEnabled { get }`  

```csharp
public System.Boolean isEnabled { get; }
```

- `public Colossal.PSI.Common.Mod mod { get; private set }`  

```csharp
public Colossal.PSI.Common.Mod mod { get; private set; }
```


## Constructors

- `public UIModuleAsset()`  

```csharp
public UIModuleAsset();
```


## Methods

- `private static ParseModuleInfo(System.IO.StreamReader reader) : Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo`  

```csharp
private static Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo ParseModuleInfo(System.IO.StreamReader reader);
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `private static ProcessLine(System.String line, Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo& moduleInfo) : System.Boolean`  

```csharp
private static System.Boolean ProcessLine(System.String line, Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo& moduleInfo);
```


## Events

- `onActivePlaysetChanged` : `System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean>`  

```csharp
public event System.Action<Colossal.IO.AssetDatabase.UIModuleAsset, System.Boolean> onActivePlaysetChanged;
```


## Nested types

- `Colossal.IO.AssetDatabase.UIModuleAsset+ModuleInfo`  
- `Colossal.IO.AssetDatabase.UIModuleAsset+<>c`  

