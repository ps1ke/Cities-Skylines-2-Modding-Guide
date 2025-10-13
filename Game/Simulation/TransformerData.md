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
public void GetTransformerData(Entity entity, out int capacity, out int flow)
	{
		int lowVoltageCapacity = 0;
		int highVoltageCapacity = 0;
		flow = 0;
		if (m_SubNets.TryGetBuffer(entity, out var bufferData))
		{
			ProcessMarkerNodes(bufferData, ref lowVoltageCapacity, ref highVoltageCapacity, ref flow);
		}
		if (m_InstalledUpgrades.TryGetBuffer(entity, out var bufferData2))
		{
			ProcessMarkerNodes(bufferData2, ref lowVoltageCapacity, ref highVoltageCapacity, ref flow);
		}
		capacity = math.min(lowVoltageCapacity, highVoltageCapacity);
	}
```

- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  

```csharp
private void ProcessMarkerNodes(DynamicBuffer<Game.Net.SubNet> subNets, ref int lowVoltageCapacity, ref int highVoltageCapacity, ref int flow)
	{
		for (int i = 0; i < subNets.Length; i++)
		{
			Entity subNet = subNets[i].m_SubNet;
			if (!m_NetNodes.HasComponent(subNet) || m_Deleted.HasComponent(subNet) || !m_ElectricityNodeConnections.TryGetComponent(subNet, out var componentData) || !m_ElectricityValveConnections.TryGetComponent(subNet, out var componentData2) || !m_PrefabRefs.TryGetComponent(subNet, out var componentData3) || !m_ElectricityConnectionDatas.TryGetComponent(componentData3.m_Prefab, out var componentData4))
			{
				continue;
			}
			if (componentData4.m_Voltage == Game.Prefabs.ElectricityConnection.Voltage.Low)
			{
				lowVoltageCapacity += componentData4.m_Capacity;
				if (ElectricityGraphUtils.TryGetFlowEdge(componentData2.m_ValveNode, componentData.m_ElectricityNode, ref m_FlowConnections, ref m_FlowEdges, out ElectricityFlowEdge edge))
				{
					flow += edge.m_Flow;
				}
			}
			else
			{
				highVoltageCapacity += componentData4.m_Capacity;
			}
		}
	}
```

- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  

```csharp
private void ProcessMarkerNodes(DynamicBuffer<Game.Net.SubNet> subNets, ref int lowVoltageCapacity, ref int highVoltageCapacity, ref int flow)
	{
		for (int i = 0; i < subNets.Length; i++)
		{
			Entity subNet = subNets[i].m_SubNet;
			if (!m_NetNodes.HasComponent(subNet) || m_Deleted.HasComponent(subNet) || !m_ElectricityNodeConnections.TryGetComponent(subNet, out var componentData) || !m_ElectricityValveConnections.TryGetComponent(subNet, out var componentData2) || !m_PrefabRefs.TryGetComponent(subNet, out var componentData3) || !m_ElectricityConnectionDatas.TryGetComponent(componentData3.m_Prefab, out var componentData4))
			{
				continue;
			}
			if (componentData4.m_Voltage == Game.Prefabs.ElectricityConnection.Voltage.Low)
			{
				lowVoltageCapacity += componentData4.m_Capacity;
				if (ElectricityGraphUtils.TryGetFlowEdge(componentData2.m_ValveNode, componentData.m_ElectricityNode, ref m_FlowConnections, ref m_FlowEdges, out ElectricityFlowEdge edge))
				{
					flow += edge.m_Flow;
				}
			}
			else
			{
				highVoltageCapacity += componentData4.m_Capacity;
			}
		}
	}
```


