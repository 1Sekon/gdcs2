---
draft: false
title: Making Logic Gates
weight: 6080
date: 2024-09-16T00:00:00.000Z
authors:
  - tanhr
contributors:
  - chuckolate
  - tanhr
description: Logic gates receive truth values and output a single truth value, making them essential tools for creating conditions. This guide explains the AND, NOT, OR, and XOR gates and how to combine them into more complex trigger setups.
tags:
  - Grade 2
  - Trigger Setups
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

- Logic gates receive a set of conditions and output a true or false statement.
- They can be combined in various ways to set up more complex conditions.
- Logic gates have a wide range of applications and are fundamental tools for giving instructions to a program or trigger setup.

{{< /callout >}}

** **

Logic gates, also known as logic operators or comparisons, are functions that **receive one or more *truth values* and output a single *truth value***. A **truth value** is a statement that is either TRUE or FALSE. Logic gates are the basis of computer science, so they are essential in the design and operation of any kind of system, including Geometry Dash triggers. In GD's case, a true output may result in a trigger being activated, while a false output may not. It can also result in a group being toggled on for a true output and being toggled off for a false one.

There are 3 main logic gates: AND, NOT, and OR logic gates. There is also the XOR logic gate but it isn't frequently used; it will still be included in this guide in case you need it. These 4 basic gates can be combined in various ways in order to create more complex logic gates. As an example, you can get a new gate by adding a NOT at the end of the 3 other gates: NOT AND becomes NAND, NOT OR becomes NOR and NOT XOR becomes XNOR.

Usually logic gates are used with 2 input statements, however some of the gate implementations you will see can be extended to use as many inputs as you so desire, as we will soon cover here.

# 1: Truth Types

Before we define what each logic gate does and show ways to implement them into GD, we must first understand how we can translate truth values into GD triggers. There are three **truth types** that you will have to manage.

## Spawn truth type

This is the most universal truth type. In this case, __a truth value `A` is true if *group `A` is spawned* and conversely, is false if *nothing is spawned*__. This is the truth type that condition triggers use. Geometry Dash triggers are made in such a way that you can convert any truth type into a spawn truth and convert a spawn truth into any truth type (this will be discussed in a later chapter).

## Toggle Truth Type

In this truth type, __a truth value `A` is true if *group `A` is toggled on*, and is false if *it is toggled off*__. The toggle truth is the most simple way to store a truth value over time, as you only need to use a toggle trigger to activate or toggle off the triggers or objects you want, and also because it is more intuitive to check if an object is toggled on or off, compared to if a group is spawned or not.

## Item Truth Type

You can represent TRUE and FALSE values as being a 1 or a 0 respectively. This allows you to use an Item ID to store truth values. This way, in an **item truth type**, __a truth value is true if *the number stored in the Item ID is 1* and is false if *it is 0*__. The 2.2 update offers some very interesting ways to interact with Item IDs, so this truth type can be useful for more advanced applications like binary calculus. Note that this method is less optimized since you are using a number to store something that is never bigger than 1, and also is not as useful for spawning sequences.

# 2: AND Gate

## What is the AND Logic Gate?
The **AND logic gate** receives two truth values, let's say value `A` and value `B`, __and outputs TRUE only if both `A` *and* `B` are TRUE__. So for instance, if you input a condition that is false and another condition that is true, the AND logic gate will output false.
In order to cover all the possible outputs a logic gate can yield given all the possible combinations of inputs it can receive, we can use a **truth table**. __A logic gate's truth table is a table where to the table's left are listed all the possibilities of inputs, whereas to the table’s right the corresponding output is stated__. Here is the truth table for the AND gate:

{{< img src="https://lh3.googleusercontent.com/d/1OCfqvGWRyHscRPNee2832ep545bYdNBb" >}}

If you replace the TRUE and FALSE values by binary 1s and 0s, you can notice that the AND gate does a multiplication between `A` and `B`.

{{< img src="https://lh3.googleusercontent.com/d/18GcjAv_sR1epIjwum-vQWFxwyHRn9Av1" >}}

## What is it Used for?

The AND gate is usually used to activate something only if a set of conditions is valid. You can also use it as a literal gate: if `A` is TRUE, then let `B` through, but if `A` is FALSE, then block `B`.

It is also used to define AND gates that use more than two inputs. This is done by chaining multiple AND gates. For example, if you want to define an AND gate that takes three inputs `A`, `B` and `C`, you would use two AND logic gates as follows: (`A` AND `B`) AND `C`. Here, all of the inputs must be TRUE so that the output is also TRUE.

## Ways to make it in GD
There are a handful of ways you can implement an AND gate using GD triggers. For each setup, we will specify what truth type(s) the gate takes as input, what truth type the gate outputs, and how many inputs the setup can hold.

**Toggle Setup**

- Input type: Toggle truth
- Output type: Toggle truth
- Several inputs

When you give an object multiple groups, the object will be toggled on if every group it has is toggled on. If one or more of the groups is toggled off, the object will be toggled off. Here is an example of a block that only shows when both groups 1 *and* 2 are toggled on.

{{< youtube f_J4Atvj5fo >}}

**Chaining Conditions**

- Input type: Spawn/toggle truth
- Output type: Spawn truth
- Several inputs

This setup makes use of a chain of triggers where each trigger spawns its following. You can use conditional triggers that will only continue the chain if the condition inside of them is true, like Count, Instant Count, Collision or Instant Collision triggers. This way, the final group of the chain will spawn only if all the conditions inside the chain are true.

You would do it like this:
1. Place a condition trigger that activates your output group.
2. Give this trigger a new group and set it to spawn trigger (multi trigger if you want to activate the gate several times).
3. Add another condition trigger that spawns the group you just made.
4. Repeat for how many conditions you want.
Here is an example of making the BG pulse when Item ID 1 is 3 *and* Item ID 2 is 4.

{{< youtube bljVgtqF4Ds >}}

If you also want to use Toggle triggers as input, give any element of the chain (the output included) the groups you want to have toggled on in order to activate the output. Here is an example of a BG pulse only occurring if group 2 is toggled on *and* Item ID 1 is 4.

{{< youtube OG603p-gN9U>}}

**Item Edit Setup**

- Input type: Item truth
- Output type: Item truth
- 2 inputs

Using an Item Edit trigger, you can compute the operation `A` AND `B` by multiplying your input Item IDs and then storing the result in another Item ID. Here is how you can store the result of Item ID 1 *and* Item ID 2 in Item ID 3:

{{< img src="https://lh3.googleusercontent.com/d/1EJJHGrbjxo_byketTYVnA1N1LdIZoTFM" >}}

# 3: OR Gate

## What is the OR Logic Gate?
The **OR logic gate** receives two truth values `A` and `B`, __and outputs TRUE when `A` is true, `B` is true, or both `A` and `B` are true__. This means that you will get a true output only if *at least one of the inputs is true*, i.e., every input is sufficient. Here’s the OR logic gate truth table:

{{< img src="https://lh3.googleusercontent.com/d/12Rmsc6xBQSC6V5DKLGTdGAelGaj2J4SL" >}}

## What is it Used for?

The OR gate is actually the one with the most intuitive use; you use one without realizing every time you have several ways to activate something. The OR gate is also used when making more complex logic gates.

For instance, just like with the AND gate, you can chain multiple OR gates to get an OR gate that receives multiple inputs. In fact, you can do that with any logic gate that has two or more inputs in order to define a gate of as many inputs as you want.

## Ways to make it in GD

**Spawn Setup**

- Input type: Spawn truth
- Output type: Spawn truth
- Several inputs

You can give your output trigger several groups, as each one of them will be a sufficient condition to activate the output. In this example the background will pulse if Item ID 1 is 3 *or* 5.

{{< img src="https://lh3.googleusercontent.com/d/1uv09a-kJoSKjJ7hahmVkfeLJ3JY7h2Bm" >}}

However, if more than one condition is true, you will get the output spawned several times.

**Toggle Setup**

- Input type: Spawn truth
- Output type: Toggle/spawn truth
- Several inputs

To avoid getting several outputs, you can use Toggle triggers. This is the setup:
1. Place a Toggle trigger that toggles off the output at the start of your gate.
2. Place the condition triggers such that they activate after the Toggle trigger. (Check [spawn order](/docs/guides/triggers-2/spawn-order/) for more details)
3. Make each of those triggers spawn a Toggle trigger that toggles on the output.
4. Place the output such that it executes after everything.

Here is an example of the BG doing a pulse if Item ID 1 is 3 *or* Item ID 2 is 5.

{{< youtube EfzJGouz5gM >}}

**Item Edit Setup**

- Input type: Item truth
- Output type: Item truth
- 2 inputs

If you add your input Item IDs, the only way the result can be zero is if both Item IDs are zero. If the result is divided by 2 and then the ceiling is taken, you will get exactly an OR gate. This configuration will store the result of Item ID 1 *or* Item ID 2 in Item ID 3:

{{< img src="https://lh3.googleusercontent.com/d/1AvX6KT-KzBmwJDwg5zNty2zVhLBUrEYO" >}}

# 4: NOT Gate

## What is the NOT Logic Gate?

The **NOT logic gate** __inverts the truth value you give it__. Because of that, the NOT gate will activate something only if the given condition is false. Like the other gates, you can use a truth table to see all the gate’s possible outputs.

{{< img src="https://lh3.googleusercontent.com/d/1loSdDgiQ4USLACi0eKprrQ8NpQQoE2R5" >}}

You may notice that this one is special, since it has only 1 input. In fact, *this gate cannot be extended to several inputs*.

## What is it Used for?

Often when you make a system, you will have to do something in *the opposite case*, the case in which your condition is false. This is what the NOT gate is for. It is also often used as a component of more complex logic gates.

## Ways to make it in GD

**Trigger Integrated NOT**

- Input type: Any truth type
- Output type: Any truth type

The NOT gate is hard to make in Geometry Dash. Thankfully, most of the triggers have an integrated NOT gate! You just have to find it. Most of the time it is a checkbox (toggle off instead of toggle on in Toggle triggers, trigger on exit in the Collision trigger, etc.), but it can also be implemented by triggering *False ID* instead of *True ID* in certain triggers such as the Item Comp or Instant Collision triggers. For this reason, you will rarely need to make a NOT gate. But if you still do, I will cover how you can manually make one.

**Toggle Setup**

- Input type: Spawn truth
- Output type: Toggle/spawn truth

You can use toggles to make a NOT gate. The way you do this is by toggling off a trigger when the condition you are checking is true. Here is the setup:
1. Place your trigger with the condition of your choice.
2. Make it activate a Toggle trigger that toggles off group `A`. Note that you can also use the toggle off option of the trigger if it is available.
3. Place the output trigger of your choice and give it the group `A`. Make sure it executes after the condition trigger. (Check [spawn order](/docs/guides/triggers-2/spawn-order/) for more details)
4. If you want to use the gate several times, toggle on the output trigger right after the gate is activated.
Here is an example on how to make the setup that will pulse the background if Item ID 1 is not 5.

{{< youtube Z9TzhT2AKGk >}}

Note that in this example, it is much smarter to use the toggle off feature of the Instant Count trigger or to use an Item Comp trigger.
**Instant Count Setup**

- Input type: Item truth
- Output type: Spawn truth

You can make an Instant Count trigger activate when the Item ID is 0.

{{< img src="https://lh3.googleusercontent.com/d/1HueI9870aT6U0sSKODGE3uEl9GzJ_WPA" >}}

**Item Edit and Pickup Setup**

- Input type: Item truth
- Output type: Item truth

The Item Edit trigger is insufficient by itself to make a NOT gate; you need to add an extra Pickup trigger. The Item Edit will negate the input ID and will store the result in another Item ID. Then, the Pickup trigger will add 1 to the result. This operation will transform a 1 into a 0 and vice versa.

{{< img src="https://lh3.googleusercontent.com/d/16NPc1G44nc_1mVCPT-lkxaylfTsYRvP9" >}}

{{< img src="https://lh3.googleusercontent.com/d/1bvPVxKn4Gto_3wPKnVoS043O2zs6h5t4" >}}

# 5: XOR Gate

## What is the XOR Logic Gate?

XOR stands for eXclusive OR. The **XOR logic gate** __will output TRUE whenever `A` and `B` have different truth values__, so it behaves slightly differently to the default OR gate since XOR will yield FALSE if both `A` and `B` are TRUE. Here is the XOR truth table:

{{< img src="https://lh3.googleusercontent.com/d/17pvM3pc67CCwM1F4nWh8JsYWPyc_-nm7" >}}

Logic wise you can define the XOR logic gate in two equivalent ways :
- `A` XOR `B` = (`A` AND NOT `B`) OR (`B` AND NOT `A`)
- `A` XOR `B` = (`A` OR `B`) AND NOT(`A` AND `B`)
You can also see the XOR logic gate as a 2 input (or more) *T-flip flop*: anytime `A` or `B` changes, the output changes as well.

## What is it used for?

The XOR gate is the least used gate. It is mostly used in computers to make a binary adder (we will see how this works in the examples section). You can also use the XOR gate like a toggleable NOT gate: if `A` is FALSE then let `B` through, but if `A` is TRUE then invert `B`. Also, when using many inputs, the XOR gate can tell if a sum of zeros or ones is even or odd.

## Ways to make it in GD

**Sequence T-flip flop Setup**

- Input type: Spawn truth
- Output type: Toggle/spawn truth
- Several inputs

[You can use a T-flip flop with a Sequence trigger](/docs/guides/triggers-1/sequence/) and make your conditions activate the T-flip flop. In this example the block will be toggled on if Item ID 1 is 3 XOR Item ID 2 is 5:

{{< youtube HWhSGZUDrU0 >}}

I would like to give a very specific example to illustrate what I meant at the XOR logic gate's uses when I said that the output changes anytime `A` or `B` changes. In this example, I would like the block to appear only when the player is in the first hitbox or the second one but not both. You may recognize the XOR statement. The way you can do that is by activating the T-flip flop every time the player enters or exits any of the hitboxes.

{{< youtube Ap24SePuf7Y >}}

However this method has a big flaw: the Sequence trigger can't activate more than once in a single frame, which means you can't feed your conditions at the same time.

**Item T-flip flop Setup**

- Input type: Spawn truth
- Output type: Item truth
- Several inputs

This T-flip flop solves that issue but it requires using an Item ID. Here is how to make it :
1. Place a Pickup trigger at the start of your level and set your Item ID to -1.
2. Place a Pickup trigger that multiplies your Item ID by -1. Activate the spawn trigger and multi trigger options.
3. Make each of your conditions spawn that Pickup trigger.
4. As your output, use an Instant Count trigger that checks if the Item ID is 1.
5. To reset the gate (and use it several times) override the Item ID to -1.
Here is an example of a system that pulses the background if Item ID 1 is 3 *xor* Item ID 2 is 5:

{{< youtube PHk6XNgik9E >}}

You can easily turn a XOR gate into a *XNOR* (also known as an equals gate) by offsetting the T-flip flop by 1 activation.

**Combination of Other Gates**

- Input type: Spawn truth
- Output type: Spawn truth
- 2 inputs

You can also make a XOR by combining an AND, an OR and a NOT gate. Remember that `A` XOR `B` = (`A` OR `B`) AND NOT(`A` AND `B`).

This is the setup:
1. Place your 2 condition triggers and make them both activate group `P`. This will make the OR gate.
2. Place one of your condition triggers again such that it activates before the 2 others. Make it activate group `Q`.
3. Place your second condition trigger again and give it group `Q`. This will be our AND gate.
4. Make that trigger toggle off group `R`. This will be the NOT gate. Most triggers can toggle off a group by themselves but if it can't, make it activate a toggle trigger.
5. Place your output trigger such that it activates after everything and give it the groups `P` and `R`.
Don't forget to toggle back on group `R` if you want to use the gate several times. This is what you system may look like:

{{< img src="https://lh3.googleusercontent.com/d/1pawhpur_RjUWCESQayVr1KE9tuP_nUhm" >}}

**Item Comp Setup**

- Input type: Item truth
- Output type: Spawn truth
- 2 inputs

This Item Comp configuration will spawn group 1 if Item ID 1 *xor* Item ID 2 is 1. It works by the definition of the XOR gate.

{{< img src="https://lh3.googleusercontent.com/d/1IE1xR58JGE04UYuP5G3lmFSQ6A-wZYjO" >}}

**Item Edit Setup**

- Input type: Item truth
- Output type: Item truth
- 2 inputs

This Item Edit setup will store the result of Item ID 1 *xor* Item ID 2 in Item ID 3. If the input IDs are different, the result will be 1, and it will be 0 otherwise.

{{< img src="https://lh3.googleusercontent.com/d/1Kzrhj2ngcErKq9BPNxCFT8ChHOceldhF" >}}

# 6: Truth Type Conversion

## Why Would You Convert Different Truth Types?

There are several reasons for this: a specific truth type can be more convenient or optimized to the specific thing you are doing, and some truth types allow you to store the truth state while others don't. The different logic gates setups you have seen in this guide require you to use certain types of truth, but you can use truth type conversion to modify those setups to use the truth types you desire. We will see six ways to convert from one truth type to another one.

## How to Convert Different Truth Types

**Spawn Truth to Toggle Truth Type Conversion**<br>
Let's say you want to toggle on group `A` when group `B` is spawned. You can place a Toggle trigger, give it group `B` and then set it to toggle on group `A`. If you want to use the gate several times, I recommend toggling off group `A` using another Toggle trigger that spawns with a NOT gate. This way, group `A` will toggle off when the condition is false and toggle on when it's true.

**Toggle truth to spawn truth type conversion**<br>
Let's say you want to spawn group `A` only if group `B` is active. To do this, you can give group ID `B` to the trigger that spawns group `A`. This trigger will not be able to activate if group `B` is toggled off, but it will be able to do so if group `B` is toggled on.

**Spawn Truth to Item Truth Type Conversion**<br>
Let's say you want to set Item ID `A` to be 1 when group `B` spawns. You can use a Pickup trigger that will override Item ID `A` to one when it is spawned by group `B`. You also can, just like with the spawn to toggle truth type conversion gate, connect another Pickup trigger to a NOT gate that will set Item ID `A` to 0.

**Item Truth to Spawn Truth Type Conversion**<br>
Let’s say you want to spawn group `A` if the value stored in Item ID `B` is 1. You can use an Instant Count or Item Comp trigger to spawn group `A` only if Item ID `B` is 1. You can also use a Count trigger that will spawn something right when Item ID `B` reaches the number you want.

For the conversions I didn't cover, you can convert any truth type to spawn and then convert from spawn to whatever truth type you want.

# 7: Boolean Algebra and its Properties

**Boolean Algebra** is a type of algebra in which *operations are done using only 2 numbers, the number 0 and the number 1*. The operations you can do with those numbers are precisely the logic gates you saw in this guide. Understanding boolean algebra properties can help you out at using logic gates conveniently in order to make more complex truth conditions.

## Commutativity

All of the gates (OR, AND and XOR) are **commutative**. Which means that __the order in which you choose `A` and `B` has no importance__. Taking the example of the AND gate it means that :
- `A` AND `B` = `B` AND `A`

## Associativity
All of the gates are also **associative**. That means, __when two or more logic gates are combined, the order in which the operations are performed doesn't matter__.

Taking the example of the AND gate:
- `A` AND (`B` AND `C`) = (`A` AND `B`) AND `C` = `A` AND `B` AND `C`
Note that this way, the order in which you define a 3-input or more AND gate doesn’t matter.

## Distributivity
The AND and OR logic gates are **distributive**. It means that:
- `A` AND (`B` OR `C`) = (`A` AND `B`) OR (`A` AND `C`)
- `A` OR (`B` AND `C`) = (`A` OR `B`) AND (`A` OR `C`)

## Involution

NOT is **involutory**. This means that __doing a NOT operation two times in a row will give the same output as if no operation was done in the first place__.
- NOT(NOT(`A`)) = `A`

## De Morgan's Law

**De Morgan's law** is a way to distribute NOT with OR and AND gates. It is a set of 2 laws that are very useful when doing complex gates :
- NOT(`A` OR `B`) = NOT(`A`) AND NOT(`B`)
- NOT(`A` AND `B`) = NOT(`A`) OR NOT(`B`)
You can also note that the XOR gate satisfies the following properties:
- NOT(`A`) XOR NOT(`B`) = `A` XOR `B`
- NOT(`A`) XOR `B` = `A` XOR NOT(`B`) = NOT (`A` XOR `B`)

# 8: Conditional and Biconditional Gates

The *Conditional* and *Biconditional* logic gates are two gates that are used in mathematics to express relation between two truth values.
## Biconditional Logic Gate
The **Biconditional gate**, also known as the equivalence gate or XNOR gate, __is a relation between two statements that will output TRUE if the two statements have the same truth value__. If statements `P` and `Q` are given to the biconditional gate and it yields TRUE, `P` and `Q` are said to be equivalent. You often write this relation as follows: `P`⇔`Q`.

As an example, *x is divisible by 2* ⇔ *x is even*. But you can also say that *5² = 25* ⇔ *3×4=12*, or *3=4* ⇔ *the earth doesn't exist*, because in the first case both are true statements and in the second case both are false statements. Here is the biconditional gate truth table:

{{< img src="https://lh3.googleusercontent.com/d/1swUGS4HioJU-KDfe30JQsKWxEoMvwTPA" >}}

## Conditional Logic Gate
The **Conditional gate**, also known as the *implication*, is another relation between two statements, let’s say `P` and `Q`. Logic wise, it is defined this way: `P` IMPLIES `Q` = NOT(`P`) OR `Q`. It means that __if `P` is true, then `Q` is also true, but not always the other way around__. As an example, most triggers execute an action `Q` if the condition `P` is true. But if the action `Q` has been executed, it doesn't mean that condition `P` is true. It is possible that another trigger with a condition different than `P` has done action `Q`. You often write the conditional relation `P` IMPLIES `Q` as `P` => `Q`. As usual, the truth table of the implication gate is as follows:

{{< img src="https://lh3.googleusercontent.com/d/1yCOm5jlhORaYhHYU2usqTEIp3grxdwoY" >}}

Let's take a more concrete example in game. You have two Spawn triggers, `A` and `B`, that both spawn group 1. If `A` is activated then group 1 is spawned. But if group 1 is spawned it doesn't mean that the trigger `A` has activated. It is possible that `B` did it instead. So you have `A` => *group 1 is spawned*.

{{< img src="https://lh3.googleusercontent.com/d/1Uvf2PvXlUqkvdOd8IBR5ZME91wgKFKSB" >}}

If you make sure that there is only one trigger that can activate group 1, then you would have: `A` ⇔ *group 1 is spawned*.

{{< img src="https://lh3.googleusercontent.com/d/10nbs_B1Hd0BtjekwtkhrDKDMvHxchUGC" >}}

# 9: Examples

To end this guide, I will present to you some examples of combined gates in-game to illustrate the lesson.

## Example 1: NOR Gate

Imagine you want to activate something when none of your conditions are valid. The OR is almost what you need since it gives FALSE only if all the conditions are false. If you put a NOT gate after the OR gate, you get a **NOR gate** (NOT OR), __which gives TRUE only when all the conditions are false__. However as you might have seen, the NOT gate is very impractical when it is not trigger integrated. Remembering De Morgan's law, we know that NOT (`A` OR `B`) = NOT(`A`) AND NOT(`B`). So if we use an AND gate, we can use the integrated NOT of our input triggers `A` and `B`. Let's say we want to make something appear only if one number is 3 *nor* another number is 4. We can make it like this:
1. Place an Instant Count trigger that checks if the first number is 2. Keep the activate option off (that will be our first NOT gate).
2. Repeat with another Instant Count trigger that will check if the second number is 4.
3. Make both triggers toggle off the same group, that group will be our output.

{{< youtube WJwGAR2vYC4 >}}

## Example 2: Enemy Attack

Now let's try something more complex, in which we have several input types. Imagine you want to make an enemy attack the player only under some very specific conditions. Say, the enemy attacks the player only if the player is in a certain area, its HP is above 10 *and* if it has no shield, *OR* if “bossfight mode” is activated. Logicwise, the underlying attack conditions would be defined like this: IF \[(*player in area* AND *player HP > 10* AND NOT *shield*) OR *bossfight mode*\], THEN *enemy attack*.

Let's use GD stuff to represent our conditions: we can use a Collision State block to represent our area, an Item ID to store the player's HP, a Toggle trigger to know if the player has a shield (toggles on = has a shield, toggles off = has no shield) and finally let's say “bossfight mode” is activated with a spawn truth type. We also want our output to be a spawn truth type so we can spawn the system that attacks the player.
1. Let’s begin by making the AND gate. I started with the Collision State block since I can spawn the rest of the gate when the player enters the area.
2. For the shield I needed to make a NOT gate. I used a Toggle trigger that toggles off group ID 4, which in turn is toggled on/off by the shield (group ID 1). Then I gave group ID 4 to the next element in the AND gate.
3. The last element this AND gate needs is an Instant Count trigger. It checks that the player's HP is more than 10, and spawns the enemy attack if that is the case.
4. Moving on to the OR gate, I just made the bossfight mode spawn the output. I also removed multi trigger to the output so it isn't spawned multiple times.

{{< youtube 5vWtrUESK9Q >}}

If I needed the gate to work several times, I would need to toggle off the output after it is spawned to make sure it isn't spawned multiple times. Then, I would need to make a reset system that would toggle on the output and stop the enemy attack. A good idea would be to connect this reset system to a NOT gate. This way, when our set of conditions is false, the enemy stops attacking. That is a challenge you can try to build! (You may use DeM's law and change the truth type of certain inputs, since the spawn inputs don't store anything).

## Example 3: Binary Adder

A **half adder** __is a circuit used in computers to make [binary additions](<https://www.build-electronic-circuits.com/full-adder/>)__. It receives 2 inputs `A` and `B` in binary, then gives two outputs: The first one will be the sum between `A` and `B`, which is done using a XOR gate, and the second one will be the “carry” of the addition, which is done using an AND gate. We can use a logic gate diagram to help ourselves visualize this system:

{{< img src="https://lh3.googleusercontent.com/d/1LZSZGv2Il5Dd-eDPWSCstwqIdcDanemE" >}}

Here is how I did it in Geometry Dash using Item Edit gates:
1. Place an Item Edit trigger and perform a multiplication between Items ID 1 and 2, and save the output on another Item ID. This will be our carry.
2. Place another Item Edit trigger and perform a binary XOR between Items ID 1 and 2, and save the output on another Item ID. This will be our XOR gate.

{{< img src="https://lh3.googleusercontent.com/d/1kyaPenCiCxyQVVKsjItohcr1Yyo1wYS3" >}}

When combining two half adders and a OR logic gate, we get a **full adder** __that can add up to 3 numbers__. Here’s how the full adder diagram looks:

{{< img src="https://lh3.googleusercontent.com/d/10Kb7Smz4iO__d7FoZ-gyUHj_MLzKoQkH" >}}

Using the half adder setup I already made, this is how I did the full adder setup:

{{< youtube lGGzIc9DTJk >}}

You may notice I actually didn't use any trigger to make the OR gate. That is because there is a very interesting way to include this gate inside of the last AND gate. Something very special with that OR gate is that it is impossible to get both inputs true. In binary, the only time the addition doesn't work is 1+1, because it overflows. So, I can basically add up the outputs I want to make an OR. To make this addition, I used a feature inside of the last AND Item Edit: instead of overriding Item ID 5, I added the result of the AND to Item ID 5. It’s this extra addition that acts as the OR gate.

{{< img src="https://lh3.googleusercontent.com/d/1psrjAWnwF5sFZyj-CfCB0Kl5F7RAMein" >}}

# Sources

- [Practical Ninjas: Half adder](<https://www.youtube.com/watch?v=thkTzdnkL5U>)
- [Build Electronic Circuits: Full Adder](<https://www.build-electronic-circuits.com/full-adder/>)
