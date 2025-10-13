# Game.UI.Editor.EditorHierarchyUISystem+ItemId

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `Colossal.UI.Binding.IJsonReadable`, `System.IEquatable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>`, `System.IComparable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>`  

## Code

```csharp
public sealed struct ItemId : Colossal.UI.Binding.IJsonWritable, Colossal.UI.Binding.IJsonReadable, System.IEquatable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>, System.IComparable<Game.UI.Editor.EditorHierarchyUISystem+ItemId>
{
    public Game.UI.Editor.EditorHierarchyUISystem+ItemType type;
    public Unity.Entities.Entity entity;
    public System.Int32 subIndex;

    public System.Boolean isContainer { get; }

    public ItemId(Game.UI.Editor.EditorHierarchyUISystem+ItemType type, Unity.Entities.Entity entity, System.Int32 subIndex);

    public System.Int32 CompareTo(Game.UI.Editor.EditorHierarchyUISystem+ItemId other);
    public System.Boolean Equals(Game.UI.Editor.EditorHierarchyUISystem+ItemId other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.UI.Editor.EditorHierarchyUISystem+ItemType type`  

```csharp
public Game.UI.Editor.EditorHierarchyUISystem+ItemType type;
```

- `public Unity.Entities.Entity entity`  

```csharp
public Unity.Entities.Entity entity;
```

- `public System.Int32 subIndex`  

```csharp
public System.Int32 subIndex;
```


## Properties

- `public System.Boolean isContainer { get }`  

```csharp
public System.Boolean isContainer { get; }
```


## Constructors

- `public ItemId(Game.UI.Editor.EditorHierarchyUISystem+ItemType type, Unity.Entities.Entity entity = null, System.Int32 subIndex = 0)`  

```csharp
public ItemId(Game.UI.Editor.EditorHierarchyUISystem+ItemType type, Unity.Entities.Entity entity, System.Int32 subIndex);
```


## Methods

- `public CompareTo(Game.UI.Editor.EditorHierarchyUISystem+ItemId other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.Editor.EditorHierarchyUISystem+ItemId other);
```

- `public Equals(Game.UI.Editor.EditorHierarchyUISystem+ItemId other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.UI.Editor.EditorHierarchyUISystem+ItemId other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  

```csharp
public System.Void Read(Colossal.UI.Binding.IJsonReader reader);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


