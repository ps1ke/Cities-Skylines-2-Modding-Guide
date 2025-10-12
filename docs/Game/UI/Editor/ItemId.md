# Game.UI.Editor.EditorHierarchyUISystem+ItemId

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`, `System.IEquatable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>`, `System.IComparable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>`  

## Fields

- `public Game.UI.Editor.EditorHierarchyUISystem+ItemType type`  
- `public Unity.Entities.Entity entity`  
- `public System.Int32 subIndex`  

## Properties

- `public System.Boolean isContainer { get }`  

## Constructors

- `public ItemId(Game.UI.Editor.EditorHierarchyUISystem+ItemType type, Unity.Entities.Entity entity = null, System.Int32 subIndex = 0)`  

## Methods

- `public CompareTo(Game.UI.Editor.EditorHierarchyUISystem+ItemId other) : System.Int32`  
- `public Equals(Game.UI.Editor.EditorHierarchyUISystem+ItemId other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

