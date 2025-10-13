# Colossal.Collections.NativeHeapBlock

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct NativeHeapBlock
{
    internal Colossal.Collections.UnsafeHeapBlock m_Block;

    public System.UInt32 Length { get; }
    public System.Boolean Empty { get; }
    public System.UInt32 Begin { get; }
    public System.UInt32 End { get; }

    public NativeHeapBlock(Colossal.Collections.UnsafeHeapBlock block);

}
```


## Fields

- `internal Colossal.Collections.UnsafeHeapBlock m_Block`  

```csharp
internal Colossal.Collections.UnsafeHeapBlock m_Block;
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

- `public System.UInt32 Begin { get }`  

```csharp
public System.UInt32 Begin { get; }
```

- `public System.UInt32 End { get }`  

```csharp
public System.UInt32 End { get; }
```


## Constructors

- `public NativeHeapBlock(Colossal.Collections.UnsafeHeapBlock block)`  

```csharp
public NativeHeapBlock(Colossal.Collections.UnsafeHeapBlock block);
```


