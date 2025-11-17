# Closure Understanding Questions - Week 1

Use these questions to test your understanding after learning about closures. Try to answer them without looking at notes, then verify your understanding.

## Fundamental Concepts

### Basic Understanding
1. **What is a closure?** (Define it in your own words)
2. **What are the three requirements for a closure to exist?**
3. **What is a "free variable" in the context of closures?**
4. **What is the "enclosing scope" and how does it relate to closures?**
5. **How does a closure differ from a regular function?**

### Mechanics & Behavior
6. **When is the closure created - at function definition time or execution time?**
7. **What happens to variables in the enclosing scope after the outer function returns?**
8. **Can closures modify variables from the enclosing scope? If so, what keyword is needed?**
9. **What happens if you try to modify a variable from the enclosing scope without using `nonlocal`?**
10. **How do closures relate to the LEGB (Local, Enclosing, Global, Built-in) rule?**

## Practical Understanding

### Code Analysis
11. **Given this code, explain what happens:**
    ```python
    def outer(x):
        def inner(y):
            return x + y
        return inner
    
    add_five = outer(5)
    result = add_five(3)
    # What is result? Why?
    ```

12. **What will this code output and why?**
    ```python
    def create_multipliers():
        return [lambda x: i * x for i in range(5)]
    
    multipliers = create_multipliers()
    print([m(2) for m in multipliers])
    ```

13. **How would you fix the above code to work correctly?**

14. **What's the difference between these two approaches?**
    ```python
    # Approach 1: Using closure
    def make_counter():
        count = 0
        def counter():
            nonlocal count
            count += 1
            return count
        return counter
    
    # Approach 2: Using class
    class Counter:
        def __init__(self):
            self.count = 0
        def __call__(self):
            self.count += 1
            return self.count
    ```

### Use Cases
15. **When would you choose a closure over a class?**
16. **When would you choose a class over a closure?**
17. **What are 3-5 practical use cases for closures?**
18. **How are closures used in decorators?**
19. **How can closures be used for data privacy/encapsulation?**

## Advanced Concepts

### Edge Cases & Gotchas
20. **What happens if multiple closures share the same enclosing scope variable?**
21. **Can closures access variables from multiple levels of nesting?**
22. **What happens if you create multiple closures from the same outer function? Do they share state?**
23. **How do closures interact with loops? (Common Python gotcha)**
24. **What's the difference between `global` and `nonlocal` keywords?**

### Implementation Details
25. **How can you inspect a closure's free variables? (Hint: `__closure__` attribute)**
26. **What does `cell` mean in the context of closures?**
27. **How does Python store closure variables internally?**
28. **Can you modify a closure's free variables from outside the closure?**

## Comparison & Design

### Closure vs Alternatives
29. **Compare closures with:**
    - Classes with `__call__` method
    - Functions with default arguments
    - Global variables
    - `functools.partial`

30. **What are the memory implications of closures?**
31. **Can closures cause memory leaks? If so, how?**

### Design Decisions
32. **When designing a counter, validator, or callback system, how do you decide between closures and classes?**
33. **How do closures enable functional programming patterns in Python?**
34. **How do closures relate to JavaScript closures? (If you know JS)**

## Practical Application

### Problem Solving
35. **How would you implement a memoization function using closures?**
36. **How would you create a function factory that generates validator functions?**
37. **How would you implement an event listener system using closures?**
38. **How can closures be used to create configuration-preserving functions?**

### Debugging
39. **If a closure isn't working as expected, what are common issues to check?**
40. **How do you debug closure-related issues? What tools help?**

## Real-World Understanding

41. **Where have you seen closures used in real Python libraries or frameworks?**
42. **How do closures enable callback patterns?**
43. **How are closures used in async/await patterns? (Preview for later weeks)**
44. **Can closures be pickled/serialized? Why or why not?**

## Self-Assessment Checklist

After learning, you should be able to:
- [ ] Explain closures to someone else without using jargon
- [ ] Write a closure from scratch without looking at examples
- [ ] Identify when a closure would be better than a class
- [ ] Debug closure-related bugs
- [ ] Use `nonlocal` correctly
- [ ] Understand the common loop-variable closure gotcha
- [ ] Implement practical use cases (counter, memoization, validators)
- [ ] Explain how closures relate to scope and namespaces

---

## Answer Key Hints

- Review your notes if you can't answer 80%+ of these
- Try implementing the code examples yourself
- Experiment with `__closure__` attribute to see closure internals
- Compare closure implementations with class-based alternatives
- Practice by building the mini exercises from the syllabus

