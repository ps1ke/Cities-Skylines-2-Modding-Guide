# Colossal.Json.PositionTrackingStringReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class public  

**Base:** `System.IO.StringReader`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class PositionTrackingStringReader : System.IO.StringReader, System.IDisposable
{
    private System.String input;
    private System.Int32 start;
    private System.Int32 position;

    public PositionTrackingStringReader(System.String input);

    public System.String GetBlock();
    public System.String GetBounds(System.Int32 count);
    public System.Char GetCharacter();
    public virtual System.Int32 Read();
    public virtual System.Int32 Read(System.Char[] buffer, System.Int32 index, System.Int32 count);
    public virtual System.String ReadLine();
    public virtual System.String ReadToEnd();
    public System.Void TagStart();
}
```


## Fields

- `private System.String input`  

```csharp
private System.String input;
```

- `private System.Int32 start`  

```csharp
private System.Int32 start;
```

- `private System.Int32 position`  

```csharp
private System.Int32 position;
```


## Constructors

- `public PositionTrackingStringReader(System.String input)`  

```csharp
public PositionTrackingStringReader(System.String input);
```


## Methods

- `public GetBlock() : System.String`  

```csharp
public System.String GetBlock();
```

- `public GetBounds(System.Int32 count) : System.String`  

```csharp
public System.String GetBounds(System.Int32 count);
```

- `public GetCharacter() : System.Char`  

```csharp
public System.Char GetCharacter();
```

- `public virtual Read() : System.Int32`  

```csharp
public virtual System.Int32 Read();
```

- `public virtual Read(System.Char[] buffer, System.Int32 index, System.Int32 count) : System.Int32`  

```csharp
public virtual System.Int32 Read(System.Char[] buffer, System.Int32 index, System.Int32 count);
```

- `public virtual ReadLine() : System.String`  

```csharp
public virtual System.String ReadLine();
```

- `public virtual ReadToEnd() : System.String`  

```csharp
public virtual System.String ReadToEnd();
```

- `public TagStart() : System.Void`  

```csharp
public System.Void TagStart();
```


