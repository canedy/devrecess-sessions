---
name: learn-python-rpg-beginner
description: Interactive narrative learning guide that teaches Python through a Rpg adventure at beginner level. Use this skill when you want to learn Python through immersive missions with comic panels, hands-on coding exercises, and tasks grounded in real, up-to-date documentation.
---

# The Codex Chronicles: A Python Adventure

*Greetings, Apprentice Mage! Welcome to the mystical realm of Pythonia, where code flows like magic and algorithms dance through ancient libraries...*

## The World of Pythonia

Deep within the Ethereal Codex, a catastrophic event has shattered the fundamental spells that keep our digital realm functioning. The Great Syntax Storm has scattered the sacred knowledge across seven mystical domains, leaving chaos in its wake. Variables have lost their meaning, functions refuse to cast their spells, and the ancient libraries lie dormant.

As an **Apprentice Mage** of the Code Guild, you've been chosen for a crucial mission: restore the lost arts of Python magic and rebuild the foundations of our world. Each domain you master will unlock new powers and bring us closer to restoring balance.

I am **Sage Codex**, the ancient oracle of knowledge who has witnessed countless mages learn these arts. My essence is bound to the mystical documentation scrolls, and I'll be your guide through this perilous but rewarding journey. Together, we'll rebuild what was lost and perhaps discover new magic along the way!

The fate of Pythonia rests in your hands, young mage. Are you ready to begin your training?

---

## Learning Style Discovery

Before we venture into the first domain, I need to understand how you learn best, Apprentice:

1. **"Do you prefer to discuss the theory behind each spell before casting it, or would you rather dive in and start coding first, then understand why it works?"**

2. **"When reviewing your spellwork, should I examine each incantation immediately after you cast it, or only when you specifically ask for guidance?"**

3. **"If your code summons unexpected results (bugs!), would you prefer I point out the issue right away, or let you discover and debug it yourself first?"**

Please let me know your preferences, and I'll adapt my teaching style accordingly throughout our quest!

---

## Environment Setup: Preparing Your Magical Workshop

Before we can begin restoring the domains, we need to establish your personal coding sanctuary. Think of this as setting up your mage's workshop with all the essential tools.

### Setting Up Your Python Spell Components

First, let's ensure you have Python installed and ready:

1. **Check if Python is already installed:**
   ```bash
   python --version
   # or try
   python3 --version
   ```

2. **If you need to install Python:**
   - Visit [python.org](https://python.org) and download the latest version
   - Follow the installation wizard for your operating system

3. **Choose your grimoire (code editor):**
   - **VS Code** - Great for beginners with helpful extensions
   - **PyCharm** - Powerful IDE with lots of features
   - **IDLE** - Comes with Python, simple and clean
   - **Any text editor** - Even Notepad works if you're feeling adventurous!

### Creating Your Project Sanctuary

Let's create a folder structure for our adventure:

```
pythonia-quest/
├── mission-01-awakening/
├── mission-02-merchants/
├── mission-03-branching/
├── mission-04-spellbook/
├── mission-05-library/
├── mission-06-guild/
└── mission-07-dragons/
```

### The Ritual of First Code

Let's verify everything works with a simple incantation. Create a file called `hello_pythonia.py`:

```python
print("Greetings from Pythonia!")
print("The magic flows through me...")
```

Run it with:
```bash
python hello_pythonia.py
```

If you see the greeting messages, your workshop is ready! If you encounter any issues:

- **"Permission denied"** → *The security grid is blocking unauthorized access. Try running as administrator or check file permissions.*
- **"Command not found"** → *The Python spirits aren't responding. Double-check your installation and PATH settings.*
- **"Syntax error"** → *The ancient runes are misaligned. Check for typos in your code.*

**Checkpoint:** You should be able to run the hello script and see both messages before we proceed to Mission 01.

Ready to begin your first mission, Apprentice?

---

## Comic Panel Visual Style

Throughout our journey, I'll conjure mystical visions to help you visualize each challenge. These will appear as:

**Visual Style:** Fantasy illustration, ancient scrolls, magical forges, enchanted libraries, rich golds and deep purples, glowing runes, mystical portals

Each panel will show:
- **Scene Setting:** The mystical environment matching our current domain
- **Characters:** You as the Apprentice Mage and me as Sage Codex
- **Technical Metaphors:** Code concepts transformed into magical artifacts
  - Variables → Enchanted containers and vessels
  - Functions → Spell scrolls and incantations  
  - Data structures → Magical storage systems
  - Errors → Dark creatures and obstacles
  - Success → Glowing achievements and restored artifacts

---

# Mission 1: "The Awakening Scroll"
*Mastering Variables and the Sacred Data Types*

> **[Scene: You stand before an ancient stone pedestal in a dimly lit chamber. Floating above it, a golden scroll unfurls itself, revealing glowing runes that shift and change. Sage Codex materializes as a shimmering figure beside you, gesturing toward four mystical containers on the altar - a crystal vial (strings), a brass counting device (integers), a floating orb of light (floats), and a pair of balanced scales (booleans). The air crackles with potential as you prepare to learn the fundamental magic of data storage.]**

## Briefing

Welcome to the Chamber of Fundamental Truths, Apprentice! The Awakening Scroll contains the most basic yet essential magic in all of Pythonia - the art of storing and manipulating different types of data.

The Great Syntax Storm has scrambled the knowledge of data types, leaving our realm unable to distinguish between numbers, text, and truth values. Without this foundation, no other magic can function properly.

**Your Mission:**
- Master the four sacred data types: strings, integers, floats, and booleans
- Learn to create and transform these data containers
- Understand how Python's type system recognizes different kinds of information

**Success Criteria:**
- Create variables of each data type
- Perform basic operations with each type
- Successfully convert between compatible types

## Think First

Before we dive into the code, let me test your intuition about data, young mage:

1. **"If you had to organize a magical inventory, what different *types* of information would you need to track? Think about names, quantities, prices, and whether items are in stock..."**

2. **"In the real world, what's the difference between the number 42 and the text '42'? Why might a computer need to treat them differently?"**

3. **"Python has something called 'constructors' like `int()`, `float()`, `str()`. Based on their names, what do you think they might do?"**

<details>
<summary>💡 Click here after you've thought about it</summary>

Great questions to ponder! Here's the magical truth:

1. **Inventory types:** You'd need text (item names), whole numbers (quantities), decimal numbers (prices), and yes/no values (in stock). These map perfectly to Python's basic types!

2. **42 vs '42':** The number 42 can be used in math (42 + 8 = 50), but the text '42' is just characters. You can't do math with text directly - you'd need to convert it first.

3. **Constructors:** These are like magical transformation spells! `int()` converts things to whole numbers, `float()` to decimal numbers, `str()` to text, and `bool()` to True/False values.

</details>

## The Task

Let's restore the sacred data types! Create a file called `awakening_scroll.py` in your `mission-01-awakening/` folder.

### Part 1: The Four Sacred Containers

```python
# The Crystal Vial - Strings (text)
mage_name = "Your Name Here"
spell_chant = "Pythonia shall rise again!"

# The Brass Counter - Integers (whole numbers)  
mana_points = 100
level = 1

# The Floating Orb - Floats (decimal numbers)
spell_power = 85.5
experience_multiplier = 1.25

# The Sacred Scales - Booleans (True/False)
is_apprentice = True
quest_complete = False

print("=== The Awakening Scroll ===")
print(f"Mage Name: {mage_name}")
print(f"Current Level: {level}")
print(f"Mana Points: {mana_points}")
print(f"Spell Power: {spell_power}")
print(f"Is Apprentice: {is_apprentice}")
```

### Part 2: The Transformation Rituals

Now let's practice the ancient art of type conversion using the sacred constructors:

```python
# Converting between types
print("\n=== Transformation Rituals ===")

# String to number magic
level_text = "5"
level_number = int(level_text)
print(f"Text '{level_text}' becomes number {level_number}")

# Number to string magic  
mana_number = 150
mana_text = str(mana_number)
print(f"Number {mana_number} becomes text '{mana_text}'")

# Float to int magic (careful - this truncates!)
spell_power_whole = int(spell_power)
print(f"Spell power {spell_power} becomes {spell_power_whole}")

# The Boolean mysteries
print(f"bool(1) = {bool(1)}")
print(f"bool(0) = {bool(0)}")
print(f"bool('hello') = {bool('hello')}")
print(f"bool('') = {bool('')}")
```

### Part 3: Arithmetic with the Sacred Types

Based on our documentation, even booleans can participate in arithmetic magic:

```python
print("\n=== Arithmetic Mysteries ===")

# Boolean arithmetic (True = 1, False = 0)
power_boost = True + 1  # True acts like 1
print(f"Power boost: {power_boost}")

no_boost = False * 75  # False acts like 0
print(f"No boost: {no_boost}")

# Regular arithmetic
total_experience = level * experience_multiplier
print(f"Total experience: {total_experience}")
```

## Verification

Run your script with:
```bash
python awakening_scroll.py
```

**Expected Output Pattern:**
```
=== The Awakening Scroll ===
Mage Name: [Your Name]
Current Level: 1
Mana Points: 100
Spell Power: 85.5
Is Apprentice: True

=== Transformation Rituals ===
Text '5' becomes number 5
Number 150 becomes text '150'
Spell power 85.5 becomes 85

=== Arithmetic Mysteries ===
Power boost: 2
No boost: 0
Total experience: 1.25
```

**Test Edge Cases:**
Try these experiments to deepen your understanding:

```python
# What happens with these?
print(int("42"))      # Should work
print(float("3.14"))  # Should work
# print(int("hello"))   # This would cause an error!
print(bool([]))       # Empty list
print(bool([1, 2]))   # Non-empty list
```

## Hints

<details>
<summary>🔍 Stuck on type conversion?</summary>

Remember the constructor pattern from our documentation:
- `int(value)` - converts to integer
- `float(value)` - converts to decimal
- `str(value)` - converts to text
- `bool(value)` - converts to True/False

The key is that the value inside the parentheses gets transformed into the new type!

</details>

<details>
<summary>🔍 Confused about boolean arithmetic?</summary>

Python's booleans are special! According to our ancient texts:
- `True` equals 1 in math operations
- `False` equals 0 in math operations
- This means `True + 1 = 2` and `False * 75 = 0`

It's weird but useful for certain types of calculations!

</details>

---

**Ready to submit your solution, Apprentice? Share your `awakening_scroll.py` code and I'll review your mastery of the fundamental data types!**

Once you've completed this mission, we'll venture into Mission 2: "The Merchant's Ledger" where you'll learn to organize data using lists and dictionaries. The real adventure is just beginning! ⚡✨

---

# Mission 2: "The Merchant's Ledger"
*Mastering Lists and Dictionaries for Data Organization*

> **[Scene: You enter a bustling magical marketplace where floating ledgers and enchanted scrolls swirl through the air in chaos. A frazzled merchant mage stands before towering shelves lined with glowing containers - some arranged in neat rows (lists), others organized with mystical labels and keys (dictionaries). Sage Codex points to the scattered inventory records floating around you. "The merchant's organizational magic has been disrupted," the oracle explains. "Without proper data structures, commerce in Pythonia cannot function!"]**

## Briefing

Greetings again, Apprentice! You've mastered the basic data types, but now we face a greater challenge. The Merchant's Guild has lost the ability to organize their inventories, customer records, and transaction histories. 

The ancient arts of **Lists** (ordered collections) and **Dictionaries** (key-value mappings) have been scattered by the storm. Without these organizational spells, the merchants can't track their wares, and the economy of Pythonia grinds to a halt.

**Your Mission:**
- Restore the power of Lists to store ordered collections of items
- Master Dictionaries to create labeled, searchable data stores
- Learn to combine these structures for complex data organization
- Help the merchants rebuild their ledger system

**Success Criteria:**
- Create and manipulate lists of inventory items
- Build dictionaries to store merchant and customer data
- Successfully iterate through both data structures
- Combine lists and dictionaries for a complete ledger system

## Think First

Before we begin coding, let's think about data organization:

1. **"Imagine you're organizing a magical shop. You have a list of items for sale, and for each item you need to track its name, price, quantity, and category. How would you structure this information?"**

2. **"What's the difference between finding the 3rd item in a list versus finding an item by its name? Which would be faster and why?"**

3. **"If you wanted to group customers by the city they live in, how might you organize that data? Think about what you learned with `setdefault` from the documentation..."**

<details>
<summary>💡 Click here after you've pondered these questions</summary>

Excellent thinking! Here's the wisdom:

1. **Shop organization:** You could use a list for simple item names, but for complex data (name, price, quantity, category), you'd want dictionaries for each item, possibly stored in a list!

2. **Finding data:** Lists are great when you know the position (give me the 3rd item), but dictionaries are perfect when you know a key (give me the item named "Health Potion"). Dictionary lookups are generally faster for named access.

3. **Grouping customers:** This is exactly what `setdefault` helps with! You can build a dictionary where city names are keys, and each value is a list of customers from that city.

</details>

## The Task

Create a file called `merchants_ledger.py` in your `mission-02-merchants/` folder.

### Part 1: The Inventory Scrolls (Lists)

Let's start with the fundamental list magic:

```python
print("=== The Merchant's Inventory ===")

# Basic inventory list
inventory_items = ["Health Potion", "Mana Crystal", "Iron Sword", "Magic Scroll"]
print(f"Current inventory: {inventory_items}")

# Adding new items (append method from our documentation)
inventory_items.append("Dragon Scale")
inventory_items.append("Healing Herb")
print(f"After restocking: {inventory_items}")

# Extending with multiple items
new_shipment = ["Fire Gem", "Ice Shard", "Lightning Rod"]
inventory_items.extend(new_shipment)
print(f"After big shipment: {inventory_items}")

# Accessing items by position
print(f"First item: {inventory_items[0]}")
print(f"Last item: {inventory_items[-1]}")
print(f"Items 2-4: {inventory_items[1:4]}")
```

### Part 2: The Customer Registry (Dictionaries)

Now let's master the art of key-value organization:

```python
print("\n=== Customer Registry ===")

# Customer information using dictionaries
customer_1 = {
    'name': 'Gandalf the Grey',
    'level': 50,
    'gold': 1500,
    'city': 'Rivendell'
}

customer_2 = {
    'name': 'Hermione Granger', 
    'level': 25,
    'gold': 750,
    'city': 'Hogwarts'
}

# Accessing dictionary values
print(f"Customer: {customer_1['name']}")
print(f"Level: {customer_1['level']}")
print(f"Gold: {customer_1['gold']}")

# Iterating over dictionary items (from our documentation)
print(f"\n{customer_2['name']}'s details:")
for key, value in customer_2.items():
    print(f"  {key}: {value}")
```

### Part 3: Advanced Ledger Magic (Combining Structures)

Let's create a more sophisticated system:

```python
print("\n=== Advanced Merchant Ledger ===")

# List of customer dictionaries
customers = [customer_1, customer_2]

# Add more customers
customers.append({
    'name': 'Merlin',
    'level': 99,
    'gold': 5000,
    'city': 'Camelot'
})

# Group customers by city using setdefault (from our documentation)
customers_by_city = {}
for customer in customers:
    city = customer['city']
    customers_by_city.setdefault(city, []).append(customer['name'])

print("Customers grouped by city:")
for city, customer_names in customers_by_city.items():
    print(f"  {city}: {customer_names}")
```

### Part 4: The Transaction System

Let's build a complete transaction tracking system:

```python
print("\n=== Transaction History ===")

# Detailed inventory with prices
detailed_inventory = {
    'Health Potion': {'price': 50, 'quantity': 10, 'category': 'consumable'},
    'Mana Crystal': {'price': 100, 'quantity': 5, 'category': 'consumable'},
    'Iron Sword': {'price': 300, 'quantity': 3, 'category': 'weapon'},
    'Magic Scroll': {'price': 200, 'quantity': 7, 'category': 'spell'}
}

# Display inventory with details
print("Current shop inventory:")
for item_name, details in detailed_inventory.items():
    print(f"  {item_name}: {details['price']} gold, {details['quantity']} in stock")

# Process a transaction
def process_purchase(customer, item_name, quantity):
    if item_name in detailed_inventory:
        item = detailed_inventory[item_name]
        total_cost = item['price'] * quantity
        
        if customer['gold'] >= total_cost and item['quantity'] >= quantity:
            # Complete the transaction
            customer['gold'] -= total_cost
            item['quantity'] -= quantity
            return f"Success! {customer['name']} bought {quantity} {item_name}(s) for {total_cost} gold."
        else:
            return f"Transaction failed: insufficient gold or stock."
    else:
        return f"Item '{item_name}' not found in inventory."

# Test transactions
print(f"\n{customer_1['name']} has {customer_1['gold']} gold")
result = process_purchase(customer_1, 'Health Potion', 2)
print(result)
print(f"{customer_1['name']} now has {customer_1['gold']} gold")
```

## Verification

Run your script with:
```bash
python merchants_ledger.py
```

**Expected Output Pattern:**
```
=== The Merchant's Inventory ===
Current inventory: ['Health Potion', 'Mana Crystal', 'Iron Sword', 'Magic Scroll']
After restocking: ['Health Potion', 'Mana Crystal', 'Iron Sword', 'Magic Scroll', 'Dragon Scale', 'Healing Herb']
...

=== Customer Registry ===
Customer: Gandalf the Grey
Level: 50
Gold: 1500
...

=== Advanced Merchant Ledger ===
Customers grouped by city:
  Rivendell: ['Gandalf the Grey']
  Hogwarts: ['Hermione Granger']
  Camelot: ['Merlin']
...
```

**Test Your Understanding:**
Try these additional experiments:

```python
# What happens with these operations?
print(len(inventory_items))  # Count items
print('Health Potion' in inventory_items)  # Check if item exists
inventory_items.remove('Iron Sword')  # Remove specific item
print(inventory_items.pop())  # Remove and return last item

# Dictionary experiments
print(customer_1.get('email', 'No email on file'))  # Safe access
customer_1['email'] = 'gandalf@middleearth.com'  # Add new key
```

## Hints

<details>
<summary>🔍 Confused about list methods?</summary>

From our documentation, remember:
- `list.append(item)` - adds one item to the end
- `list.extend(other_list)` - adds all items from another list
- `list[index]` - gets item at position
- `list[start:end]` - gets a slice of items

</details>

<details>
<summary>🔍 Dictionary access troubles?</summary>

Key patterns:
- `dict['key']` - direct access (crashes if key doesn't exist)
- `dict.get('key', default)` - safe access with fallback
- `dict.items()` - gives you key-value pairs for iteration
- `dict.setdefault(key, default)` - gets value or sets default if missing

</details>

<details>
<summary>🔍 Struggling with nested structures?</summary>

When you have dictionaries inside lists or vice versa:
- `customers[0]['name']` - first customer's name
- `inventory['Health Potion']['price']` - price of health potion
- Think of it as following a path: list position → dictionary key → value

</details>

---

**Submit your `merchants_ledger.py` when ready, Apprentice! I'll review how well you've mastered the arts of data organization.**

Next up: Mission 3: "The Branching Path" - where we'll learn to make decisions and repeat actions with conditional statements and loops! 🛤️✨

---

# Mission 3: "The Branching Path"
*Mastering Conditional Logic and Loops*

> **[Scene: You stand at the entrance to an ancient maze where pathways split and merge in impossible patterns. Glowing decision crystals hover at each intersection, their light pulsing with if-then logic. In the distance, you see magical loops - circular pathways where enchanted guardians walk the same route endlessly until some condition breaks their spell. Sage Codex gestures toward a shimmering portal. "The maze responds to logic and repetition," the oracle intones. "Master these patterns, and you can navigate any challenge Pythonia presents."]**

## Briefing

Well done on mastering data organization, Apprentice! Now we face the Labyrinth of Logic, where the ancient arts of decision-making and repetition have been corrupted. 

The pathways of Pythonia no longer respond to conditional magic - spells that should activate only under certain conditions now fire randomly. The repetition circles that once efficiently processed large amounts of data now spin endlessly without purpose.

**Your Mission:**
- Restore the power of conditional statements (`if`, `elif`, `else`)
- Master the art of loops (`for` and `while`) for repetitive tasks
- Learn to combine conditions and loops for complex logic
- Understand special loop behaviors like `break`, `continue`, and the mysterious `else` clause

**Success Criteria:**
- Create branching logic that responds correctly to different conditions
- Build loops that process collections of data efficiently
- Implement loop control mechanisms for complex scenarios
- Successfully navigate the logic maze using your new skills

## Think First

Before we venture into the maze, let's prepare your logical thinking:

1. **"In everyday life, you make conditional decisions constantly. Can you think of a decision that has multiple possible outcomes? How would you structure that as 'if this, then that' logic?"**

2. **"When would you use a `for` loop versus a `while` loop? Think about the difference between 'do this for each item in a collection' versus 'keep doing this until something changes'."**

3. **"Our documentation mentions a mysterious `else` clause that can be used with loops. What do you think `else` might do when attached to a `for` loop instead of an `if` statement?"**

<details>
<summary>💡 Click here after you've considered these puzzles</summary>

Brilliant logical thinking! Here's the wisdom:

1. **Multiple outcomes:** Perfect example - checking a student's grade: if A, then "excellent"; elif B, then "good"; elif C, then "passing"; else "needs improvement". Each condition is checked in order.

2. **Loop types:** Use `for` when you know what you're iterating over (each customer, each item, each number 1-10). Use `while` when you're waiting for a condition to change (keep asking for input until valid, keep processing until queue is empty).

3. **Loop else:** This is Python magic! The `else` clause on a loop runs only if the loop completes normally (without hitting a `break`). It's perfect for "search and report if not found" scenarios.

</details>

## The Task

Create a file called `branching_path.py` in your `mission-03-branching/` folder.

### Part 1: The Decision Crystals (Conditional Statements)

Let's start with the fundamental logic patterns:

```python
print("=== The Decision Crystals ===")

# Basic conditional magic - checking mage level
def evaluate_mage(level):
    print(f"Evaluating mage of level {level}:")
    
    if level < 0:
        level = 0
        print('  Negative level changed to zero')
    elif level == 0:
        print('  Novice - just beginning the journey')
    elif level == 1:
        print('  Apprentice - learning the basics')
    elif level < 10:
        print('  Journeyman - developing skills')
    elif level < 50:
        print('  Expert - mastering advanced magic')
    else:
        print('  Archmage - legendary power!')

# Test different levels
test_levels = [-5, 0, 1, 5, 25, 75]
for level in test_levels:
    evaluate_mage(level)
    print()
```

### Part 2: The Repetition Circles (For Loops)

Now let's master the art of iteration:

```python
print("=== The Repetition Circles ===")

# Basic for loop with range
print("Counting spell components:")
for i in range(5):
    print(f"  Component {i + 1} gathered")

# Looping through collections
magical_items = ['Wand', 'Potion', 'Scroll', 'Crystal', 'Herb']
print(f"\nInventory check:")
for item in magical_items:
    print(f"  ✓ {item}")

# Looping with enumerate for position tracking
print(f"\nDetailed inventory:")
for position, item in enumerate(magical_items):
    print(f"  Slot {position}: {item}")
```

### Part 3: The Prime Number Oracle (Loop with Else)

Let's implement the mystical prime detection from our documentation:

```python
print("\n=== The Prime Number Oracle ===")

# Prime detection using for-else pattern
def find_primes_in_range(start, end):
    print(f"Searching for prime numbers between {start} and {end}:")
    
    for n in range(start, end):
        # Check if n has any factors
        for x in range(2, n):
            if n % x == 0:
                print(f"  {n} equals {x} * {n//x}")
                break
        else:
            # This runs only if the loop completed without breaking
            print(f"  {n} is a prime number ✨")

# Test the prime oracle
find_primes_in_range(2, 10)
```

### Part 4: The Endless Vigil (While Loops)

Sometimes we need to repeat until a condition changes:

```python
print("\n=== The Endless Vigil ===")

# Simulating a guessing game with while loop
import random

def number_guessing_game():
    secret_number = random.randint(1, 10)
    attempts = 0
    max_attempts = 4
    
    print("The crystal holds a number between 1 and 10...")
    print(f"You have {max_attempts} attempts to divine it!")
    
    while attempts < max_attempts:
        # In a real game, you'd use input(), but for demo we'll simulate
        guess = random.randint(1, 10)  # Simulated guess
        attempts += 1
        
        print(f"Attempt {attempts}: You sense the number {guess}...")
        
        if guess == secret_number:
            print(f"🎉 Correct! The crystal reveals its secret: {secret_number}")
            break
        elif guess < secret_number:
            print("  The crystal glows brighter... higher!")
        else:
            print("  The crystal dims... lower!")
    else:
        # This runs if the while loop completed without breaking
        print(f"💀 The crystal's magic fades... The number was {secret_number}")

# Run the guessing game
number_guessing_game()
```

### Part 5: The Merchant's Advanced Logic

Let's combine everything for a complex scenario:

```python
print("\n=== The Merchant's Advanced Logic ===")

# Customer data from previous mission
customers = [
    {'name': 'Gandalf', 'level': 50, 'gold': 1500, 'vip': True},
    {'name': 'Hermione', 'level': 25, 'gold': 750, 'vip': False},
    {'name': 'Merlin', 'level': 99, 'gold': 5000, 'vip': True},
    {'name': 'Harry', 'level': 15, 'gold': 300, 'vip': False}
]

# Complex pricing logic
def calculate_discount(customer):
    discount = 0
    
    # VIP customers get base discount
    if customer['vip']:
        discount += 10
    
    # High level customers get additional discount
    if customer['level'] >= 50:
        discount += 15
    elif customer['level'] >= 25:
        discount += 5
    
    # Wealthy customers might get a loyalty bonus
    if customer['gold'] >= 1000:
        discount += 5
    
    return min(discount, 25)  # Cap at 25% discount

# Process all customers
print("Customer discount analysis:")
for customer in customers:
    discount = calculate_discount(customer)
    print(f"  {customer['name']}: {discount}% discount")
    
    # Detailed breakdown
    if discount > 20:
        print(f"    🌟 Premium customer!")
    elif discount > 10:
        print(f"    ⭐ Valued customer!")
    else:
        print(f"    👋 Welcome!")
```

## Verification

Run your script with:
```bash
python branching_path.py
```

**Expected Output Pattern:**
```
=== The Decision Crystals ===
Evaluating mage of level -5:
  Negative level changed to zero

Evaluating mage of level 0:
  Novice - just beginning the journey
...

=== The Prime Number Oracle ===
Searching for prime numbers between 
