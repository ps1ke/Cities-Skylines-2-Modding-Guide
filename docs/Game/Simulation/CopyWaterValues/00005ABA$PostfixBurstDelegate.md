# Game.Simulation.SurfaceDataReader+Game.Simulation.CopyWaterValues_00005ABA$PostfixBurstDelegate

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class sealed public  

**Base:** `System.MulticastDelegate`  
**Implements:** `System.ICloneable`, `System.Runtime.Serialization.ISerializable`  

## Code

```csharp
public sealed class CopyWaterValues_00005ABA$PostfixBurstDelegate : System.MulticastDelegate, System.ICloneable, System.Runtime.Serialization.ISerializable
{
    public CopyWaterValues_00005ABA$PostfixBurstDelegate(System.Object , System.IntPtr );

    public virtual System.IAsyncResult BeginInvoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex, System.AsyncCallback , System.Object );
    public virtual System.Void EndInvoke(System.IAsyncResult );
    public virtual System.Void Invoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex);
}
```


## Constructors

- `public CopyWaterValues_00005ABA$PostfixBurstDelegate(System.Object , System.IntPtr )`  

```csharp
public CopyWaterValues_00005ABA$PostfixBurstDelegate(System.Object , System.IntPtr );
```


## Methods

- `public virtual BeginInvoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex, System.AsyncCallback , System.Object ) : System.IAsyncResult`  

```csharp
public virtual System.IAsyncResult BeginInvoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex, System.AsyncCallback , System.Object );
```

- `public virtual EndInvoke(System.IAsyncResult ) : System.Void`  

```csharp
public virtual System.Void EndInvoke(System.IAsyncResult );
```

- `public virtual Invoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex) : System.Void`  

```csharp
public virtual System.Void Invoke(UnityEngine.Rendering.AsyncGPUReadbackRequest& asyncReadback, Unity.Collections.NativeArray`1[[Game.Simulation.SurfaceWater, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpu, Unity.Collections.NativeArray`1[[Unity.Mathematics.float4, Unity.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cpuTemp, Unity.Jobs.JobHandle& readers, Unity.Mathematics.int2& texSize, System.Boolean& pendingReadback, System.Int32 readbackDistribution, System.Int32 readbackIndex);
```


