# Colossal.IO.AssetDatabase.IAssetData

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`  

**Attributes:** `JsonConverter`  

## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.String name { get }`  
- `public Colossal.IO.AssetDatabase.Identifier id { get; set }`  
- `public System.String uri { get; set }`  
- `public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set }`  
- `public System.Boolean isPersistent { get }`  
- `public System.Boolean isDirty { get }`  

## Methods

- `public abstract MarkDirty() : System.Boolean`  
- `public abstract PostCreate() : System.Void`  
- `public abstract Save(System.Boolean force = False) : System.Void`  
- `public abstract Unload(System.Boolean force = False) : System.Void`  

