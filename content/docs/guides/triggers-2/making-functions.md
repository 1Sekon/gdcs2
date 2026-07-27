---
draft: false
title: Making Functions
weight: 6170
date: 2026-05-25T00:00:00.000Z
description: Once you start building increasingly complex systems, your setups may become unmanageable or even you may begin to loose understanding of the whole web of triggers being created. This is where functions come in. They isolate individual bits of logic into atomized setups with clear purposes, making setups easier to utilize, understand, reuse and expand. This guide will cover all the considerations you must know in order to properly create functions without shooting yourself in the foot.
authors:
  - chuckolate
contributors:
  - chuckolate
  - alexunam_777
tags:
  - Grade 2
  - Trigger Setups
math: true
seo:
  title: How to Program in Geometry Dash
  description: This explains how to understand Geometry Dash triggers as a programming language.
  canonical: ""
  noindex: false
---

{{< callout context="note" title="TLDR - What this guide covers" icon="outline/info-circle" >}}

-

{{< /callout >}}


{{< callout context="caution" title="Important" icon="outline/info-circle" >}}

Before reading this guide, you *must* already have some experience with the remapping system and with using logic in trigger setups. In particular, these guides could come in handy:
- [Making Loops](/docs/guides/triggers-2/making-loops)
- [Making Logic Gates](/docs/guides/triggers-2/making-logic-gates)
- [Using Remap Properties](/docs/guides/triggers-2/using-remap-properties)

Additionally, having a basic understanding in any programming language will be useful as well.

{{< /callout >}}

** **

# 1. What are Functions?

At its core, a function is a mathematical concept that describes a special kind of relationship between inputs and outputs. Imagine a machine: you put something in (*an input*), and it consistently gives you a specific result out (an *output*). In a computational context, a function still adheres to the mathematical principle of mapping inputs to a single, deterministic output. However, *how* this mapping occurs shifts from abstract mathematical notation to a concrete sequence of operations performed by a computing system. **The core idea is that a computational function is a procedure that, given specific inputs, reliably produces a specific output after a series of defined steps.** This procedure must be finite and *unambiguous*, much like a mathematical function.

{{< img src="https://lh3.googleusercontent.com/d/1nkj42iLTL1HLMoBLDgk-yWixHwmov_rB">}}

A function has three main attributes:
- **Input Data**: These are the parameters you give to the function. Computationally, inputs are concrete pieces of data like numbers, objects, or other functions, among other data types.
- **Processing Logic**: This is the algorithm or set of instructions that takes the input data and transforms it into the output.
- **Output Data**: The final result produced by the function. It may produce a new piece of data, change attributes of other data, or do both.

Function syntax varies depending on what programming language you are using, but more often than not, most functions follow a similar pattern:

```c
function function_name(input) {
    instructions
    return output
}
```

We first declare this set of instructions will be a function with the keyword `function`, then provide its name in `function_name`, followed by the input parameters `input` inside parenthesis. Inside the brackets, we declare the steps the function must follow in `instructions`. The keyword `return` declares what the function will output.

For instance, let's say we want to compute the average between two numbers. We can do it by defining a function that takes two numbers $A$ and $B$ as input, and outputs the average. That can be written like this:
```c
function average(A, B) {
    sum = A + B         // the function stores A + B in a new variable sum
    average = sum / 2   // then calculates the average using sum
    return average      // finally, the function outputs the result
}
```
We can use this function to compute the average between any pair of numbers we input; it should verify that $\rm{average}(2,8) = 5$, $\rm{average}(2,1) = 1.5$, and $\rm{average}(-3,3) = 0$, for example.

The main advantage of using functions is that they let you group a set of instructions and freely reuse them. This makes coding much easier:
- It lets you avoid repetition as you don't have to write the same instructions every time.
- It simplifies managing your code, because if something breaks you can test the function in isolation.
- It can improve readability, as you can give functions meaningful names and purposes to make your code more understandable, not just to yourself but to others as well.

From the previous example, every time we want to compute the average between two numbers, we can just use the $\rm{average}$ function instead of summing and dividing every time. Also, if we later in the code perform $z = \rm{average}(x,y)$, it can easily be understood that $z$ stores the average between $x$ and $y$.

# 2. Functions in GD

Now that we understand what functions are and their advantages, how can we make functions with Geometry Dash’s trigger system? The clear answer is by using **Spawn triggers**. In GD, Spawn triggers behave like functions, where everything the Spawn trigger activates correspond to the instructions of the function. In 2.2, it's now possible to give inputs to these functions via spawn remapping, so we can now create general-purpose setups with remappable IDs in mind, and then use them with any set of inputs.

Throughout this guide, we'll use a pseudocode language to describe trigger logic. The goal is to express the behavior of a function clearly and objectively before translating it into triggers, allowing us to write down the logic of our functions independently of specific setup implementations. In particular, we can structure functions in this way:

```c
GID function_name(inputIDs) {
  instructions      // here are all the trigger setups spawned
  modify outputIDs  // we setup how to modify the output IDs
}
```

Instead of identifying functions by their name, *we identify them using the group ID (GID) that the Spawn trigger activates* when it runs the function. Also, using remapping we can tell the spawn trigger what input IDs *and* output IDs to use, so the instructions make modifications to the output IDs depending on what the input IDs do.

Let’s take for example this setup. Here, the Item Edit trigger is taking the original value of Item ID 1 as its input, and performs "$\rm{I1 = I1 \cdot 2}$", outputting the result back in $\rm I1$.

{{< img src="https://lh3.googleusercontent.com/d/1BcepCAH8EI_639fj6Ya6tueB442fB0ZZ">}}

This means that, GID 10 is a function that remaps ID 1 to both the input and output ID declared via remapping. This setup allows us to reuse the same logic to double *any* item ID, without needing to create a separate copy of the trigger setup each time.

(Example: 3. BasicRemapFunction)

We may write this as code as well. We will give it a descriptive name, and denote what group ID spawns the function.

```c
GID_10 double_item_id(ID_1) {
  ID_1 = ID_1 * 2
}
```

That way, instead of saying "Set Item ID to 1, and double it two times", we can just write

```c
ID_1 = 1
double_item_id(ID_1)
double_item_id(ID_1)
```

which is equivalent to placing an item edit trigger that sets Item ID 1 to 1, and then placing two spawn triggers spawning GID 10 in order to double the item ID.

We can go even further with the notation. Instead of using just the ID numbers as arguments, we can also give them names in order to make the function more readable. So taking $\verb|double\_item\_id|$ as an example, we could rewrite it as follows:

```c
GID_10 double_health(ID_1 health) {
  health = health * 2
}
```

In this case, we give extra meaning to our functions: instead of just being a function that doubles an arbitrary ID, it's a function that doubles an hypothetical health attribute, represented by item ID 1.

Throughout this guide, IDs will be represented symbolically as `ID_A`, `ID_B`, `ID_C`, and so on. These are placeholders for the numeric IDs that will eventually be assigned inside the editor. Using symbolic names keeps the examples independent of any particular implementation and makes it easier to focus on the logic of the function. That way, we can write

```c
ID_A object
ID_B enemy
```

which declares `object` and `enemy` are associated with two different in-game IDs. They might correspond to IDs 1 and 2 in one setup, or 1203 and 7204 in another: *the actual numeric values are assigned when the function is instantiated through remapping*.

# 3. ID Types

Functions don't necessarily have to rely only on item IDs. In fact, when a Spawn trigger remaps an ID, it doesn’t just affect one ID type; <span style="color: red;">**_all_**</span> the ID types will be remapped as well. That is, if you remap ID $A$ into ID $B$, then group ID $A$ remaps to group ID $B$, item ID $A$ remaps to item ID $B$, block ID $A$ remaps to block ID $B$, and so on. For this reason, when designing your functions, **you must be mindful not just of which IDs you are using, but also which ID *types* you are using from each ID remapped.**

For instance, let's say we want to make a function that moves an object to the player, only if the object is "active". If $A$ is our object, then we can represent "being active" with an item ID that takes the value of 1 if $A$ is active, or 0 if it's not. We could use two different IDs, one for $A$ and another for the item ID, but we could also use only ID $A$, where we move the object using group ID $A$ and store its active state in item ID $A$. We can write that function like this:
```c
// object.item denotes the item ID of object
// object.group denotes the group ID of object

GID_B move_if_active(ID_A object) {
    if (object.item == 1) {
        move object.group to the player
    }
}
```

Note that the function above doesn't give precise instructions on how to translate that into Geometry Dash *yet*, but it does specify **the logic behind our idea**, which is representable in any programming language. In-game, we can translate it as follows:

(Example: 4. Types Example)

Using IDs in a compact way like this, instead of using a lot of IDs for different purposes is useful for optimization and commodity purposes:

1. **We are taking advantage of all the ID types associated with a single numeric ID**, which allows us to store lots of functionality in our functions with few arguments. As IDs in Geometry Dash are limited (specially group IDs which are the most important ones), we have room to make lots of new functions.

2. **Few IDs make functions easier to manage**, as you have less possible points of error to fix in case something goes wrong. Furthermore, it makes remapping less of a hassle for the same reason.

From now on, function setups in this guide (and upcoming ones) will stick to this approach of ID usage, in order to make them as efficient as possible. Also, our code will adopt the following notation, which will help us clearly indicate what kind of ID is being used, while keeping the code easy to read. For any other ID type, the notation will be specified later if needed, but you can probably guess how it would be denoted.

| ID Type | Notation | Meaning |
| :--- | :--- | :--- |
| Group | variable.group | Group ID of the variable |
| Item | variable.item | Item ID of the variable |
| Time | variable.time | Time ID of the variable |
| Block | variable.block | Block ID of the variable |
| Control | variable.control | Control ID of the variable |

Since repeatedly writing expressions such as `object.item` or `enemy.time` can become cumbersome, throughout this guide we'll use the operator `:=` to create *aliases*. An alias simply gives a more descriptive name to an existing ID and each on of their types; **it does not create a new variable or copy its value**. Furthermore, each type of the ID can have different aliases to represent different ideas. For instance, we can write the previous function equivalently as

```c
GID_B move_if_active(ID_A object) {
    active := object.item
    target := object.group

    if (active == 1) {
        move target to the player
    }
}
```

Or if we want to spawn an enemy, we could write

```c
GID_B spawn_enemy(ID_A enemy) {
    sprite := enemy.group
    health := enemy.time

    toggle sprite on  // Toggles the group of the enemy to make it appear on screen
    health = 20.0  // Sets the health of the enemy
}
```

which treats the group ID of the enemy as its sprite, and the time ID of the enemy as a health attribute, and sets it to 20. Under the hood this are just aliases for a Toggle trigger that activates group ID `A` and an Item Edit trigger that performs `Time ID A = 20` where both triggers spawn under ID `B`, but we are giving a special meaning to those operations.

# 4. Variable Scope

When writing programs, one of the most important concepts is **scope**. Scope determines **where a variable exists, and which parts of the program are allowed to access or modify it**. Most programming languages distinguish between two kinds of variables:

- **Local variables**, which only exist while a specific function is running.
- **Global variables**, which exist independently of any function and can be accessed from anywhere in the program.

For example, consider the $\verb|average|$ function we defined before:

```js
function average(A, B) {
    sum = A + B
    return sum / 2
}
```

Here, sum is a local variable. It is created when the function begins executing, used to perform the calculation, and destroyed once the function returns. If another part of the program also creates a variable called sum, the two variables are completely unrelated. This makes functions easier to reuse as each call to $\verb|average|$ gets its own independent copy of sum, so multiple calls can run without interfering with each other.

Geometry Dash however, works **very** differently. In GD, every single ID and their respective types already exists globally throughout the level, and will always be the same. A Spawn trigger doesn't create a new set of IDs for its exclusive use when it spawns, it simply remaps existing IDs to different ones. As a result, **functions in GD don't have local variables**: every ID a function uses refers to an ID that also exists outside that function's scope. Therefore, two functions that use a shared pool of IDs may produce unexpected results if used in conjunction, and *will* do so if you're not careful.

{{< callout context="note" title="Because of this, writing functions in GD requires deciding which IDs should be shared between every function call and which ones should be remapped independently." icon="outline/info-circle" >}}
{{< /callout >}}

## Global & Local Variable Issues

Let's see an example. We want to move an object $O$ horizontally to the right as many times as a number $n$ dictates. We can approach this problem by making a function that moves $O$ horizontally by $n$ steps of 10 units each, using a while loop. To count the steps, we will use a non-remappable temporal ID $C$, labeled `temp`.

We can write that function as this:

```c
// The temp variable is not part of the arguments of interest, and therefore not remappable. We will declare it externally under ID C
ID_C temp
counter := temp.item  // We will treat the item ID as the counter. It is 0 by default


GID_D horizontal_move(ID_A object, ID_B steps) {
    n := steps.item
    target := object.group

    while (counter < n) {
        move target 10 units to the right
        counter = counter + 1
    }
}
```

This will work the first time the function is called, as `temp` will be exactly equal to $n$ once the loop finishes. However, *it won't necessarily work the next time*, due to `temp` being different than 0 now, and therefore the next call of this function will produce a different amount of steps as intended.

(Example: 5. Scope Failing)

We can fix this by resetting the value of `temp` *inside* the function, which we can interpret as "creating" the `temp` variable when activating $\verb|horizontal_move|$, even though ID $C$ is still a global ID that every trigger can access.

```c
GID_D horizontal_move(ID_A object, ID_B steps) {
    n := steps.item
    target := object.group

    ID_C temp  // We set temp to 0 inside the function, virtually declaring a local variable
    counter := temp.item
    counter = 0

    while (counter < n) {
        move target 10 units to the right
        counter = counter + 1
    }
}
```

Now, every time we run this function, ID $C$ will start counting from scratch, which will produce a valid number of steps.

(Example: 6. Fix IDs)

However, **this function *still* has a problem**. What would happen if we activate multiple instances of the function while other ones are still running? As each instance of $\verb|horizontal_move|$ is using the same ID_C as its `temp` variable, which is *not* local, then if we activate an instance while another one is running, it will reset `temp` to 0 while another one is still moving an object, completely changing the final result like we saw in the example above.

## How to Handle Local Variables

Given this, whenever you create a function, it is good practice to classify every ID it uses into one of two categories:

- Function arguments (IDs that should be remapped independently for each instance).
- Shared state (IDs that are intentionally global across every instance).

Thinking about this distinction *before* building the setup greatly reduces accidental conflicts. Once you do that, think about how your shared state variables and their associated functions will be used.

Here's a few tips on how to handle them. In practice, it's better to use a combination of all these tips, preferring the less cumbersome option if available.

**Use fixed IDs**<br>

If it is guaranteed that only one instance of your function can ever execute at a time, then using fixed IDs for local uses like `temp` in $\verb|horizontal_move|$ is perfectly fine.

For example, perhaps the function is only used by a single setup, or a new call is only made after the previous one has finished. Since the temporary counter is never accessed by two function instances simultaneously, there is no possibility of interference.

In these situations, using a fixed Item ID is the simplest solution, and adding another remappable ID would only make the function harder to use.

**Reuse existing arguments to store temporal information**<br>

If the above option is not feasible, you can reuse existing input IDs in order to temporarily store information. This gives you less freedom of ID choice as you depend on the number of arguments the function has, and also restricts the uses of the ID as some ID types are needed merely for the function to work. Although, this can become less of an issue if your function has a lot of ID arguments where to hold local information.

Looking at our previous example, if we aren't using the item ID of $O$, we can give it a temporal use to store the `temp` counter as follows:

```c
GID_C horizontal_move(ID_A object, ID_B steps) {
    n := steps.item
    target := object.group

    // We reset the item ID of ID A, treating it as the counter
    counter := object.item
    counter = 0

    while (counter < n) {  // we now use object.item to store the counter
        move target 10 units to the right
        counter = counter + 1
    }
}
```

This way, even if we have multiple instances of $\verb|horizontal_move|$ running at the same time, there won't be any conflict as long as you use different objects.

(Example: 7. Reusing IDs)

**Add remappable local variables**<br>

Sometimes, however, your argument IDs may already be storing important information that can't be overwritten. Cases like where for a single ID the group, item, time and/or block IDs are fundamental for the function to work properly. In that case, reusing IDs is no longer possible. The only remaining option is to use new arguments that can carry over all the temporal operations, without being overwritten with other instances of your functions.

In the $\verb|horizontal_move|$ example, that would translate like this:

```c
GID_D horizontal_move(ID_A object, ID_B steps, ID_C temp) {
    n := steps.item
    target := object.group

    counter := temp.item
    counter = 0  // Counter is now a variable of the function, which can be remapped freely

    while (counter < n) {
        move target 10 units to the right
        counter = counter + 1
    }
}
```

Each Spawn trigger can now remap `temp` independently, so every instance has its own temporary storage while leaving `object.item` untouched. The downside of this method is that the function can become harder to use as you have to look after more arguments, and you have less IDs for other functions.

(Example: 8. Using New Arguments)

# 5. Synchronization

On the example above we were stumbling into problems when multiple instances activated while others where still running. We'll talk more about that now.

## Synchronous & Asynchronous Functions

In most programming languages, the instructions you give to functions are run in a specific order, one step at a time. Take a look at the following piece of code for example. It takes a number $a$, an integer $n$, and outputs $a^n$. Notice that to do that, it follows the instructions from top to bottom, where it first defines the output, then it enters a for loop where it multiplies the output by $a$ as many times as $n$ dictates. After doing *all* the multiplications step by step, it finally outputs the result.

```js
// Javascript code example

function power(a, n) {
    output = 1
    counter = n
    while (counter > 0) {
	    output = output * a
	    counter = counter - 1
    }
    return output
}
```

These are called **synchronous functions**. When a synchronous function is called, *the program pauses and waits for it to finish before continuing to the next instruction*. This means that these functions follow a strict set of sequences, one at a time. While one operation is being performed, other task instructions are halted until the operation is finished.

In GD triggers don't *exactly* work this way. If a trigger spawns, **it will *not* halt the execution of other triggers**. If two Spawn triggers spawn on the same frame, such that the first one activates a loop, and the other one does an instantaneous action, the second Spawn trigger won't wait until the loop finishes, and it will execute its action no matter if the loop stops or not. This means that functions in GD are **asynchronous**, as multiple operations can run concurrently without waiting for other tasks to complete. This function behaviour is benefitial in most cases, as:

- Different setups can function independently from each other, allowing for a lot of processes being run at the same time.
- Multiple instances of a single setup can run in parallel via remapping, making repetitive tasks more managable.

This is great for GD, as levels can have lots of movements, color changes and other processes handled every frame without much issues. However, if we need operations that must execute in a strict sequence, or perform tasks that are dependent on other ones, we have to be *extra* careful of processes being handled in the correct order, specially for the ones that require more than a single frame to be completed.

## Sequential Execution

Recall from the [Spawn Order guide](/docs/guides/triggers-2/spawn-order/) that Spawn triggers will activate triggers from left to right on the X-axis, where every trigger that shares the same X-position will be triggered according to priority order. Because of this, **trigger setups are better read from left to right instead of top to bottom**, thus if we have to make setups that follow instructions sequentially, we *must* order triggers this way in order to avoid problems. Also, because of order inheritance, if a Spawn trigger activates multiple Spawn triggers, then whatever these triggers spawn will do so in the order in which the parent Spawn triggers activate. Below is an example showcasing how order works, notice that it isn't purely from left to right but it obeys the order of the Spawn triggers; once a Spawn trigger finishes, it jumps back to the parent to keep executing new triggers.

{{< img src="https://lh3.googleusercontent.com/d/1HwV6Nimy1RJQtiz6xGmvmrFFYuTIsH6q">}}

In order for functions to sequentially, **make every task work in a single frame if possible**, so that spawn and priority order automatically manage the order in which trigger spawns. If an operation is performed in a frame, then within the same frame you can keep spawning other triggers after the operation is done; all of them will work as if the operation is finished, preserving the sequential order.

**Example: Modulo Function**<br>

The *modulo* is a function that returns the remainder of the division of two numbers $A$ and $B$. It's notated as $A \% B$ and it's a very useful function for modular arithmetic. Although it isn't an option in the Edit Item trigger, we can make a setup for it, following these instructions:

```c
GID_D modulo(ID_A, ID_B, ID_C) {
    divided := ID_A.item
    divisor := ID_B.item
    output := ID_C.item

    output = floor(dividend / divisor)
    output = divisor * output
    output = dividend - output
}
```

The function has three instructions that must be performed from top to bottom, otherwise it will simply not work. The first two steps calculate the largest multiple of item ID $B$ such that item ID $B$ is less than item ID $A$, and the final step substract that number from item ID $A$ to get the reminder. We are only using arithmetic here, so making this function is easy; for each step use an Item Edit trigger, and place them from left to right.

(Example: 10. Modulo Function)

In general, functions that involve computing numbers will follow the same logic. Place the triggers in order from left to right to make sure the calculations are done correctly. As long as you don't use loops, this type of functions most of the cases can compute an output within a single tick, so you can reuse them inmediately (like in this example).

## Concurrent Execution

Notice that so far in our examples so far are mostly sequential, but most triggers don't behave that way. Particularly, triggers that have a *duration* like transformative triggers and triggers that *wait an event to happen* like Collision & Count triggers won't stop executing if other triggers on your function are activated. If we spawn other triggers after the said triggers have already been activated, then **all of those triggers become active concurrently**, meaning their actions will be active at the same time.

From now on we will need a way to denote specific triggers. We will do it as follows:
```c
move(GID target, float move_time, int move_x, int move_y, ...)
rotate(GID target, GID center, float move_time, float degrees, ...)
advanced_follow(GID target, GID follow, float easing, ...)
// every other trigger follows an analog structure...
```
These are ***built-in*** functions (provided by the game, not made by us) that take as arguments specific IDs, like `target`, `center` or `follow` IDs, which correspond to those specific IDs in their associated triggers. Additionally, they take up other arguments **that are not remappable**, and are instead fixed values that once placed *cannot* be changed, like `move_time`, `easing`, `move_x`, etc. These functions will model directly a trigger *placement*. However, when and for how long these are active will depend on the functions that spawn the triggers.

Now that we defined that, let's look at the following code:

```c
ID_A variable1
ID_B variable2

move(target=variable1.group, move_time=0.5, move_x=10, move_y=10)
move(target=variable2.group, move_time=1.5, move_x=-10, move_y=-10)
```

{{< gif src="https://lh3.googleusercontent.com/d/1LrPuqnYEFNTz8SIezkxN-Un-vrB8dv9W">}}

Here, the Move trigger that targets $\verb|variable1|$ will *activate first*, given our previous top-to-bottom order of execution. However, the Move trigger that targets $\verb|variable2|$ will *inmediately* follow, giving the final result that the two move triggers will be active at the same time during the first 0.5 second window of activation. After that, the first move trigger will have finished its execution, but the other one will be active for another full second. In that process, IDs $A$ and $B$ could be doing other stuff, like using block IDs to detect collisions, which requires other collision triggers to work concurrently with the move triggers to actually register the collision.

Speaking of that, we will represent triggers that *wait for an event to happen* with the `on` keyword. This is an **event handler**, meaning that the code inside an `on` block is not executed when the function is spawned. Instead, it is registered as a call that will execute **every time the specified condition is met**. For instance, look at this code:

```c
on collision(ID_A.block, ID_B.block) {
    // block 1
}

on count(ID_A.item >= 100) {
    // block 2
}

on event(player_jump) {
    // block 3
}
```

Here, block 1 executes when a collision between block IDs $A$ and $B$ happens, block 2 executes the instant item ID $A$ is greater or equal than 100, and block 3 executes when the player jumps. Under the hood there's a Collision, Count and Event trigger associated with each call. Event handlers are *persistent*: once registered, they continue existing after the function finishes executing all its instructions, and remain active until they are explicitly stopped. Note that these also applies for the Advanced Follow trigger, and triggers that support infinite duration like dynamic rotate triggers.

Time for an example. Let's say we want to code the interaction between the player and some enemies. Both the player and the enemies are entities that can exist concurrently, and to register interactions between them we will need Collision triggers to check for collisions. The enemy will chase the player, and we will give the player a sword that can damage the enemy. If the enemy's health reaches zero, we will make it disappear. Those ideas are shown in the code below:

```c
ID_A sword  // ID for the player's sword. We will treat this as a global variable
sword_damage := sword.time
sword_damage = 4.5


GID_C spawn_enemy(ID_B enemy) {
    sprite := enemy.group  // Alias for the enemy group
    health := enemy.time  // Alias for the the time ID where the health is stored
    health = 20  // Set a base health

    // Toggle on the enemy
    toggle(group=sprite, activate_group=true)

    // We will setup an advanced follow trigger so the enemy chases the player
    advanced_follow(target=sprite, follow=P1, easing=150.0, easing_pm=100.0)

    // We will also setup a collision event, that will be active alongside the advanced follow trigger
    // Every collision between the enemy and the sword executes the code below
    on collision(enemy.block, sword.block) {
        health = health - sword_damage

        if (health <= 0) {
            toggle(group=sprite, activate_group=false) // Destroy the enemy
        }
    }
}
```

Here's the implementation in GD:

(Example: 12. Enemy Setup)

The current implementation may look good at first, but it has a huge problem. Once the enemy despawns, if we don't stop the Advanced Follow & Collision triggers, they will keep running *forever* even though the enemy no longer exists, as seen from the video where the enemies keep chasing the player after their health is 0. A first attempt might be to simply add a Stop trigger when the enemy dies. But if we do that, the Stop trigger would stop **every** Advanced Follow and Collision trigger that belongs to the setup, including those used by every other enemy currently alive, which isn't probably what we want.

(Example: 13. Stop Enemy Issue)

The issue comes from the fact that these triggers are persistent. Unlike instantaneous or triggers that hold for a set duration, they continue existing after the function finishes executing, so *they need a way to distinguish which function instance they belong to*. This is the issue Control IDs are meant to fix.

## Control IDs

A Control ID **acts as a local *controller* for persistent triggers**. Assigning a Control ID to a trigger associates that trigger with a *specific function instance*. That way, Pause, Resume and Stop triggers can target that Control ID, affecting **only the triggers that belong to that particular instance**.

This is what allows asynchronous functions to clean up after themselves without interfering with other copies of the same function. Using Control IDs, our enemy function can therefore be rewritten as follows:

```c
ID_A sword
sword_damage := sword.time
sword_damage = 4.5


GID_C spawn_enemy(ID_B enemy) {
    sprite := enemy.group
    health := enemy.time
    health = 20

    // We will now use the enemy's control ID to assign the advanced follow & collision triggers to this particular enemy instance
    behaviour := enemy.control

    toggle(group=sprite, activate_group=true)

    // We set the control ID to stop the advanced follow & collision triggers when the enemy dies
    advanced_follow(target=sprite, follow=P1, easing=150.0, easing_pm=100.0, control=behaviour)

    on collision(enemy.block, sword.block, control=behaviour) {
        health = health - sword_damage

        if (health <= 0) {
            toggle(group=sprite, activate_group=false)
            stop(target=behaviour, use_control=true)
        }
    }
}
```

Notice that both the Advanced Follow trigger and the Collision trigger use the same Control ID, stored in `enemy.control`. When the enemy dies, the Stop trigger that handles the `stop(target=behaviour, use_control=true)` operation only stops the triggers associated with *that particular enemy*. Every other enemy has its own Control ID, so its behaviour continues unaffected.

(Example: 14. Control IDs)

Control IDs are therefore one of the most important tools for writing reusable asynchronous functions. **Whenever a function creates persistent behaviour, such as Collision, Count, Event, Time Event triggers, it is generally good practice to associate those triggers with a Control ID**. This allows each function instance to manage its own lifetime independently from every other instance. We can also add them to any other trigger if we want to control their behaviour as well, like stoping moving triggers prematurely per instance.

Control IDs are not limited to stopping triggers, either. Since Pause and Resume also operate on Control IDs, they can temporarily suspend or continue only a specific function instance without affecting the rest of the level. This makes them useful whenever asynchronous tasks need to be coordinated or synchronized. Additionally, they can also be used in conjunction with the Retarget Advanced Follow trigger in order to set an specific instance of an Advanced follow trigger chase a different ID, without making other instances do the same.

# 6. 0-Tick Functions

Although multi-tick functions are sometimes unavoidable, many trigger setups can be redesigned so they complete within a single frame. Besides making synchronization much simpler, this often improves readability, reusability and performance. The next section explores these functions in more detail.

Functions that work in a single frame are often referred as **0-Tick functions** due to how they don't need to wait for a tick in order to be executed again: *you can activate them multiple times within a single tick*.

## How to Achieve 0-Tick

Discuss methods like spawn order and inlining, and also game limitations.

# 7. Performance

Finally, we will discuss performance. We've covered so far a lot of ways to use functions, but depending on how these are implemented they can begin to take a toll on performance. ...

## Stacked Triggers

Discuss how having lots of concurrent & inline triggers impact performance.

## Overhead

Discuss spawn remap overhead.

# Continuation

This guide layed down the foundation of treating GD triggers as a programming language. There was a lot to unpack to explain the basics, but applying some or all of these concepts will allow you to make complex setups while taking advantage of key trigger concepts and understanding the game's limitations.

Note that we didn't cover function composition, classes or memory allocation, which are also common programming concepts. Those will be explained more carefully in upcoming guides.
