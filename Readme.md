Rundeck JSON plugin
=======

version: 1.1

This is an example "Resource Format Plugin" for [RunDeck](http://rundeck.org).

It provides a parser and generator for resources in JSON format, using the
Google GSON library.

Dependencies:
-----

Copy the latest rundeck-core jar to the `build-dependencies` directory.

Build
-----

./gradlew

Artifact
-----

    build/libs/rundeck-json-plugin-1.1.jar

Install
-----

Copy the `rundeck-json-plugin-1.1.jar` to your `$RDECK_BASE/libext` directory.

You can now use the `resourcejson` format when configuring Resource Model Source
plugins, or exporting resources via the API.

For example, add a new File resource model source with a ".json" extension, or
a new URL resource model source for a URL that returns json.

When accessing resources via the API, use `?format=resourcejson` to retrieve the resources in this format.

Format
-----

The JSON format supported for nodes is:

~~~ {.json}
{
  "nodes": {
    "Venkman.local": {
      "tags": ["a","b","c"],
      "attributes": {
        "osFamily": "unix",
        "username": "greg",
        "osVersion": "10.7.1",
        "osArch": "x86_64",
        "description": "Rundeck server node",
        "hostname": "Venkman.local",
        "osName": "Mac OS X"
      }
    },
    "centos5": {
      "tags": ["d","b","c"],
      "attributes": {
        "osFamily": "unix",
        "username": "greg",
        "osVersion": "10.7.1",
        "osArch": "x86_64",
        "description": "Test node",
        "hostname": "centos5",
        "osName": "Mac OS X",
        "monkey":"banana",
        "eats-cheese":"yes"
      }
    }
  }
}
~~~

More Info
-----

More info about rundeck plugins:

* [Resource Format plugin usage](http://rundeck.org/docs/plugins-user-guide/resource-model-source-plugins.html#resource-model-document-formats)
* [Resource Format plugin development](http://rundeck.org/docs/developer/model-format-parser-and-generator-plugin.html)
* [Rundeck API - Resources for a project](http://rundeck.org/docs/api/index.html#updating-and-listing-resources-for-a-project)
