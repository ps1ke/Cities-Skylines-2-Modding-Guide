# Game.Rendering.Utilities.HeapBlock

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Utilities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Rendering.Utilities.HeapBlock>`, `System.IEquatable<Game.Rendering.Utilities.HeapBlock>`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `public System.UInt64 begin`  
- `public System.UInt64 end`  

## Properties

- `public System.UInt64 Length { get }`  
- `public System.Boolean Empty { get }`  

## Constructors

- `public HeapBlock(System.UInt64 begin, System.UInt64 end)`  

## Methods

- `public CompareTo(Game.Rendering.Utilities.HeapBlock other) : System.Int32`  
- `public Equals(Game.Rendering.Utilities.HeapBlock other) : System.Boolean`  
- `public static OfSize(System.UInt64 begin, System.UInt64 size) : Game.Rendering.Utilities.HeapBlock`  

