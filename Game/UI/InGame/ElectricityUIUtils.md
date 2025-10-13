# Game.UI.InGame.ElectricityUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ElectricityUIUtils
{
    public static Game.Net.Layer GetPowerLineLayers(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefabEntity);
    public static Game.UI.InGame.VoltageLocaleKey GetVoltage(Game.Net.Layer layers);
    public static System.Boolean HasVoltageLayers(Game.Net.Layer layers);
}
```


## Methods

- `public static GetPowerLineLayers(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefabEntity) : Game.Net.Layer`  

```csharp
public static Layer GetPowerLineLayers(EntityManager entityManager, Entity prefabEntity)
	{
		Layer layer = Layer.None;
		if (entityManager.HasComponent<TransformerData>(prefabEntity))
		{
			layer |= Layer.PowerlineLow;
		}
		if (entityManager.TryGetBuffer(prefabEntity, isReadOnly: true, out DynamicBuffer<Game.Prefabs.SubNet> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity prefab = buffer[i].m_Prefab;
				if (entityManager.HasComponent<ElectricityConnectionData>(prefab) && entityManager.TryGetComponent<NetData>(prefab, out var component))
				{
					layer |= component.m_LocalConnectLayers;
				}
			}
		}
		return layer & (Layer.PowerlineLow | Layer.PowerlineHigh);
	}
```

- `public static GetVoltage(Game.Net.Layer layers) : Game.UI.InGame.VoltageLocaleKey`  

```csharp
public static VoltageLocaleKey GetVoltage(Layer layers)
	{
		return (layers & (Layer.PowerlineLow | Layer.PowerlineHigh)) switch
		{
			Layer.PowerlineLow => VoltageLocaleKey.Low, 
			Layer.PowerlineHigh => VoltageLocaleKey.High, 
			_ => VoltageLocaleKey.Both, 
		};
	}
```

- `public static HasVoltageLayers(Game.Net.Layer layers) : System.Boolean`  

```csharp
public static bool HasVoltageLayers(Layer layers)
	{
		return (layers & (Layer.PowerlineLow | Layer.PowerlineHigh)) != 0;
	}
```


