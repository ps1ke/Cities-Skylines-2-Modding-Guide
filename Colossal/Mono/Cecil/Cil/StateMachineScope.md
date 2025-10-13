# Colossal.Mono.Cecil.Cil.StateMachineScope

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class StateMachineScope
{
    internal Colossal.Mono.Cecil.Cil.InstructionOffset start;
    internal Colossal.Mono.Cecil.Cil.InstructionOffset end;

    public Colossal.Mono.Cecil.Cil.InstructionOffset Start { get; set; }
    public Colossal.Mono.Cecil.Cil.InstructionOffset End { get; set; }

    internal StateMachineScope(System.Int32 start, System.Int32 end);
    public StateMachineScope(Colossal.Mono.Cecil.Cil.Instruction start, Colossal.Mono.Cecil.Cil.Instruction end);

}
```


## Fields

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset start`  

```csharp
internal Colossal.Mono.Cecil.Cil.InstructionOffset start;
```

- `internal Colossal.Mono.Cecil.Cil.InstructionOffset end`  

```csharp
internal Colossal.Mono.Cecil.Cil.InstructionOffset end;
```


## Properties

- `public Colossal.Mono.Cecil.Cil.InstructionOffset Start { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.InstructionOffset Start { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.InstructionOffset End { get; set }`  

```csharp
public Colossal.Mono.Cecil.Cil.InstructionOffset End { get; set; }
```


## Constructors

- `internal StateMachineScope(System.Int32 start, System.Int32 end)`  

```csharp
internal StateMachineScope(System.Int32 start, System.Int32 end);
```

- `public StateMachineScope(Colossal.Mono.Cecil.Cil.Instruction start, Colossal.Mono.Cecil.Cil.Instruction end)`  

```csharp
public StateMachineScope(Colossal.Mono.Cecil.Cil.Instruction start, Colossal.Mono.Cecil.Cil.Instruction end);
```


