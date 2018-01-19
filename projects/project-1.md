---
layout: project
type: project
image: images/scheme.png
title: Shaka Scheme - Build a Scheme Interpreter
permalink: projects/ShakaScheme
# All dates must be YYYY-MM-DD format!
date: 2017-01-09
labels:
  - C++
  - Scheme
  - Google Test
  - GitHub
summary: A Scheme interpreter constructed in C++ that implements the Scheme programming language standard that is defined in the Revised7 Report on the Algorithmic Language Scheme (R7RS).
---

<div class="ui small rounded images">
  <img class="ui image" src="../images/scheme.png">
</div>

Shaka Scheme is a Scheme interpreter constructed in C++ that implements the Scheme programming language standard that is defined in the Revised7 Report on the Algorithmic Language Scheme (R7RS).

Here is some code:

```js
// (+ z1 ...)
Args add_numbers(Args args) {

  if (args[0]->get_type() != Data::Type::NUMBER) {
    throw TypeException(117,
                        "STDPROC: Incorrect argument type to Native "
                            "Procedure: "
                            "+");
  }

  shaka::Number result = shaka::Number(0);
  for (std::size_t i = 0; i < args.size(); i++) {
    result = result + args[i]->get<shaka::Number>();
  }

  Args result_vector;
  NodePtr result_value = create_node(result);
  result_vector.push_back(result_value);

  return result_vector;
}
```

Visit the [Shaka Scheme GitHub](https://github.com/uhmanoa-transpiler-project/shaka-scheme).



