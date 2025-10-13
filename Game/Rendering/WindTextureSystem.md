# Game.Rendering.WindTextureSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class WindTextureSystem : Game.GameSystemBase
{
    private Game.Simulation.WindSystem m_WindSystem;
    private UnityEngine.Texture2D m_WindTexture;
    private Unity.Jobs.JobHandle m_UpdateHandle;
    private System.Boolean m_RequireUpdate;
    private System.Boolean m_RequireApply;

    public UnityEngine.Texture2D WindTexture { get; }

    public WindTextureSystem();

    public System.Void CompleteUpdate();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void RequireUpdate();
}
```


## Fields

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private UnityEngine.Texture2D m_WindTexture`  

```csharp
private UnityEngine.Texture2D m_WindTexture;
```

- `private Unity.Jobs.JobHandle m_UpdateHandle`  

```csharp
private Unity.Jobs.JobHandle m_UpdateHandle;
```

- `private System.Boolean m_RequireUpdate`  

```csharp
private System.Boolean m_RequireUpdate;
```

- `private System.Boolean m_RequireApply`  

```csharp
private System.Boolean m_RequireApply;
```


## Properties

- `public UnityEngine.Texture2D WindTexture { get }`  

```csharp
public UnityEngine.Texture2D WindTexture { get; }
```


## Constructors

- `public WindTextureSystem()`  

```csharp
[Preserve]
	public WindTextureSystem()
	{
	}
```


## Methods

- `public CompleteUpdate() : System.Void`  

```csharp
public void CompleteUpdate()
	{
		if (m_RequireApply)
		{
			m_RequireApply = false;
			m_UpdateHandle.Complete();
			m_WindTexture.Apply();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_WindTexture = new Texture2D(WindSystem.kTextureSize, WindSystem.kTextureSize, TextureFormat.RGFloat, mipChain: false, linear: true)
		{
			name = "WindTexture",
			hideFlags = HideFlags.HideAndDontSave
		};
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_RequireUpdate)
		{
			m_RequireUpdate = false;
			m_RequireApply = true;
			JobHandle dependencies;
			WindTextureJob jobData = new WindTextureJob
			{
				m_WindMap = m_WindSystem.GetMap(readOnly: true, out dependencies),
				m_WindTexture = m_WindTexture.GetRawTextureData<float2>()
			};
			m_UpdateHandle = jobData.Schedule(WindSystem.kTextureSize * WindSystem.kTextureSize, dependencies);
			m_WindSystem.AddReader(m_UpdateHandle);
		}
	}
```

- `public RequireUpdate() : System.Void`  

```csharp
public void RequireUpdate()
	{
		m_RequireUpdate = true;
	}
```


## Nested types

- `Game.Rendering.WindTextureSystem+WindTextureJob`  

