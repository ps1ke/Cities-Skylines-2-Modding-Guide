# Game.Serialization.ReadBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Serialization.Entities.IReadBuffer`  

## Code

```csharp
public class ReadBuffer : Colossal.Serialization.Entities.IReadBuffer
{
    private Unity.Collections.NativeArray<System.Byte> <buffer>k__BackingField;
    private Unity.Collections.NativeReference<System.Int32> <position>k__BackingField;

    public Unity.Collections.NativeArray<System.Byte> buffer { get; private set; }
    public Unity.Collections.NativeReference<System.Int32> position { get; private set; }

    public ReadBuffer(System.Int32 size);

    public System.Void Done(Unity.Jobs.JobHandle handle);
    public System.Void Done();
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Byte> <buffer>k__BackingField`  

```csharp
private Unity.Collections.NativeArray<System.Byte> <buffer>k__BackingField;
```

- `private Unity.Collections.NativeReference<System.Int32> <position>k__BackingField`  

```csharp
private Unity.Collections.NativeReference<System.Int32> <position>k__BackingField;
```


## Properties

- `public Unity.Collections.NativeArray<System.Byte> buffer { get; private set }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> buffer { get; private set; }
```

- `public Unity.Collections.NativeReference<System.Int32> position { get; private set }`  

```csharp
public Unity.Collections.NativeReference<System.Int32> position { get; private set; }
```


## Constructors

- `public ReadBuffer(System.Int32 size)`  

```csharp
public ReadBuffer(System.Int32 size);
```


## Methods

- `public Done(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void Done(Unity.Jobs.JobHandle handle);
```

- `public Done() : System.Void`  

```csharp
public System.Void Done();
```


