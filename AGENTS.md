# Agent Guidelines

## Build & Test Commands

- **Build all**: `./gradlew build`
- **Run tests**: `./gradlew test`
- **Run single test**: `./gradlew test --tests "FullyQualifiedClassName.methodName"`
- **Run module tests**: `./gradlew <module-name>:test`
- **Run pact tests** (if required): `./gradlew verifyPacts`
- **Run locally**: `MICRONAUT_ENVIRONMENTS="local,nicelogging" ./gradlew <module-name>:run`

## Code Style

- **Imports**: Alphabetical order, then blank line, then java.util, then blank line, then static imports.
- **Annotations**: Use Lombok (@Slf4j, @RequiredArgsConstructor) for boilerplate. Use @Singleton for services, @Controller for controllers.
- **Naming**: Controllers end in `Controller`, Services end in `Service`, DTOs end in `Dto`, Exceptions end in `Exception`.
- **Dependency Injection**: Constructor injection via Lombok @RequiredArgsConstructor (final fields) where possible. If properties are required, then remove the annotation and create the constructor manually.
- **Error Handling**: Use custom exceptions extending RuntimeException.
- **Logging**: Use @Slf4j and log.error/warn/info/debug. No System.out.
- **Testing**: Use JUnit5/6 . For integration tests, use @MicronautTest and Kafka/DB test containers where appropriate.
- **Types**: Use UUID for IDs, Instant for dates, Optional for nullable returns.
- **Package Structure**: com.nwboxed.{domain}.{controller|service|repository|dto|exceptions}
