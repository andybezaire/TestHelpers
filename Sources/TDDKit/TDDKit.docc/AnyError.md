# ``XCTest/XCTestCase/AnyError``

An equatable identifiable error.

## Overview

This can be used to test that a service throws the error passed to one of its dependencies.
For example:

```
func test_failingFetchX_fetchY_fails() async throws {
    let error = AnyError()
    let (sut, _) = makeSUT(fetchXResult: .failure(error))
    let capturedError = await captureError(from: try await sut.fetchY())
    XCTAssertNotNil(error)
    XCTAssertEqual(capturedError as? AnyError, error)
}
```

## Topics

### Group

- <!--@START_MENU_TOKEN@-->``Symbol``<!--@END_MENU_TOKEN@-->
