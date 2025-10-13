# Colossal.Mono.Cecil.Cil.OpCodes

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class OpCodes
{
    internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] OneByteOpCode;
    internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] TwoBytesOpCode;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Nop;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Break;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_0;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_3;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_0;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_3;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_0;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_3;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldnull;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_M1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_0;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_3;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_5;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_6;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_7;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Dup;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Pop;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Jmp;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Call;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Calli;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ret;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Br_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Br;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Switch;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_Ref;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_Ref;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Add;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Div;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Div_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode And;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Or;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Xor;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Shl;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Neg;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Not;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Callvirt;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpobj;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldobj;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldstr;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Newobj;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Castclass;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Isinst;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Throw;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldfld;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldflda;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stfld;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsfld;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsflda;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stsfld;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stobj;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Box;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Newarr;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldlen;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelema;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Ref;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Ref;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Any;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Any;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox_Any;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanyval;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ckfinite;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Mkrefany;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldtoken;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U2;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U1;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfinally;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave_S;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Arglist;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ceq;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt_Un;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldftn;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldvirtftn;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Localloc;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfilter;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Unaligned;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Volatile;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Tail;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Initobj;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Constrained;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpblk;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Initblk;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode No;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Rethrow;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Sizeof;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanytype;
    public static readonly Colossal.Mono.Cecil.Cil.OpCode Readonly;

}
```


## Fields

- `internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] OneByteOpCode`  

```csharp
internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] OneByteOpCode;
```

- `internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] TwoBytesOpCode`  

```csharp
internal static readonly Colossal.Mono.Cecil.Cil.OpCode[] TwoBytesOpCode;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Nop`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Nop;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Break`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Break;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_0`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_0;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_3`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_3;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_0`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_0;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_3`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_3;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_0`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_0;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_3`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_3;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldnull`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldnull;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_M1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_M1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_0`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_0;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_3`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_3;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_5`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_5;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_6`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_6;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_7`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_7;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldc_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Dup`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Dup;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Pop`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Pop;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Jmp`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Jmp;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Call`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Call;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Calli`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Calli;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ret`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ret;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Br_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Br_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Br`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Br;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Brfalse;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Brtrue;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Beq;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bne_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bge_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Bgt_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ble_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Blt_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Switch`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Switch;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_U4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_Ref`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldind_Ref;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_Ref`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_Ref;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Add`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Add;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Div`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Div;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Div_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Div_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Rem_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode And`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode And;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Or`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Or;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Xor`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Xor;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Shl`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Shl;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Shr_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Neg`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Neg;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Not`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Not;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Callvirt`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Callvirt;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpobj`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpobj;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldobj`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldobj;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldstr`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldstr;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Newobj`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Newobj;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Castclass`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Castclass;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Isinst`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Isinst;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_R_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Throw`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Throw;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldfld`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldfld;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldflda`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldflda;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stfld`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stfld;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsfld`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsfld;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsflda`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldsflda;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stsfld`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stsfld;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stobj`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stobj;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Box`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Box;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Newarr`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Newarr;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldlen`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldlen;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelema`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelema;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_U4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Ref`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Ref;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_R8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Ref`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Ref;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Any`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldelem_Any;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Any`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stelem_Any;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox_Any`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Unbox_Any;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U4;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U8;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanyval`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanyval;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ckfinite`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ckfinite;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Mkrefany`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Mkrefany;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldtoken`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldtoken;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U2`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U2;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U1`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U1;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_Ovf_U;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Add_Ovf_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Mul_Ovf_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Sub_Ovf_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfinally`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfinally;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave_S`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Leave_S;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stind_I;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Conv_U;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Arglist`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Arglist;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ceq`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ceq;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Cgt_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt_Un`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Clt_Un;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldftn`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldftn;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldvirtftn`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldvirtftn;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarg;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldarga;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Starg;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloc;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Ldloca;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Stloc;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Localloc`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Localloc;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfilter`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Endfilter;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Unaligned`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Unaligned;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Volatile`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Volatile;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Tail`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Tail;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Initobj`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Initobj;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Constrained`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Constrained;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpblk`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Cpblk;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Initblk`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Initblk;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode No`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode No;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Rethrow`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Rethrow;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Sizeof`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Sizeof;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanytype`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Refanytype;
```

- `public static readonly Colossal.Mono.Cecil.Cil.OpCode Readonly`  

```csharp
public static readonly Colossal.Mono.Cecil.Cil.OpCode Readonly;
```


