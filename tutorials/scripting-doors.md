# Scripting Doors

## Description

Create scriptable doors that make your map more interactive.

|||
|:--|:--|
|**Title**| How to Forge Interactive Maps in Halo Infinite |
|**Created By** | [@RedNomster](https://twitter.com/RedNomster)|
|**Reference URL**| https://youtu.be/m3u7XaHU47k|

## Double Doors

### Required Objects

* [Double Doorway](../objects/halo-design-set/doorways/double-doorway.md)
* [Floor Standard](../objects/halo-design-set/floors/floor-standard.md)
* [Script Brain](../objects/gameplay/scripting/script-brain.md)
* [Scriptable Switch (Invisible)](../objects/gameplay/scripting/scriptable-switch-invisible.md)

### Required Nodes

* [Move Object to Transform](../scripting/objects-transform/move-object-to-transform.md)
* [Object Reference](../scripting/variables-basic/object-reference.md)
* [On Object Interacted](../scripting/events-custom/on-object-interacted.md)

### &#x20;Steps

#### Add required objects

Add the required objects to map in order to setup a scripted double doorway.

* 2 - Double Doorway; Stacked back to back
* 4 - Floor Standard; side by side in the middle of the doorway
* 1 - Script Brain
* 1 - Scriptable Switch (Invisible)

![](../.gitbook/assets/images/tutorials/creating-doors-double-doors-1.png)

#### Object Reference - Switch

Select the Scriptable Switch, then go into Node Graph and place an **Add Object Reference** to the Scriptable Switch.

![Add Object Reference Node](../.gitbook/assets/images/tutorials/creating-doors-double-doors-2.png)

![Object Reference - Scriptable Switch](../.gitbook/assets/images/tutorials/creating-doors-double-doors-3.png)

#### Object Reference - Floors (Doors)

Add Object Reference nodes to each Floor Standard objects, similar to the step above.

![Object Reference - Floors](../.gitbook/assets/images/tutorials/creating-doors-double-doors-7.png)

#### Add Script Nodes

Add **Move Object to Transform** node and then an **On Object Interacted** node

![Move Object to Transform Node](../.gitbook/assets/images/tutorials/creating-doors-double-doors-4.png)

![On Object Interacted Node](../.gitbook/assets/images/tutorials/creating-doors-double-doors-5.png)

#### Configure Script Nodes

Connect the nodes; See [reference](scripting-doors.md#reference)

![](../.gitbook/assets/images/tutorials/creating-doors-double-doors-6.png)

{% hint style="info" %}
If you prefer to have a faster or slower door movement speed, adjust the amount of seconds on the **Move Object To Transform** node _Duration In Seconds_.
{% endhint %}

### Result

<figure><img src="https://i.imgur.com/IRceB9F.gif" alt=""><figcaption><p>Double Doors - Open</p></figcaption></figure>

## Automatic Doors

### Required Objects

* [Single Doorway A](../objects/halo-design-set/doorways/single-doorway-a.md)
* [Floor Standard](../objects/halo-design-set/floors/floor-standard.md)
* [Script Brain](../objects/gameplay/scripting/script-brain.md)
* [Pointer](../objects/gameplay/scripting/pointer.md)

### Required Nodes

* [Area Monitor](../scripting/variables-basic/area-monitor.md)
* [Branch](../scripting/logic/branch.md)
* [Move Object to Transform](../scripting/objects-transform/move-object-to-transform.md)
* [Object Reference](../scripting/variables-basic/object-reference.md)
* [On Object Entered Area](../scripting/events/on-object-entered-area.md)
* [On Object Exited Area](../scripting/events/on-object-exited-area.md)

### Steps

{% hint style="info" %}
_Optional_

Prior to adding objects, create a new folder in order to keep similar objects in the same working folder.
{% endhint %}

#### Add required objects

Add the required objects to map in order to setup a scripted automatic doorway.

* 2 - Single Doorway A; Stacked back to back
* 2 - Floor Standard; stacked on top of each other, one beneath the surface floor
* 1 - Script Brain
* 2 - Pointer; One pointer used as a boundary another a reference point

![Automatic Doors](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-3.png)

![Automatic Doors - Full](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-4.png)

![Automatic Doors - Folders](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-6.png)

#### Object Reference - Floors (Doors)

Add Object Reference nodes to each Floor Standard objects, then go into Node Graph and place an **Add Object Reference** for the doors.

![Object Reference - Doors](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-11.png)

#### Object Reference - Pointers

Select the Detector Pointer, then go into Node Graph and place an **Add Object Reference** to the Pointer.

![Object Reference - Pointers](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-12.png)

#### Set Pointer Boundary

Select and place the pointer in the desired placement. Set the boundary that fits the size of where you would like to monitor player movements.

![Detector - Boundary](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-1.png)

![Detector - Boundary](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-7.png)

![Area Monitor Boundary](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-10.png)

#### Set Reference Pointer

In order to close the door properly, the door must have a Destination Point to reference. Copy the coordinates of the **Closed** door to the same point as the reference pointer, this will ensure the door closes to its original coordinates.

![Reference Pointer Coordinates](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-8.png)

![Door Original Coordinates](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-9.png)

#### Configure Script Nodes

Connect the nodes; See [reference](scripting-doors.md#references)

![Automatic Doors - Script](../.gitbook/assets/images/tutorials/creating-doors-automatic-doors-5.png)

{% hint style="info" %}
In order for the script to properly run, you must have the references set correctly. Review the reference video on automatic doors for more information.
{% endhint %}

### Result

<figure><img src="https://i.imgur.com/jx4Ep53.gif" alt=""><figcaption><p>Automatic Doors - Open and Close</p></figcaption></figure>

## References

See the reference video by Red Nomster!

{% embed url="https://www.youtube.com/watch?v=m3u7XaHU47k" %}
Red Nomster - How to Forge Interactive Maps in Halo Infinite
{% endembed %}

|||
|:--|:--|
|**Page Authored By**| [@Nitro](https://twitter.com/NitroForged)|
|**Date**|  20 November 2022  |