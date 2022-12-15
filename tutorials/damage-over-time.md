# Damage Over Time

## Description

Create prograssively more complex damage over time (DoT) scripts. The following are themed after a poison effect commonly found in RPGs.

## Required Objects

* [Script Brain](objects\gameplay\scripting\script-brain.md)
* [Named Location Volume](objects\gameplay\volumes\named-location-volume.md)

{% hint style="info" %}
A _Named Location Volume_ is used in this tutorial for simplicity but any object can be used if its _Object Mode_ can be set to _Dynamic_ and given a _Gameplay Boundary_.
{% endhint %}

## Part 1: The Danger Zone

### The Goal

The simplest DoT effect we can make is going to be a zone that deals damage to anything inside its boundaries. A common use case for this is a "the floor is lava" scenario.

We're going to accomplish this in the following manner:

1. Define the boundaries of the zone.
2. Deal damage to each object in the zone.

{% hint style="info" %}
Players are registered as entering or exiting a boundary based on their midsection. If the bottom of a boundary is aligned with the ground, then distance to the top will need to be at least 3.6 units to register a standing and 2.5 units for a crouching Spartan.
{% endhint %}

### Required Nodes

* x1 - [Every N Seconds](scripting\events-custom\every-n-seconds.md)
* x1 - [For Each Object](scripting\logic\for-each-object.md)
* x1 - [Damage Object](scripting\objects\damage-object.md)
* x1 - [Get Objects In Area Monitor](scripting\objects\get-objects-in-area-monitor.md)
* x1 - [Area Monitor](scripting\variables-basic\area-monitor.md)
* x1 - [Object Reference](scripting\variables-basic\object-reference.md)

{% hint style="info" %}
The _For Each Object_ node is effectively interchangable with the _For Each Player_ node. The only difference between the two is that the player version will ignore all non-player objects in the supplied list. The object version is required to **also** damage any other objects that have health, e.g. vehicles and destructibles.
{% endhint %}

### Steps

#### Add Objects {#part-1-objects}

Add a _Script Brain_ anywhere to the map. These are located under Gameplay 🡒 Scripting.

Add a _Named Location Volume_ and adjust its position and boundary to fit your needs. These are located under Gameplay 🡒 Volumes.

Give this volume a name. _Danger Zone_ will be used for the duration of this tutorial.

{% hint style="info" %}
Naming objects for scripting is optional. However, names you provide will likely be more effective than the default.
{% endhint %}

![Danger Zone Properties](../.gitbook/assets/images/tutorials/damage-over-time/danger-zone-properties.png)

#### Select References {#part-1-references}

Select the _Script Brain_ and _Danger Zone_ and enter the node graph.

{% hint style="info" %}
Selecting the _Script Brain_ before entering a node graph will guarantee you enter the brain you intend to edit. Forge will remember which brain you were in last.
{% endhint %}

#### Add Nodes {#part-1-nodes}

Once inside the node graph, pressing Y will bring up a secondary menu with the option _Add Object Reference_ and populate an _Object Reference_ node for each _Dynamic_ object that was selected. You will need to delete the _Script Brain_ reference if you had it selected as we will not be using it.

The remaining required nodes are located under:

* Events Custom
* Logic
* Objects
* Variables Basic

#### Configure Nodes {#part-1-config}

Configuring the nodes is fairly straightforward. The 2 pins you should note are the _Seconds_ and _Damage Amount_ on the _Every N Seconds_ and _Damage Object_ nodes respectively. This should be fairly obvious, but they will determine the rate and amount of damage.

{% hint style="info" %}
The _Every N Seconds_ node provides us with a technique called polling. It will ensure that all connected nodes are executed at a regular interval.
{% endhint %}

![Danger Zone Script](../.gitbook/assets/images/tutorials/damage-over-time/danger-zone-script.png)

### Result

![Damage Zone Result](../.gitbook/assets/images/tutorials/damage-over-time/danger-zone-result.gif)

## Part 2: Lingering Damage

### The Goal

Expanding upon the last script, what we want to do now is have a brief period of time when damage continues if a player leaves the _Danger Zone_ as if they have been poisoned. To accomplish this, we will need to record a list of players that have entered the _Danger Zone_ and start a timer when they exit to remove them from this list.

### Required Nodes

* x1 - [On Object Entered Area](../scripting/events/on-object-entered-area.md)
* x1 - [On Object Exited Area](../scripting/events/identifier.md)
* x1 - [Wait For N Seconds](../scripting/logic/wait-for-n-seconds.md)
* x1 - [Add Object To List](../scripting/objects/add-object-to-list.md)
* x1 - [Remove Object from List](../scripting/objects/remove-object-from-list.md)
* x1 - [Delcare Object List Variable](../scripting/variables-advanced/declare-object-list-variable.md)
* x1 - [Get Object List Variable](../scripting/variables-advanced/get-object-list-variable.md)
* x2 - [Set Object List Variable](../scripting/variables-advanced/set-object-list-variable.md)
* x1 - [Identifier](../scripting/variables-basic/identifier.md)

{% hint style="info" %}
The _Identifier_ node is optional, but it will make the configuring of the nodes simpler and save time as you will only have to connect pins instead of typing the name you want to use into every other node.
{% endhint %}

### Steps

#### Add Objects {#part-2-objects}

If you've followed along from the last part, there are no new objects to add. See [part 1 objects](#part-1-objects) for the already existing objects.

#### Select References {#part-2-references}

There are no new references, so see [part 2 references](#part-2-references) for the already existing references.

#### Add Nodes {#part-2-nodes}

We won't need the _Get Objects In Area Monitor_ node anymore, so it can be deleted. The new required nodes are located under:

* Events
* Logic
* Objects
* Variables Advanced
* Variables Basic

In order to replicate what the _Get Objects In Area Monitor_ node was doing for us before, we're going to use the _Declare Object List Variable_ that will record what objects have entered and exited the _Danger Zone_. Due to the nature of scripting, you can safely assume that when you get or set declared variables, they will up to date when the node runs.

{% hint style="info" %}
There are 3 types of variable scope. Most of the time, _Local_ will be good enough for anything you need to script.
{% endhint %}

#### Configure Nodes {#part-2-config}

The biggest change to the [part 1 config](#part-1-config) is we will have 2 main sections to the script. The top is our poll from part 1 that will deal the damage to everything in the declared list at a regular interval. The bottom will manage what objects are in the declared list.

2 _Set Object List Variable_ nodes are required due to the restriction that nodes with diamond pins may only be connected to a single event node. Everything else is fairly straightforward. Note the _Seconds_ pin in the _Wait For N Seconds_ node. This will determine how long you want the poison effect to last after the object leaves the _Danger Zone_.

![Lingering Damage Script](../.gitbook/assets/images/tutorials/damage-over-time/lingering-damage-script.png)

### Result

![Lingering Damage Result](../.gitbook/assets/images/tutorials/damage-over-time/lingering-damage-result.gif)

## Part 3: Curing The Effect

### The Goal

description

### Required Nodes

nodes

### Steps

steps

#### Add Objects

objects

#### Select References

references

#### Add Nodes

nodes

#### Configure Nodes

config

### Result

result

## Part 4: Poison Guns

### The Goal

description

### Required Nodes

nodes

### Steps

steps

#### Add Objects

objects

#### Select References

references

#### Add Nodes

nodes

#### Configure Nodes

config

### Result

result
