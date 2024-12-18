# CUID2

Go implementation of [CUID2](https://github.com/paralleldrive/cuid2) - Collision-resistant ids optimized for horizontal scaling and performance.

## Installation
```bash
go get github.com/PatrickChoDev/cuid2
```

## Usage
```go
import "github.com/PatrickChoDev/cuid2"

// Generate a CUID with default settings
id := cuid2.Generate() // Example: "tz4a98xxat96"

// Initialize with custom options
generator, err := cuid2.Init(
    cuid2.WithLength(10),                 // Custom length (2-32)
    cuid2.WithRandomFunc(rand.Float64),   // Custom random function
    cuid2.WithFingerprint("myapp"),       // Custom fingerprint
)
if err != nil {
    // Handle error
}
id = generator() // Generate using custom settings

// Validate a CUID
valid := cuid2.IsCuid("tz4a98xxat96") // Returns true/false
```

## Features
- Thread-safe ID generation
- Configurable length (2-32 characters)
- Customizable random function
- System fingerprinting for distributed systems
- Validation function
- Zero external dependencies (except crypto/sha3)

## License
MIT License

