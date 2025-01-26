# Road to Pet Clinic
The goal is to provide beginners with a structured approach to Java, during this road you'll build numerous small scale programs like:
- various currency/temperature/time converters (data type practice)
- Drawing various shapes using loops (for, while)
- and other miscalenous 

You'll build 2 Big projects:
- Pet Clinic CLI (String manipulation, Validation, Regex, OOP)
- Pet Clinic REST API (Everything in Pet Clinic CLI + REST, Database)

They'll support:
- Creating/Reading/Updating doctors
- Creating/Reading/Updating doctor specialties
- Creating/Reading/Updating Pet & Pet Owners
- Creating/Reading/Updating Pet visitations for doctors 

## Basics
"_Before one can run, one must crawl, before one can crawl, one must be born, before one is born, one must be a small sparkle of desire in the eyes of their parents." - Sun Tzu
### 01. How does  a java program look like 
```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world");
    }
}
```
Theory: Java is an Object orientated language, in Java any and every logic is contained within classes/objects a:
1. _Methods_ - it's logic that can be executed within our program and they are contained within a class (the main(String[] args)
2. _Classes_ - it's a larger container for interconnected logic, it can also contain variables and constants(the Main)

**Note: ignore public, class and static keywords, we'll focus on them later**
**Some things that should be remembered are that every { must have a }, every ( must have a ), every [ must have a ]**
```java
    public class SomeClassName {
        //notice how each bracket must be closed
    }
```
**An example of opening and closing brackets and nesting**
```java
    public class SomeClassName { //open bracker 01
        public void someMethod(){ //open bracket 02
            
        } //close bracket 02
    }//close bracket 01
```
If you're very observant by now you would have noticed that methods have an extra pair of brackets **( )**, sometimes they may have something written inthem, we'll focus on this in a later session
```java 
```
### 02. The core types
No that you know the basics of a java program, you're ready to start writing 
| Type    | Explanation                                    | Range/Values                                                                                 | Typical Use Case                                                   |
|---------|------------------------------------------------|----------------------------------------------------------------------------------------------|--------------------------------------------------------------------|
| boolean | Holds `true` or `false`                        | `true` or `false`                                                                            | Checking conditions (e.g., if a condition is met)                  |
| byte    | 8-bit integer                                  | `-128` to `127`                                                                              | Storing very small integers when memory is tight                   |
| short   | 16-bit integer                                 | `-32768` to `32767`                                                                          | Older code or constrained systems needing small integer storage    |
| int     | 32-bit integer                                 | `-2,147,483,648` to `2,147,483,647`                                                          | Most general-purpose integer calculations                          |
| long    | 64-bit integer                                 | `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807`                                  | Large integer calculations (e.g., big counters)                    |
| float   | 32-bit floating-point number                   | Approx. `1.4E-45` to `3.4028235E38`                                                          | Storing decimal numbers when moderate precision is enough          |
| double  | 64-bit floating-point number                   | Approx. `4.9E-324` to `1.7976931348623157E308`                                               | Storing decimal numbers with higher precision                      |
| char    | Single 16-bit Unicode character                | `\u0000` (0) to `\uffff` (65535)                                                            | Storing one character (e.g., letters, symbols)                     |
| String  | Sequence of characters (not primitive in Java) | No fixed limit (depends on available memory)                                                | Storing text like words and sentences                              |

Think of  int, double and String as the defaults :), the other are more niche types
**Note**: Some data types are omitted just to not confuse you.
#### Usage in a program
| Type    | Declaration Example               |
|---------|------------------------------------|
| boolean | `boolean myFlag = true;`          |
| byte    | `byte myByte = 100;`              |
| short   | `short myShort = 200;`            |
| int     | `int myInt = 1000;`               |
| long    | `long myLong = 10000L;`           |
| float   | `float myFloat = 3.14f;`          |
| double  | `double myDouble = 3.14;`         |
| char    | `char myChar = 'A';`              |
| String  | `String myString = "Hello";`     |

#### Lets reason? 
1. You're writing an application that tracks warranty in years of a washing machine, memory is very important, what type of data do you use?
2. You're writing an application that tracks warranty in years of a washing machine, we've got all the memory in the world, what data types do you use? 
3. You're supposed to storesomebodys name, what type of data do you use?
4. You're doing some calculations which involve a "," percision isn't important, we need a rough estimate, what data do you use?
5. You're doing very more percise calculations involving a "," what type of data do you use? 
6. You're doing calulcations involving very long data, what type of data do you use?

### Interacting with our code

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter your first name: "); // output
        String firstName = scanner.nextLine(); // read from console

        System.out.print("Enter your last name: "); // output
        String lastName = scanner.nextLine(); //read from console again

        System.out.println("Your name is " + firstName + " " + lastName); // Output in console
    }
}
```
Try reading numbers from the scanner, you'll see that you're going to encounter issues
```java
int number = scanner.nextLine()
```
Scanner provides built in functions like:
 - nextInt()
 - nextDouble()
 - many more

However, if you forget about them, remember you've got a String, and each of the prvious types (short, double, byte, int) have a corresponding one with a capital letter (Short, Double, Byte, Int) that has a method .parseDouble, .parseInt that accepts a string
```java
    String iExpectANumber = scanner.nextLine(); // read from console
    int realValue = Int.parseInt(iExpectANumber)
```

Now we're ready to make the first steps and expand a bit. 

After this point, you should get the basics of the type. 
### A Group, basic data types
1. **Michael’s Ferry Challenge**  
   Michael, the boatsman, has **17 people** to ferry across a river before nightfall. His small raft only carries **4 people** at a time.  
   **Question**: How many trips does he need to make?

2. **Sophia’s Party Pizzas**  
   Sophia is throwing a party for her **14 friends**, and each pizza has **8 slices**. She wants everyone to have at least **1 slice**.  
   **Question**: How many pizzas should she order?

3. **Amir’s Road Trip**  
   Amir wants to visit his grandmother, who lives **150 km** away. He’ll drive at **50 km/h**.  
   **Question**: How many hours will the trip take?

4. **Valerie’s Archery Practice**  
   Valerie has **45 arrows** in her quiver, and each monster she fights requires **8 arrows**.  
   **Question**: How many monsters can she defeat, and how many arrows remain?

5. **Leo’s Vending Machine Snack**  
   Leo has **$2.50** to spend on a vending machine snack that costs **$1.70**.  
   **Question**: How much change will he get back?

6. **Treasure Hunter Tasha**  
   Tasha opens **12 treasure chests**, each containing **3 gold coins**.  
   **Question**: How many coins does she end up with?

7. **Noah’s Fuel Calculation**  
   Noah’s car consumes **1 liter** of fuel per **15 km** driven. He needs to travel **120 km**.  
   **Question**: How many liters of fuel will he use?

8. **Emily’s Discount Dilemma**  
   Emily sees a store offering **20% off** on a **$50** item.  
   **Question**: What is the discounted price she’ll pay?

9. **Jon’s Age in Days**  
   Jon is **20 years** old. Ignoring leap years,  
   **Question**: How many days has he (approximately) been alive?

10. **Zara’s Classroom Puzzle**  
    Zara’s school has **155 students** and each classroom can seat **30 students**.  
    **Question**: How many classrooms are needed so nobody is left standing?

11. **Carmen’s Celsius Conversion**  
    Carmen has a temperature reading of **25°C**. Using `F = (C * 9/5) + 32`,  
    **Question**: What is that in Fahrenheit?

12. **Ethan’s Marathon**  
    Ethan runs a marathon of **42.195 km** in **4 hours**.  
    **Question**: What is his average speed in km/h?

13. **Ivy’s Restaurant Bill**  
    Ivy and **2 friends** ate at a restaurant. The total bill was **$90**. They want to split it equally.  
    **Question**: How much does each pay?

14. **Rachel’s Cash Conundrum**  
    Rachel needs to pay **$57** but only has **$20** bills in her wallet.  
    **Questions**: How many \$20 bills does she use, and what is her change?

15. **Bruno’s Typing Limit**  
    Bruno is writing a review in a text field that can hold **200 characters**. He has already typed **75**.  
    **Question**: How many characters can he still type?

16. **Lily’s Timezone Check**  
    Lily’s local time is **2 PM**, while her friend’s time zone is **3 hours behind**.  
    **Question**: What time is it for her friend?

17. **Oscar’s Packing Mission**  
    Oscar must pack **93 items** into boxes that each hold **10 items**.  
    **Questions**: How many full boxes can he fill, and how many items remain unpacked?

18. **Nina’s Camping Trip**  
    Nina needs **2 liters** of water per day on her camping trip. She plans to camp for **5 days**.  
    **Question**: How many liters does she need to bring?

19. **Mia’s Musical Beats**  
    Mia’s song is **3 minutes** long (i.e., **180 seconds**) and runs at **120 beats per minute**.  
    **Question**: How many total beats are in the entire song?

20. **Marco’s Painting Project**  
    Marco has a wall of **30 square meters** to paint. Each can of paint covers **12 square meters**.  
    **Question**: How many cans does he need?

21. **Ella’s Username Length**  
    Ella’s username must be at least **8 characters** long.  
    **Task**: Write a check (boolean) confirming if her username meets this length, and print a message.

22. **Kevin’s Bank Interest**  
    Kevin deposits **$1000** at **5% annual interest** (simple interest).  
    **Question**: How much will he have after 1 year?

23. **Grace’s Movie Snacks**  
    Grace invites **4 friends** for a movie night. Each person eats roughly **2.5 bags** of popcorn.  
    **Question**: How many bags should she have on hand?

24. **Luca’s Gaming Teams**  
    Luca has **56 participants** in a gaming tournament, forming teams of **5** players each.  
    **Questions**: How many full teams can he create, and how many players are left over?

25. **Olivia’s Batch Processing**  
    Olivia’s factory machine processes **7 units** per minute. She needs to process **100 units** total.  
    **Question**: How many minutes will it take?

26. **Theo’s Calorie Burn**  
    Theo burns **9 calories** per minute while running. In a **30-minute** run,  
    **Question**: How many total calories does he burn?

27. **Isabella’s Currency Exchange**  
    Isabella is traveling from the US to Canada. The exchange rate is **1 USD = 1.2 CAD**. She has **50 USD**.  
    **Question**: How many CAD will she get?

28. **Jade’s Lightning Observation**  
    Jade sees lightning and hears thunder **5 seconds** later. Sound travels about **340 m/s**.  
    **Question**: How far away was the lightning?

29. **Arthur’s Laptop Battery**  
    Arthur’s laptop drains at **10%** per hour when streaming video. Starting from **100%**,  
    **Question**: How many hours until the battery is fully drained?

30. **Penelope’s String Repetition**  
    Penelope wants to print her favorite movie title **3 times** in a row (e.g., \"FrozenFrozenFrozen\").  
    **Task**: Show how she might concatenate that string.
### B Group

# 5 Absurd Multi-Component Exercises

These scenarios combine multiple data types, arithmetic, and logic with a dash of humor.

---

## 1. Bruno’s Bizarre Burrito Bar

**Scenario**  
Bruno runs a late-night burrito bar catering to hungry retired zombies (yes, retired zombies). Not sure, if they are just elderly zombies or zombies that used to be zombies  ¯\_(ツ)_/¯
1. **Zombie Count**  
   - Prompt for how many zombies showed up.  
   - Each zombie orders 2 burritos on average.
2. **Burrito Calculation**  
   - Burritos cost $3.53412356 each.  
   - Calculate the total burrito income.
3. **Brain Sauce Upsell**  
   - 40% of zombies buy “brain sauce” for an extra $1.23.  
   - Calculate how many sauces were sold and the extra income.
4. **Nightly Expenses**  
   - Staff salaries = $200  
   - Special zombie-cleanup = $100  
5. **Survival Check**  
   - If more than 30 zombies appeared, print a warning about potential zombification hazard.  
   - Otherwise, note that Bruno survived another night.

**Key Points**  
- Floating-point math for burrito and sauce costs.  
- Integer logic for zombie count.  
- Condition/boolean for the “zombification hazard” warning.

---

## 2. Gretta’s Goblin Grooming Salon

**Scenario**  
Gretta runs a salon for goblins who love looking fancy:
1. **Goblin Haircuts**  
   - Each goblin demands a stylish haircut costing $15.  
   - Ask how many goblins visited.  
   - Calculate haircut revenue.
2. **Ear Wax Waxing**  
   - 50% of those goblins also get their ears waxed for $5.  
   - Calculate additional revenue.
3. **Potion Problem**  
   - A rogue goblin steals a magical styling potion worth $30 if the number of goblins is more than 10.  
   - If that happens, subtract $30 from revenue.
4. **Hag’s Tax**  
   - There’s a local “Hag’s Tax” of 10% on the total revenue.  
   - Calculate the tax amount and final net revenue.
5. **Salon Rating**  
   - If final net revenue is above $200, print “Gretta’s Goblin Grooming is thriving!”  
   - Otherwise, print “Needs more goblins... or less theft.”

**Key Points**  
- Use conditional logic for potion theft.  
- Calculate percentages for the tax.  
- Multiple arithmetic steps for combined services.

---

## 3. Captain Carl’s Crooked Cruise

**Scenario**  
Captain Carl runs a pirate cruise that occasionally “borrows” cargo along the way:
1. **Passenger Manifest**  
   - Prompt for how many passengers are on board.  
   - Each passenger pays $120 for the trip.
2. **Port Fees**  
   - Every time the ship docks (3 stops total), Carl pays $50 in docking fees.  
   - Subtract these fees from passenger revenue.
3. **“Found” Treasure**  
   - If there are more than 50 passengers, the crew manages to “find” some treasure worth $500.  
   - Add that to the total.
4. **Island Tiki Bar**  
   - The crew spends $2.50 per passenger at the bar.  
   - Subtract this total from the final revenue.
5. **Mutiny Check**  
   - If final revenue is below $1000, print “The crew is restless... potential mutiny!”  
   - Otherwise, print “All is well on the high seas!”

**Key Points**  
- Multiple revenue additions and subtractions.  
- Condition to determine if treasure is added.  
- Another condition for mutiny check.

---

## 4. Lady Lydia’s Llama Drama

**Scenario**  
Lady Lydia has a llama farm that hosts an annual llama race:
1. **Race Entry**  
   - Each racer pays $25 to enter a llama in the race.  
   - Ask how many llamas are racing.  
   - Calculate race-entry income.
2. **Llama Food**  
   - Each llama devours $5 worth of fancy feed.  
   - Subtract the total cost of feed from the income.
3. **Prize Pool**  
   - 30% of the remaining income is set aside as the “Champion’s Prize.”  
   - Subtract this from the total to see how much Lydia keeps.
4. **Spit Incidents**  
   - If there are more than 10 llamas, you have at least one “llama spit incident.”  
   - Print a warning about the cleanup cost, which is $20. Subtract that from Lydia’s share.
5. **Profit vs. Loss**  
   - If Lydia’s final share is more than $100, print “Llamas made me rich today!”  
   - Otherwise, print “Those llamas just ate my profits—literally.”

**Key Points**  
- Arithmetic for feed cost, prize pool, and final share.  
- Condition triggers spit incident cost.

---

## 5. Duke Douglas’s Dragon Disco

**Scenario**  
Duke Douglas organizes a disco night for dragons (they love to boogie):
1. **Dragon Tickets**  
   - Each dragon ticket costs $40.  
   - Prompt for how many dragons show up.
2. **Fire Insurance**  
   - Regardless of attendance, there’s a flat $200 insurance cost in case they set the disco on fire.  
   - Subtract this from ticket revenue.
3. **Snack Bar**  
   - Each dragon consumes a barrel of “Spicy Salsa” for $10, but if there are more than 20 dragons, each gets a 20% discount (because bulk salsa!).  
   - Calculate salsa cost and subtract from revenue.
4. **Dance Contest Bonus**  
   - If the final revenue (post-salsa) is over $500, sponsor money adds $100 to the event. Otherwise, no sponsor bonus.
5. **Dancefloor Burn Check**  
   - If more than 10 dragons attend, print “Dancefloor might be scorched!”  
   - Otherwise, print “Safe boogie night!”

**Key Points**  
- Combining integers (dragon count) with floating discounts.  
- Condition to apply sponsor bonus and discounts.  
- Final check for a comedic note about scorched floors.


