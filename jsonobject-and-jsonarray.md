---
description: Generic JSON objects
---

# JsonObject and JsonArray

Default object types of parsed JSON inputs are `Map` and `List`. While this can be enough, sometimes you want a more developer-friendly way to navigate the returned object, especially nested values - you keep casting all over the code. **Jodd JSON** comes with two nice classes: `JsonObject` and `JsonArray` that can be used instead of defaults. They are quite convenient to work with JSON structure.

Here is an example of the usage:

```java
JsonObject jo = JsonParser.create().parseAsJsonObject("{ ... }");

Integer i = jo.getInteger("key");
JsonObject child = jo.getJsonObject("child");
JsonArray ja = jo.getJsonArray("arr");
Double d = ja.getDouble(ndx);
```

### Serialization

Both `JsonObject` and `JsonArray` may be used for serialization, too. You can use them to construct the JSON structure and then serialize it as usual.

### Binary values

`JsonObject` is able to read and write binaries i.e. `byte[]`. Of course, JSON format does not support the binary types, hence the input array is encoded to Base64. Similarly,the  Base64 field can be read as binary and convert into the `byte[]`.

