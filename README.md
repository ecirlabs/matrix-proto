# Matrix Proto

Protocol Buffer definitions for the Matrix distributed system components.

## Overview

This repository contains the Protocol Buffer definitions for the Matrix system's microservices and components. It defines the contract for inter-service communication and data structures used throughout the system.

## Components

### Agent (matrix/agent/v1)
- **Metrics**: System metrics collection and reporting
  - CPU and memory statistics
  - Custom metric support
  - Real-time metrics streaming

### Control (matrix/control/v1)
- **Node Control**: Management interface for Matrix nodes
  - Health checking
  - Version information
  - Graceful shutdown
  - Metrics retrieval

### Key-Value Store (matrix/kv/v1)
- **CRDT Service**: Conflict-free replicated data types implementation
  - Key-value operations (Get, Put, Delete)
  - Value merging
  - Snapshot management
  - Prefix scanning

### Marketplace (matrix/marketplace/v1)
- **Registry Service**: Module marketplace functionality
  - Module publishing
  - Module downloading
  - Search capabilities
  - Payment verification

## Prerequisites

- [Protocol Buffers Compiler](https://github.com/protocolbuffers/protobuf) (protoc)
- [Buf](https://buf.build/docs/installation) - Modern Protocol Buffers tooling
- Go 1.20 or later (for Go code generation)

## Getting Started

1. **Install Buf**
   ```bash
   brew install bufbuild/buf/buf   # macOS
   ```

2. **Generate Code**
   ```bash
   buf generate
   ```

3. **Lint Protos**
   ```bash
   buf lint
   ```

## Development

### Project Structure
```
.
├── matrix/
│   ├── agent/v1/          # Agent-related definitions
│   ├── common/v1/         # Shared types and utilities
│   ├── control/v1/        # Node control interface
│   ├── kv/v1/            # Key-value store operations
│   └── marketplace/v1/    # Module marketplace
├── buf.yaml              # Buf configuration
├── buf.gen.yaml          # Code generation configuration
└── buf.lock             # Dependency lock file
```

### Making Changes

1. Make changes to `.proto` files
2. Run `buf lint` to ensure compliance with best practices
3. Run `buf generate` to update generated code
4. Commit changes and create a pull request

## Best Practices

- Use specific response types for each RPC method
- Follow consistent naming conventions
- Include comprehensive field documentation
- Maintain backward compatibility
- Use appropriate field numbers and types

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us. We welcome contributions and value the input of our community!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.