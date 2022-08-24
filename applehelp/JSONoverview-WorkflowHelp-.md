# "JSON overview - Workflow Help"

*23-08-2022 22:31* 

> JSON is a popular data-interchange format used by APIs (application programming interfaces). JSON lets you bundle a large amount of data into one chunk of text and then send it along to another service. All of the data values are given names, referred to as keys, and are combined with special characters like colons (:) and braces () to form data objects.
![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## JSON overview

*JSON* is a popular data-interchange format used by [APIs](https://help.apple.com/workflow/#/apd2e30c9d45) (application programming interfaces). JSON lets you bundle a large amount of data into one chunk of text and then send it along to another service. All of the data values are given names, referred to as *keys*, and are combined with special characters like colons (`:`) and braces (`{`and `}`) to form *data objects*.

In JSON, your values are structured into two types of data objects: dictionaries and lists.

A *dictionary* is a collection of values that each have a unique key, together called *key/value pairs*. In JSON, they look like `{key1: value1, key2: value2, key3: value3}` (and so forth).

A *list* is simply an ordered collection of values. In JSON, they look like `[value1, value2, value3]`, and so on.

In both cases, you can set the values as text, numbers, booleans (true or false), dictionaries, and lists.

JSON allows you to nest dictionary and list structures however you want. For example, you can nest a dictionary within a dictionary or nest a list within a dictionary. This allows you to model almost any structure of data, basic or complex, making JSON a powerful yet simple way to organize values as data objects.

For example, you can represent a person using a dictionary like:

`{"first_name: "John", "last_name": "Appleseed", "age": 9}`

Or, if you want a list of people, you can put the people dictionaries in a list like:

`[{"first_name: "John", "last_name": "Appleseed", "age": 9},``{"first_name: "Kate", "last_name": "Bell", "age": 10},``{"first_name: "Anna", "last_name": "Haro", "age": 11}]`

*Note:* For more information about the semantics of JSON, visit [http://www.json.org](http://www.json.org/).

© 2018 Apple Inc. All rights reserved.
***

==**1672**== Words

- **[JSON overview - Workflow Help](https://help.apple.com/workflow/#/apd0f2e057df)**