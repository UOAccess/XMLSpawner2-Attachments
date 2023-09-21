
# XmlParagon v1.00

**Updated**: 2/25/08  
**Author**: ArteGordon

## Summary

An Xmlspawner attachment that can be applied to individual xmlspawners to customize paragon spawns from that spawner. Various paragon spawning properties can be set such as buff factors, conversion rate, artifact drop rate, chest drop rate, hue, labels. Paragon spawning on the spawner can also be entirely disabled.

## Description

To use this system, add the XmlParagon attachment to any xmlspawner by using the command:  
```
[addatt xmlparagon
```
Then target an xmlspawner. You can edit the xmlparagon properties by using the command:

```
[getatt
```

And targeting the xmlspawner to open the attachments gump and then selecting the properties button on the XmlParagon attachment.

### Customization

Custom paragon attachments can also be scripted with different default behavior. Some simple examples have been included:

- `MLParagon.cs` changes the artifact drops to ML artifacts.
- `WeakParagon.cs` is an XmlParagon attachment with weaker default buff factors.

#### Overridable Methods

Custom attachments derived from the XmlParagon attachment can also be scripted with the following methods that can be overridden for further customization:

- `XmlAddChest(BaseCreature bc, int treasureLevel)`
- `XmlChestChance(BaseCreature bc)`
- `XmlGetParagonLabel(BaseCreature bc)`
- `XmlConvert(BaseCreature bc)`
- `XmlUnConvert(BaseCreature bc)`
- `XmlCheckConvert(BaseCreature bc, Point3D location, Map m)`
- `XmlCheckArtifactChance(Mobile m, BaseCreature bc)`
- `XmlGiveArtifactTo(Mobile m, BaseCreature bc)`

## Installation

This system involves making six modifications to the `BaseCreature` script. No other scripts are affected. Standard paragon spawning on spawners that do not have this attachment is not affected by this system.

### Steps

1. **Install XmlSpawner2**: This system only works with xmlspawners. Other spawning systems will not be affected.

2. **Modify BaseCreature.cs**: Add the following line at the top.

    ```csharp
    using Server.Engines.XmlSpawner2;
    ```

    **Further Modifications**: Change lines around 368, 542, 770, 915, 3903, and 4324 as described in the original document.
