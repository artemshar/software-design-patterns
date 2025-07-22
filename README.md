# Software Design Patterns
Top [X] Software Design Patterns

### 1. Repository Pattern
- **Purpose**: Abstract data access (as discussed above).
- **Common in**: Clean architecture, DDD, services with persistence layers (Node.js, Spring, Laravel).
- **Benefits**:
    - Decouples business logic from data access.
    - Easier to swap database or mock data in tests.
    - Encourages cleaner, testable code.
- **Diagram**: Application (Use Cases) > Domain Layer (Business Logic & Models) > Repository Layer (e.g., UserRepository) > Data Access Layer (ORM, SQL, API, Files...) > Database
- **Example**:
```ts
// UserRepository.ts
class UserRepository {
  constructor(private orm: PrismaClient) {}

  async findById(id: number): Promise<User | null> {
    return this.orm.user.findUnique({ where: { id } });
  }

  async save(user: User): Promise<void> {
    await this.orm.user.update({
      where: { id: user.id },
      data: user,
    });
  }
}
```
In this case:
- Prisma (ORM) is a tool used inside the repository implementation.
- The repository defines your own app-level interface for data operations.

### 2. Factory Pattern
- **Purpose**: Centralizes object creation logic.
- **Defenition**: Factory Method is a creational design pattern that provides an interface for creating objects in a superclass, but allows subclasses to alter the type of objects that will be created.
- **Example**: Creating service instances based on configuration or environment.
- **Links**:
   - https://refactoring.guru/design-patterns/factory-method

### 3. Strategy Pattern
@todo

### 4. Middleware Pattern
@todo

### 5. Dependency Injection (DI)
@todo

### 6. Observer Pattern
@todo

### 7. Decorator Pattern
@todo

### 8. Adapter Pattern
@todo

### 9. Builder Pattern
@todo

### 10. Singleton Pattern
@todo

### 11. MVC (Model-View-Controller)
@todo

### 12. MVVM (Model-View-ViewModel)
@todo

### 13. Clean Architecture / Hexagonal Architecture
@todo

### 14. CQRS (Command Query Responsibility Segregation) 
@todo

### 15. Event Sourcing — useful in high-integrity domains, like finance
@todo


