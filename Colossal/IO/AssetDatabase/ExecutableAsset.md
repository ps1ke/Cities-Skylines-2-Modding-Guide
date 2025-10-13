# Colossal.IO.AssetDatabase.ExecutableAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class ExecutableAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean> onActivePlaysetChanged;
    private System.Boolean m_IsInActivePlayset;
    private Colossal.PSI.Common.Mod <mod>k__BackingField;
    private Colossal.Mono.Cecil.AssemblyDefinition <definition>k__BackingField;
    private System.Reflection.Assembly <assembly>k__BackingField;
    private System.Boolean <isBursted>k__BackingField;
    private System.Boolean <isMod>k__BackingField;
    private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_ReferenceOf;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> m_References;
    private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_Duplicates;
    private System.Boolean m_IsLoading;
    private static readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.AssemblyDefinition, Colossal.IO.AssetDatabase.ExecutableAsset> sAssemblyMap;
    private static Colossal.Logging.ILog moddingLog;
    public static readonly System.String sManagedLocation;
    private static const System.String kBurstSuffix;
    public static const System.String kExtension;

    public System.Boolean isInActivePlayset { get; set; }
    public System.Boolean isEnabled { get; }
    public Colossal.PSI.Common.Mod mod { get; private set; }
    public Colossal.Mono.Cecil.AssemblyDefinition definition { get; private set; }
    public System.Reflection.Assembly assembly { get; private set; }
    public System.Boolean isBursted { get; private set; }
    public System.Boolean isILAssembly { get; }
    public System.Version version { get; }
    public System.Boolean isLoaded { get; }
    public System.Boolean isLocal { get; }
    public System.Boolean isMod { get; private set; }
    public System.String name { get; }
    public System.String fullName { get; }
    public System.Boolean isReference { get; }
    public System.Boolean isRequired { get; }
    public System.Boolean canBeLoaded { get; }
    public System.Boolean isUnique { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> references { get; }

    public ExecutableAsset();

    private System.Boolean <GetUniqueVersionAsset>b__59_0(Colossal.IO.AssetDatabase.ExecutableAsset d);
    private System.Void AddDuplicates(Colossal.IO.AssetDatabase.ExecutableAsset[] duplicates);
    private System.Void AddReference(Colossal.Mono.Cecil.AssemblyNameReference assemblyName, Colossal.IO.AssetDatabase.ExecutableAsset reference);
    public static Colossal.IO.AssetDatabase.ExecutableAsset[] GetModAssets(System.Type modInterfaceType);
    public Colossal.IO.AssetDatabase.ExecutableAsset GetUniqueVersionAsset();
    public System.Void LoadAssembly(System.Action<System.Reflection.Assembly> afterLoadAction, Colossal.IO.AssetDatabase.ExecutableAsset& uniqueAsset);
    private System.Void LoadAssemblyImpl(System.Action<System.Reflection.Assembly> afterLoadAction);
    public virtual System.Void PostCreate();
    public static System.Boolean TryGetAsset(Colossal.Mono.Cecil.AssemblyDefinition definition, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean> onActivePlaysetChanged`  

```csharp
private System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean> onActivePlaysetChanged;
```

- `private System.Boolean m_IsInActivePlayset`  

```csharp
private System.Boolean m_IsInActivePlayset;
```

- `private Colossal.PSI.Common.Mod <mod>k__BackingField`  

```csharp
private Colossal.PSI.Common.Mod <mod>k__BackingField;
```

- `private Colossal.Mono.Cecil.AssemblyDefinition <definition>k__BackingField`  

```csharp
private Colossal.Mono.Cecil.AssemblyDefinition <definition>k__BackingField;
```

- `private System.Reflection.Assembly <assembly>k__BackingField`  

```csharp
private System.Reflection.Assembly <assembly>k__BackingField;
```

- `private System.Boolean <isBursted>k__BackingField`  

```csharp
private System.Boolean <isBursted>k__BackingField;
```

- `private System.Boolean <isMod>k__BackingField`  

```csharp
private System.Boolean <isMod>k__BackingField;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_ReferenceOf`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_ReferenceOf;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> m_References`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> m_References;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_Duplicates`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.ExecutableAsset> m_Duplicates;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```

- `private static readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.AssemblyDefinition, Colossal.IO.AssetDatabase.ExecutableAsset> sAssemblyMap`  

```csharp
private static readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.AssemblyDefinition, Colossal.IO.AssetDatabase.ExecutableAsset> sAssemblyMap;
```

- `private static Colossal.Logging.ILog moddingLog`  

```csharp
private static Colossal.Logging.ILog moddingLog;
```

- `public static readonly System.String sManagedLocation`  

```csharp
public static readonly System.String sManagedLocation;
```

- `private static const System.String kBurstSuffix`  

```csharp
private static const System.String kBurstSuffix;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

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

- `public Colossal.Mono.Cecil.AssemblyDefinition definition { get; private set }`  

```csharp
public Colossal.Mono.Cecil.AssemblyDefinition definition { get; private set; }
```

- `public System.Reflection.Assembly assembly { get; private set }`  

```csharp
public System.Reflection.Assembly assembly { get; private set; }
```

- `public System.Boolean isBursted { get; private set }`  

```csharp
public System.Boolean isBursted { get; private set; }
```

- `public System.Boolean isILAssembly { get }`  

```csharp
public System.Boolean isILAssembly { get; }
```

- `public System.Version version { get }`  

```csharp
public System.Version version { get; }
```

- `public System.Boolean isLoaded { get }`  

```csharp
public System.Boolean isLoaded { get; }
```

- `public System.Boolean isLocal { get }`  

```csharp
public System.Boolean isLocal { get; }
```

- `public System.Boolean isMod { get; private set }`  

```csharp
public System.Boolean isMod { get; private set; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String fullName { get }`  

```csharp
public System.String fullName { get; }
```

- `public System.Boolean isReference { get }`  

```csharp
public System.Boolean isReference { get; }
```

- `public System.Boolean isRequired { get }`  

```csharp
public System.Boolean isRequired { get; }
```

- `public System.Boolean canBeLoaded { get }`  

```csharp
public System.Boolean canBeLoaded { get; }
```

- `public System.Boolean isUnique { get }`  

```csharp
public System.Boolean isUnique { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> references { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.ExecutableAsset> references { get; }
```


## Constructors

- `public ExecutableAsset()`  

```csharp
public ExecutableAsset();
```


## Methods

- `private <GetUniqueVersionAsset>b__59_0(Colossal.IO.AssetDatabase.ExecutableAsset d) : System.Boolean`  

```csharp
private System.Boolean <GetUniqueVersionAsset>b__59_0(Colossal.IO.AssetDatabase.ExecutableAsset d);
```

- `private AddDuplicates(Colossal.IO.AssetDatabase.ExecutableAsset[] duplicates) : System.Void`  

```csharp
private System.Void AddDuplicates(Colossal.IO.AssetDatabase.ExecutableAsset[] duplicates);
```

- `private AddReference(Colossal.Mono.Cecil.AssemblyNameReference assemblyName, Colossal.IO.AssetDatabase.ExecutableAsset reference) : System.Void`  

```csharp
private System.Void AddReference(Colossal.Mono.Cecil.AssemblyNameReference assemblyName, Colossal.IO.AssetDatabase.ExecutableAsset reference);
```

- `public static GetModAssets(System.Type modInterfaceType) : Colossal.IO.AssetDatabase.ExecutableAsset[]`  

```csharp
public static Colossal.IO.AssetDatabase.ExecutableAsset[] GetModAssets(System.Type modInterfaceType);
```

- `public GetUniqueVersionAsset() : Colossal.IO.AssetDatabase.ExecutableAsset`  

```csharp
public Colossal.IO.AssetDatabase.ExecutableAsset GetUniqueVersionAsset();
```

- `public LoadAssembly(System.Action<System.Reflection.Assembly> afterLoadAction, Colossal.IO.AssetDatabase.ExecutableAsset& uniqueAsset) : System.Void`  

```csharp
public System.Void LoadAssembly(System.Action<System.Reflection.Assembly> afterLoadAction, Colossal.IO.AssetDatabase.ExecutableAsset& uniqueAsset);
```

- `private LoadAssemblyImpl(System.Action<System.Reflection.Assembly> afterLoadAction) : System.Void`  

```csharp
private System.Void LoadAssemblyImpl(System.Action<System.Reflection.Assembly> afterLoadAction);
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `public static TryGetAsset(Colossal.Mono.Cecil.AssemblyDefinition definition, Colossal.IO.AssetDatabase.ExecutableAsset& asset) : System.Boolean`  

```csharp
public static System.Boolean TryGetAsset(Colossal.Mono.Cecil.AssemblyDefinition definition, Colossal.IO.AssetDatabase.ExecutableAsset& asset);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Events

- `onActivePlaysetChanged` : `System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean>`  

```csharp
public event System.Action<Colossal.IO.AssetDatabase.ExecutableAsset, System.Boolean> onActivePlaysetChanged;
```


## Nested types

- `Colossal.IO.AssetDatabase.ExecutableAsset+ExecutableResolver`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+LoadExecutableException`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+LoadExecutableReferenceException`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+<>c`  
- `Colossal.IO.AssetDatabase.ExecutableAsset+<>c__DisplayClass68_0`  

