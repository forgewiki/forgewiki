# Scripting Doors

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

### Steps

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

## Reference

See the reference video by Red Nomster!

{% embed url="https://www.youtube.com/watch?v=m3u7XaHU47k" %}
Red Nomster - How to Forge Interactive Maps in Halo Infinite
{% endembed %}
