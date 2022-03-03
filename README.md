Roboswag
========

- [Introduction](#introduction)
- [Usage](#usage)
- [Limitations](#limitations)

Introduction <a name="introduction"></a>
------------

:robot: Roboswag is a tool that automatically generates Python libraries out of your Swagger (OpenAPI specification 
file). These libraries can be used to create tests with various payload content and its validation. It also supports 
response validation against schema and verification of different status codes.

> **Note**
> 
> The tool is in the ***Alpha*** state, which means it may be unstable and should be used at your own risk. Some 
> features may be broken and there are still many things to be developed. Happy testing!

The OpenAPI Specification (OAS) defines a standard, language-agnostic interface to RESTful APIs.
Click [here for v3 documentation](https://swagger.io/specification/) and
[here for v2 documentation](https://swagger.io/specification/v2).

> Hosted on [GitHub](https://github.com/bhirsz/robotframework-openapi). :medal_military:

Usage <a name="usage"></a>
-----

First, you need to install Roboswag. The PyPI package is not yet released, so if you want to try it out 
you need to clone the repository and install the tool from source code.

After you have the repository locally, go inside the main directory `robotframework-roboswag` and type:

```commandline
pip install .
```

Roboswag can be easily run from command line. To check if it's installed, run this to see the current version:

```commandline
roboswag -v
```

To execute Roboswag with its full capabilities, run it with provided path to the Swagger (OpenAPI specification) file:

```commandline
roboswag -s <path_to_swagger>
```

Successful execution should result in printing the information about generated files and a whole new directory (named 
by the `"title"` from your Swagger file) consisting of:
- `endpoints` directory with files representing each `tag` as a class with methods representing its endpoints,
- `models` directory with API models represented as Python classes,
- `schemas` directory with every possible schema from your API as JSON file used for validating payload and responses. 

Now you can just create a test file, import desired endpoint and start automating the testing!

Limitations <a name="limitations"></a>
-----------

The tool is already able to generate libraries but...
- Not all fields from the swagger specification may be supported. This means that a specific file may break the tool 
  and flood the terminal with stack trace
- Also, the support for Swagger V3 is not yet implemented
- Authorization to access the API is not yet fully covered
- There is not much to be configured here - it works always the same
- 
- There is no real documentation apart from this file
- There are nearly no tests assuring this tool works correctly

Please be forgiving and submit an issue, if you struggle with something or just contact us on our
[Slack channel](https://robotframework.slack.com/archives/C035KMZ2FGA). It's more than welcome also to support us by 
code contribution! :keyboard:
