---
id: command-name
title: /command-name
sidebar_label: Template
description: A short summary of what this command does.
tags:
  - Command
  - CategoryName
---

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

# /command-name

**Category:** Utility  
**Permissions Required:** None  
**Slash Command:** Yes  
**Context Menu:** No

---

## Description

Explain what this command does and when it should be used.  
Keep it short and focused on what the command helps users achieve.

Example:  
This command displays detailed information about a specified user, including their join date, roles, and permissions.

---

## Usage

```bash
  /command-name [optional-arg] <required-arg>
```

---

## Parameters

| Name     | Type   | Required | Description                                  | Example    |
| -------- | ------ | -------- | -------------------------------------------- | ---------- |
| `user`   | User   | Yes      | The user to fetch information for.           | `@Raspy`   |
| `format` | String | No       | Output format, either `short` or `detailed`. | `detailed` |

---

## Examples

<Tabs>
  <TabItem value="example1" label="Basic Usage">

```bash
/userinfo @Raspy
```

**Bot Response:**

```
Username: Raspy
Joined: Jan 1, 2023
Roles: Admin, Developer
```

  </TabItem>

  <TabItem value="example2" label="With Parameters">

```bash
/userinfo @Raspy format:detailed
```

**Bot Response:**

```
Detailed user information with additional metadata.
```

  </TabItem>
</Tabs>

---

## Permissions

| Type | Required | Notes                                  |
| ---- | -------- | -------------------------------------- |
| User | No       | No specific permission required.       |
| Bot  | Yes      | Requires the `Embed Links` permission. |

---

## Admonitions

:::note[Notes]
Notes
:::
:::warning[Warning]
Warning
:::
:::danger[Danger]
Danger
:::

---

## Related Commands

* [`/serverinfo`](./command-name)
* [`/avatar`](./command-name)

---

## Developer Notes

* Added in version: `v2.3.0`
* Implementation file: `commands/userinfo.js`
* API dependencies: Discord REST `/users/{id}`