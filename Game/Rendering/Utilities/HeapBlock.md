# Game.Rendering.Utilities.HeapBlock

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Rendering.Utilities.HeapBlock>`, `System.IEquatable<Game.Rendering.Utilities.HeapBlock>`  

**Attributes:** `DebuggerDisplay`  

## Code

```csharp
public sealed struct HeapBlock : System.IComparable<Game.Rendering.Utilities.HeapBlock>, System.IEquatable<Game.Rendering.Utilities.HeapBlock>
{
    public System.UInt64 begin;
    public System.UInt64 end;

    public System.UInt64 Length { get; }
    public System.Boolean Empty { get; }

    public HeapBlock(System.UInt64 begin, System.UInt64 end);

    public System.Int32 CompareTo(Game.Rendering.Utilities.HeapBlock other);
    public System.Boolean Equals(Game.Rendering.Utilities.HeapBlock other);
    public static Game.Rendering.Utilities.HeapBlock OfSize(System.UInt64 begin, System.UInt64 size);
}
```


## Fields

- `public System.UInt64 begin`  

```csharp
public System.UInt64 begin;
```

- `public System.UInt64 end`  

```csharp
public System.UInt64 end;
```


## Properties

- `public System.UInt64 Length { get }`  

```csharp
public System.UInt64 Length { get; }
```

- `public System.Boolean Empty { get }`  

```csharp
public System.Boolean Empty { get; }
```


## Constructors

- `public HeapBlock(System.UInt64 begin, System.UInt64 end)`  

```csharp
public HeapBlock(System.UInt64 begin, System.UInt64 end);
```


## Methods

- `public CompareTo(Game.Rendering.Utilities.HeapBlock other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Rendering.Utilities.HeapBlock other);
```

- `public Equals(Game.Rendering.Utilities.HeapBlock other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Rendering.Utilities.HeapBlock other);
```

- `public static OfSize(System.UInt64 begin, System.UInt64 size) : Game.Rendering.Utilities.HeapBlock`  

```csharp
public static Game.Rendering.Utilities.HeapBlock OfSize(System.UInt64 begin, System.UInt64 size);
```


