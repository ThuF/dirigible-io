---
layout: api
title: Exec
icon: fa-check
---


> ⚠ Deprecated

Version 4.x
---

[core/engines](https://thuf.github.io/dirigible-io/api/core_engines.html)

Version 3.x
---

[core/engines](https://thuf.github.io/dirigible-io/api/core_engines.html)

Version 2.x
---

{{ page.title }}
===

Exec object is used for executing a scripting service programmatically.

- Module: **platform/exec**
- Definition: [/core_api/issues/36](https://github.com/dirigiblelabs/core_api/issues/36)
- Source: [/platform/exec.js](https://github.com/dirigiblelabs/core_api/blob/master/core_api/ScriptingServices/platform/exec.js)
- Status: **beta**

Basic Usage
---

```javascript
/* globals $ */
/* eslint-env node, dirigible */

var exec = require('platform/exec');
var response = require('net/http/response');

var context = {"input_param": "input_param_value"};

// Test execution
var result = exec.test("/platform/exec_target_test.js", context);

response.println("Printing output parameter: " + result.context.output_param);

// use also exec.js(), exec.flow(), exec.job(), exec.sql(), exec.command() ...

response.flush();
response.close();
```

Definition
---

### Functions

---

Function     | Description | Returns
------------ | ----------- | --------
**js(path, context)**   | Executes the given JavaScript service by path | *the resulting context object*
**test(path, context)**   | Executes the given JavaScript test case by path | *the resulting context object*
**flow(path, context)**   | Executes the given Flow service by path | *the resulting context object*
**job(path, context)**   | Executes the given Job service by path | *the resulting context object*
**sql(path, context)**   | Executes the given SQL service by path | *the resulting context object*
**wiki(path, context)**   | Executes the given JavaScript transformer by path | *the resulting context object*
**command(path, context)**   | Executes the given shell Command service by path | *the resulting context object*



Compatibility
---

Rhino | Nashorn | V8
----- | ------- | --------
 ✅  | ✅  | ❌
