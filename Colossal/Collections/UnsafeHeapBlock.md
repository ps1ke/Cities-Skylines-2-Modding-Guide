# Colossal.Collections.UnsafeHeapBlock

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Colossal.Collections.UnsafeHeapBlock>`, `System.IEquatable<Colossal.Collections.UnsafeHeapBlock>`  

## Code

```csharp
public sealed struct UnsafeHeapBlock : System.IComparable<Colossal.Collections.UnsafeHeapBlock>, System.IEquatable<Colossal.Collections.UnsafeHeapBlock>
{
    public System.UInt32 begin;
    public System.UInt32 end;

    public System.UInt32 Length { get; }
    public System.Boolean Empty { get; }

    public UnsafeHeapBlock(System.UInt32 begin, System.UInt32 end);

    public System.Int32 CompareTo(Colossal.Collections.UnsafeHeapBlock other);
    public System.Boolean Equals(Colossal.Collections.UnsafeHeapBlock other);
    public static Colossal.Collections.UnsafeHeapBlock OfSize(System.UInt32 begin, System.UInt32 size);
}
```


## Fields

- `public System.UInt32 begin`  

```csharp
public System.UInt32 begin;
```

- `public System.UInt32 end`  

```csharp
public System.UInt32 end;
```


## Properties

- `public System.UInt32 Length { get }`  

```csharp
public System.UInt32 Length { get; }
```

- `public System.Boolean Empty { get }`  

```csharp
public System.Boolean Empty { get; }
```


## Constructors

- `public UnsafeHeapBlock(System.UInt32 begin, System.UInt32 end)`  

```csharp
public UnsafeHeapBlock(System.UInt32 begin, System.UInt32 end);
```


## Methods

- `public CompareTo(Colossal.Collections.UnsafeHeapBlock other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.Collections.UnsafeHeapBlock other);
```

- `public Equals(Colossal.Collections.UnsafeHeapBlock other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Collections.UnsafeHeapBlock other);
```

- `public static OfSize(System.UInt32 begin, System.UInt32 size) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
public static Colossal.Collections.UnsafeHeapBlock OfSize(System.UInt32 begin, System.UInt32 size);
```


