# JavaScript tests with expected output

Tests in test/message pass if the output matches the expected output. Message
tests are particularly useful when checking for exact error messages.

Tests and their expected output must have the same filename, with the `.js` and
`.out` extension.

```
foo.js
foo.out
```

**All tests must end with an exception**. The test runner does not
handle output from multiple runs, e.g.,  `--stress-opt`. Without an exception,
the output will be generated several times and the comparison will fail.

You can use a regex in the expected output. Instead of the exact
path. use
 ```
*%(basename)s:7: SyntaxError: Detected cycle while resolving name 'a'
```
Empty lines are ignored in the comparison, but whitespaces are not.

Exact details of the test runner are in [testcfg.py](testcfg.py).
