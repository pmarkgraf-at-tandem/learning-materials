# Coding Best Practices

## Topics

Local variable declared but not subsequently accessed — may indicate dead code or logic errors. Code Cleanliness & Maintenance
Local variable declared but not subsequently referenced — similar to 550, useful for cleanup. Code Cleanliness & Maintenance
Highest operation lacks side effects — often a sign of a logic bug. Correctness & Logic Bugs
Boolean argument to arithmetic/bitwise operator — likely a logic error. Correctness & Logic Bugs
Explicitly taking address of function — usually redundant and potentially misleading. API Misuse & Redundancy
Signed-unsigned mix with relational — common source of subtle bugs. Correctness & Logic Bugs
Shift left of signed quantity — undefined behavior risk. Correctness & Logic Bugs
Shift right of signed quantity — can lead to implementation-defined behavior. Correctness & Logic Bugs
Loss of sign in assignment — can cause unexpected behavior. Sign & Type Safety
Loss of sign in promotion — subtle and hard to detect. Sign & Type Safety
Implicit conversion from unsigned to signed — can cause overflow or logic errors. Sign & Type Safety
External symbol was defined but not referenced — useful for dead code detection. Code Cleanliness & Maintenance
Named function parameter not referenced — helps clean up unused parameters. Code Cleanliness & Maintenance
Unexpected lack of indentation — useful for enforcing style consistency. Style & Readability
Extraneous comma at end of enumerator list — may be disallowed in some compilers. Style & Readability
External variable not explicitly initialized — can lead to undefined behavior. Initialization
Boolean used as argument integer to function — can be misleading. Correctness & Logic Bugs
Boolean argument(s) to equality-operator — often a logic mistake. Correctness & Logic Bugs
Enum constant not used within default switch — helps ensure completeness. Code Cleanliness & Maintenance
Static variable could be made const — improves immutability and optimization. Const-Correctness
Parameter could be pointer to const — improves safety and clarity. Const-Correctness
implicit conversion (context) from type to type Sign & Type Safety

### Casting

* Only perform type conversions “at the edges”
  * Convert from raw to internally used type immediately after input (receipt at the driver -- although not in the driver)
  * Convert from internal types to network types at the packet creation point
* Prefer the processors native precision
* Only use unsigned types for register access and memory address manipulation
* Only perform unsigned arithmetic for memory address manipulation
* Limit manual memory address manipulation to compile-time constants

* Use the display unit for alarm generation
  * Creating each unit displayed at the input conversion point and carrying all units through
  * Carry data as structures data with all types contained
* Prefer data in named structures over primitive types (code smell: Primitive Obsession)
  * Allows compile-time type checking

### Arithmetic correctness / type safety

* Loss of precision
* Unchecked arithmetic overflow
* Unchecked arithmetic underflow
*

### Flow control

* Priority inversion
* Null pointers
* Function pointers

### Unintended effects

* Const correctness
* Array overflow/underflow

### Resources

* Shared ownership interactions

### Logic Issues / Error handling

* Ignored return value (Lint 534)
  * Ignoring return value of function — can hide critical failures. Correctness & Logic Bugs

### Style

* Hard to understand code
  * Code review issues

### Not now

* Primitive obsession (conversion risks)
  * Unchecked type mismatch

## Why Code Style Matters

Consistent code style is essential for creating readable, maintainable, and reliable software. Readable code allows team members to quickly understand logic, spot errors, and suggest improvements during code reviews. Well structured code accelerates the speed of change, as developers can confidently modify code without spending excessive time deciphering its intent. Ultimately, good code style leads to higher quality software and more efficient collaboration.

## Work here

### Single Ownership of Hardware Resources

**Best Practice:**
Each hardware resource (e.g., peripheral, bus, memory region) should be owned and controlled by no more than one software entity (such as a driver, module, or task) at any given time.

**Risks and Potential Negative Outcomes of Multiple Ownership:**

* Race conditions and unpredictable behavior due to concurrent access.
* Data corruption or loss if two entities attempt to configure or use the resource simultaneously.
* Deadlocks or system hangs if ownership is not clearly defined or transferred.
* Increased difficulty in debugging and maintaining the system.
* Security vulnerabilities if unauthorized code can access or control the resource.
* Violation of timing constraints, especially in real-time systems.

**Mechanisms for Providing Service to Multiple Software Entities:**

* Implement a single owner (e.g., a driver or manager module) that arbitrates all access to the hardware resource.
* Use a service or API layer: The owner exposes well-defined interfaces (functions, message queues, or events) for other software entities to request services.
* Queue or buffer requests from multiple clients, servicing them in a controlled, serialized manner.
* Use callbacks, events, or notification mechanisms to inform clients when their request has been completed.
* Employ resource locking or mutual exclusion (mutexes, semaphores) within the owner to ensure safe access if needed.
* Clearly document ownership and access patterns in code and design documents.

By following this practice, systems become more robust, maintainable, and predictable, especially in complex or safety-critical embedded environments.

## end
