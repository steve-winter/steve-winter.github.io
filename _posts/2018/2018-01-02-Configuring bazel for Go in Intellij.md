---
layout: post
title: "Configuring Intellij Bazel plugin to use Go on existing Projects"
comments: true
description: "Configuring Intellij Bazel plugin to use Go on existing Projects"
keywords: "go bazel intellij"
author: Steve Winter
---
I have been scratching my head on this one for a couple of hours so sharing the steps here;

1. Install bazel plugin

2. Set executable home in 'Other Settings' to Bazel installation (for me this was in /usr/local/Cellar/bazel)

3. To enable Bazel with Go in Intellij (for existing projects), update your .idea/workspace.xml to use;

```
<component name="BlazeImportSettings">
    <option name="buildSystem" value="Bazel" />
    <option name="projectDataDirectory" value="$PROJECT_DIR$" />
    <option name="projectName" value="{{project-name}}" />
    <option name="projectViewFile" value="$PROJECT_DIR$/.bazelproject" />
    <option name="workspaceRoot" value="$PROJECT_DIR$" />
  </component>
```
  
  Above the 'changelistmanager' component.
  
  4. This possibly also requires your .bazelproject be configured. Seems to be limited documentation on this file but it is the file that tells the bazel plugin what to 'see' in your project.
  
  ```
  directories:
  .

targets:
  //...:all

additional_languages:
  # Uncomment any additional languages you want supported
  # android
  # dart
  go
  # javascript
  # python
  # scala
  # typescript
```
