## Kotlin Flow

### Projects

1. **CacheApiCall:** the [CacheApiCall](./src/main/kotlin/CacheApiCall.kt) demonstrate the scenario where we need to cache an api call locally.

### Learnings Outcome

- **Create Kotlin Flow:** create kotlin flow using `flow { }`. inside flow block `emit()` must be called to produce the result otherwise the value wil not be collected.
only on adding `collect { }` block the flow will run. that is why flow is called **cold**. collect is a suspend function so must be called inside a coroutine like `runBlocking {}` or `launch {}` etc.
- **Flow Intermediate:** sometimes the flow produces result need to be transformed. the intermediates help in this case. `transform {}` is one of them. in side transform we need to `emit` the transformed result.
transform returns a new flow. add collect to collect the transformed result