# Game.Rendering.OptionalProperties

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Rendering.IOptionalProperties<Game.Rendering.OptionalProperties>`, `System.IEquatable<Game.Rendering.OptionalProperties>`  

## Code

```csharp
public sealed struct OptionalProperties : Colossal.Rendering.IOptionalProperties<Game.Rendering.OptionalProperties>, System.IEquatable<Game.Rendering.OptionalProperties>
{
    private Game.Rendering.BatchFlags m_Flags;
    private Game.Prefabs.MeshType m_MeshTypes;

    public OptionalProperties(Game.Rendering.BatchFlags flags, Game.Prefabs.MeshType meshTypes);

    public System.Boolean EnableProperty(Game.Rendering.OptionalProperties required);
    public System.Boolean Equals(Game.Rendering.OptionalProperties other);
    public System.Boolean MergeRequirements(Game.Rendering.OptionalProperties other);
}
```


## Fields

- `private Game.Rendering.BatchFlags m_Flags`  

```csharp
private Game.Rendering.BatchFlags m_Flags;
```

- `private Game.Prefabs.MeshType m_MeshTypes`  

```csharp
private Game.Prefabs.MeshType m_MeshTypes;
```


## Constructors

- `public OptionalProperties(Game.Rendering.BatchFlags flags, Game.Prefabs.MeshType meshTypes)`  

```csharp
public OptionalProperties(Game.Rendering.BatchFlags flags, Game.Prefabs.MeshType meshTypes);
```


## Methods

- `public EnableProperty(Game.Rendering.OptionalProperties required) : System.Boolean`  

```csharp
public System.Boolean EnableProperty(Game.Rendering.OptionalProperties required);
```

- `public Equals(Game.Rendering.OptionalProperties other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Rendering.OptionalProperties other);
```

- `public MergeRequirements(Game.Rendering.OptionalProperties other) : System.Boolean`  

```csharp
public System.Boolean MergeRequirements(Game.Rendering.OptionalProperties other);
```


