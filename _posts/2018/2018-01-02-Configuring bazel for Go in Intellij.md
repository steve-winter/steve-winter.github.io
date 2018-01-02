---
layout: post
title: "Configuring Intellij Bazel plugin to use Go on existing Projects"
comments: true
description: "Configuring Intellij Bazel plugin to use Go on existing Projects"
keywords: "go bazel intellij"
author: Steve Winter
---

Install bazel plugin

To configure Bazel with Go in Intellij (for existing projects), update your .idea/workspace.xml to use;

```<component name="BlazeImportSettings">
    <option name="buildSystem" value="Bazel" />
    <option name="projectDataDirectory" value="$PROJECT_DIR$" />
    <option name="projectName" value="{{project-name}}" />
    <option name="projectViewFile" value="$PROJECT_DIR$/.bazelproject" />
    <option name="workspaceRoot" value="$PROJECT_DIR$" />
  </component>
  ```
  
  Above the 'changelistmanager' component.
