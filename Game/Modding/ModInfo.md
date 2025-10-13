# Game.Modding.ModManager+ModInfo

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ModInfo
{
    private readonly System.Collections.Generic.List<Game.Modding.IMod> m_Instances;
    private Colossal.IO.AssetDatabase.ExecutableAsset <asset>k__BackingField;
    private Game.Modding.ModManager+ModInfo+State <state>k__BackingField;
    private System.String <loadError>k__BackingField;

    public System.Collections.Generic.IReadOnlyList<Game.Modding.IMod> instances { get; }
    public Colossal.IO.AssetDatabase.ExecutableAsset asset { get; private set; }
    public System.Boolean isValid { get; }
    public System.Boolean isLoaded { get; }
    public System.Boolean isBursted { get; }
    public System.String name { get; }
    public System.String assemblyFullName { get; }
    public Game.Modding.ModManager+ModInfo+State state { get; private set; }
    public System.String loadError { get; private set; }

    public ModInfo(Colossal.IO.AssetDatabase.ExecutableAsset asset);

    private static System.Void AfterLoadAssembly(System.Reflection.Assembly assembly);
    public System.Void Dispose();
    public System.Void Load(Game.UpdateSystem updateSystem);
    private System.Void OnDispose();
    private System.Void OnLoad(Game.UpdateSystem updateSystem);
    public System.Void Preload(System.Reflection.Assembly[] assemblies);
}
```


## Fields

- `private readonly System.Collections.Generic.List<Game.Modding.IMod> m_Instances`  

```csharp
private readonly System.Collections.Generic.List<Game.Modding.IMod> m_Instances;
```

- `private Colossal.IO.AssetDatabase.ExecutableAsset <asset>k__BackingField`  

```csharp
private Colossal.IO.AssetDatabase.ExecutableAsset <asset>k__BackingField;
```

- `private Game.Modding.ModManager+ModInfo+State <state>k__BackingField`  

```csharp
private Game.Modding.ModManager+ModInfo+State <state>k__BackingField;
```

- `private System.String <loadError>k__BackingField`  

```csharp
private System.String <loadError>k__BackingField;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Modding.IMod> instances { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Modding.IMod> instances { get; }
```

- `public Colossal.IO.AssetDatabase.ExecutableAsset asset { get; private set }`  

```csharp
public Colossal.IO.AssetDatabase.ExecutableAsset asset { get; private set; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```

- `public System.Boolean isLoaded { get }`  

```csharp
public System.Boolean isLoaded { get; }
```

- `public System.Boolean isBursted { get }`  

```csharp
public System.Boolean isBursted { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String assemblyFullName { get }`  

```csharp
public System.String assemblyFullName { get; }
```

- `public Game.Modding.ModManager+ModInfo+State state { get; private set }`  

```csharp
public Game.Modding.ModManager+ModInfo+State state { get; private set; }
```

- `public System.String loadError { get; private set }`  

```csharp
public System.String loadError { get; private set; }
```


## Constructors

- `public ModInfo(Colossal.IO.AssetDatabase.ExecutableAsset asset)`  

```csharp
public ModInfo(Colossal.IO.AssetDatabase.ExecutableAsset asset);
```


## Methods

- `private static AfterLoadAssembly(System.Reflection.Assembly assembly) : System.Void`  

```csharp
private static System.Void AfterLoadAssembly(System.Reflection.Assembly assembly);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Load(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
public System.Void Load(Game.UpdateSystem updateSystem);
```

- `private OnDispose() : System.Void`  

```csharp
private System.Void OnDispose();
```

- `private OnLoad(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
private System.Void OnLoad(Game.UpdateSystem updateSystem);
```

- `public Preload(System.Reflection.Assembly[] assemblies) : System.Void`  

```csharp
public System.Void Preload(System.Reflection.Assembly[] assemblies);
```


## Nested types

- `Game.Modding.ModManager+ModInfo+State`  
- `Game.Modding.ModManager+ModInfo+<>c`  

