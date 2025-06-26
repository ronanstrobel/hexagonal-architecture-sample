# hexagonal-architecture-sample

## Overview
This project serves as a template to illustrate hexagonal architecture from my perspective. It aims to provide a clean and organized structure that separates concerns across domain, application, and adapter layers, following the principles of the Ports and Adapters pattern.

## Architecture
Hexagonal architecture divides the application into three main layers:

1. **Domain (business logic)**
2. **Application (ports == interfaces)**
3. **Adapters (Implementations)**

### Domain
The domain layer contains the business logic and domain entities. It is independent of any external systems or frameworks.

### Application
Here we'll find the "ports" wich is the interfaces that the domain layer uses to interact with the outside world. There are two types of ports:
- **Driving Ports**: Interfaces that define how the application can be used (e.g., service interfaces).
- **Driven Ports**: Interfaces that define how the application interacts with external systems (e.g., repository interfaces).

### Adapters (Implementations)
Adapters implement the ports and provide the actual interaction with external systems. There are two types of adapters:
- **Driven Adapters**: Implement outbound ports to interact with external systems (e.g., databases, message brokers).
- **Driving Adapters**: Implement inbound ports to expose the application to the outside world (e.g., REST controllers, message listeners).

## Project Structure
The project is organized as follows:

```
CottonField.sln
├── src
│   ├── Domain
│   │
│   ├── Application
│   │   └── Ports
│   │       ├── Driven
│   │       │
│   │       └── Driving
│   │   
│   ├── Adapters
│   │   ├── Driven
│   │   │   └── Persistence
│   │   └── Driving
│   │       └── Api
└── tests
     ├── Integration
     │
     └── Unit
```

![hexagonal_arch](https://github.com/user-attachments/assets/0fa207fb-4be0-4ada-ae52-e8f6ce104bef)