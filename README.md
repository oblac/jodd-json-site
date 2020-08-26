# Jodd JSON

JavaScript Object Notation \(aka [JSON](http://json.org/)\) is a very popular lightweight data-interchange format. **Jodd JSON** is a lightweight library for \(de\)serializing Java objects into and from JSON.

Before you say: "_Yet another one?_", please check what makes **Jodd JSON** different. The power of the library is its control over the process of serialization and parsing; ease of use and great performances.

### Quick Start <a id="quick-start"></a>

Let's see how it looks working with serialization:

```java
    Book book = new Book();
    book.setName("Jodd in Action);
    book.setYear(2018);
    book.setAuthors(List.of(new Author("Igor")));

    String json = JsonSerializer.create()
            .include("authors")
            .serialize(book);
```

The resulting JSON may look like this:

```javascript
    {
        "name" : "Jodd In Action",
        "year" : 2018,
        "authors" : [
            { "firstName" : "Igor" }
        ]
    }
```

Parse the JSON back to Java:

```java
    Book book2 = new JsonParser()
            .parse(json, Book.class);
```

Pretty simple, right? But don't get blinded by the simplicity, **Jodd JSON** is pretty powerful. Did I mention it is one of the fastest JSON frameworks out there?

### Main features

* simple syntax and fluent interface,
* lazy parser that is super fast,
* annotations for better conversion control,
* convenient `JSONObject` and `JSONArray` classes,
* powerful exclusion and inclusion rules,
* serializer definition for types,
* the only library that can handle any number size,
* pretty formatting of the JSON output,
* loose, more forgiving, parsing mode,
* ways to address the keys and values of the Maps
* flexible fine-tuning,
* and more…

