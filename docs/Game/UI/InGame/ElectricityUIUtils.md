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
public static Game.Net.Layer GetPowerLineLayers(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefabEntity);
```

- `public static GetVoltage(Game.Net.Layer layers) : Game.UI.InGame.VoltageLocaleKey`  

```csharp
public static Game.UI.InGame.VoltageLocaleKey GetVoltage(Game.Net.Layer layers);
```

- `public static HasVoltageLayers(Game.Net.Layer layers) : System.Boolean`  

```csharp
public static System.Boolean HasVoltageLayers(Game.Net.Layer layers);
```


