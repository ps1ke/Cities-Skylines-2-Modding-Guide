# Game.Simulation.TransformerData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TransformerData
{
    public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_Deleted;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefs;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ElectricityConnectionData> m_ElectricityConnectionDatas;
    public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
    public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets;
    public Unity.Entities.ComponentLookup<Game.Net.Node> m_NetNodes;
    public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityNodeConnection> m_ElectricityNodeConnections;
    public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityValveConnection> m_ElectricityValveConnections;
    public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_FlowConnections;
    public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges;

    public System.Void GetTransformerData(Unity.Entities.Entity entity, System.Int32& capacity, System.Int32& flow);
    private System.Void ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow);
    private System.Void ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_Deleted`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_Deleted;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefs;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ElectricityConnectionData> m_ElectricityConnectionDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ElectricityConnectionData> m_ElectricityConnectionDatas;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NetNodes`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Node> m_NetNodes;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityNodeConnection> m_ElectricityNodeConnections`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityNodeConnection> m_ElectricityNodeConnections;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityValveConnection> m_ElectricityValveConnections`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityValveConnection> m_ElectricityValveConnections;
```

- `public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_FlowConnections`  

```csharp
public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_FlowConnections;
```

- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges`  

```csharp
public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges;
```


## Methods

- `public GetTransformerData(Unity.Entities.Entity entity, System.Int32& capacity, System.Int32& flow) : System.Void`  

```csharp
public System.Void GetTransformerData(Unity.Entities.Entity entity, System.Int32& capacity, System.Int32& flow);
```

- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  

```csharp
private System.Void ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow);
```

- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  

```csharp
private System.Void ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow);
```


