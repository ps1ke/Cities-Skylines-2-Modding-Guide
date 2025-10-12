# Game.Modding.ModManager+ModInfo

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.Collections.Generic.List<Game.Modding.IMod> m_Instances`  
- `private Colossal.IO.AssetDatabase.ExecutableAsset <asset>k__BackingField`  
- `private Game.Modding.ModManager+ModInfo+State <state>k__BackingField`  
- `private System.String <loadError>k__BackingField`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.Modding.IMod> instances { get }`  
- `public Colossal.IO.AssetDatabase.ExecutableAsset asset { get; private set }`  
- `public System.Boolean isValid { get }`  
- `public System.Boolean isLoaded { get }`  
- `public System.Boolean isBursted { get }`  
- `public System.String name { get }`  
- `public System.String assemblyFullName { get }`  
- `public Game.Modding.ModManager+ModInfo+State state { get; private set }`  
- `public System.String loadError { get; private set }`  

## Constructors

- `public ModInfo(Colossal.IO.AssetDatabase.ExecutableAsset asset)`  

## Methods

- `private static AfterLoadAssembly(System.Reflection.Assembly assembly) : System.Void`  
- `public Dispose() : System.Void`  
- `public Load(Game.UpdateSystem updateSystem) : System.Void`  
- `private OnDispose() : System.Void`  
- `private OnLoad(Game.UpdateSystem updateSystem) : System.Void`  
- `public Preload(System.Reflection.Assembly[] assemblies) : System.Void`  

## Nested types

- `Game.Modding.ModManager+ModInfo+State`  
- `Game.Modding.ModManager+ModInfo+<>c`  

