# Pull Requests for Node.js 22 Documentation Updates

This document contains the specific Pull Request content needed to update Azure Functions documentation to reflect **Node.js 22** as the latest supported version, replacing **Node.js 20** references.

## PR #1: Update Command Line Quickstart Prerequisites (JavaScript)

**Target File:** `how-to-create-function-azure-cli.md`
**URL:** https://learn.microsoft.com/en-us/azure/azure-functions/how-to-create-function-azure-cli

### Changes Required:

#### Change 1: Prerequisites Section
**Line:** ~15
**Current:**
```markdown
- [Node.js 20](https://nodejs.org/)
```

**Updated:**
```markdown
- [Node.js 22](https://nodejs.org/)
```

**Rationale:** Update prerequisite to reference the latest supported Node.js version as Node.js 20 will reach end-of-support on April 30, 2026.

---

## PR #2: Update Azure Developer CLI Quickstart Prerequisites (JavaScript & TypeScript)

**Target File:** `create-first-function-azure-developer-cli.md`
**URL:** https://learn.microsoft.com/en-us/azure/azure-functions/create-first-function-azure-developer-cli

### Changes Required:

#### Change 1: Prerequisites Section (JavaScript)
**Line:** ~20
**Current:**
```markdown
4. [Node.js 20](https://nodejs.org/)
```

**Updated:**
```markdown
4. [Node.js 22](https://nodejs.org/)
```

#### Change 2: Prerequisites Section (TypeScript)
**Line:** ~25
**Current:**
```markdown
4. [Node.js 20](https://nodejs.org/)
```

**Updated:**
```markdown
4. [Node.js 22](https://nodejs.org/)
```

**Rationale:** Ensure both JavaScript and TypeScript quickstarts reference the latest supported Node.js version.

---

## PR #3: Update Node.js Developer Guide CLI Examples (v3 & v4 Models)

**Target File:** `functions-reference-node.md`
**URL:** https://learn.microsoft.com/en-us/azure/azure-functions/functions-reference-node

### Changes Required:

#### Change 1: Azure CLI Example (Windows)
**Section:** "Setting the Node version" → "Azure CLI"
**Current:**
```azurecli
az functionapp config appsettings set  --settings WEBSITE_NODE_DEFAULT_VERSION=~20 \
 --name <FUNCTION_APP_NAME> --resource-group <RESOURCE_GROUP_NAME>
```

**Updated:**
```azurecli
az functionapp config appsettings set  --settings WEBSITE_NODE_DEFAULT_VERSION=~22 \
 --name <FUNCTION_APP_NAME> --resource-group <RESOURCE_GROUP_NAME>
```

#### Change 2: Documentation Text Update
**Current:**
```markdown
This sets the [`WEBSITE_NODE_DEFAULT_VERSION` application setting](functions-app-settings#website_node_default_version) the supported LTS version of `~22`.
```

**Updated:**
```markdown
This sets the [`WEBSITE_NODE_DEFAULT_VERSION` application setting](functions-app-settings#website_node_default_version) to the supported LTS version of `~22`.
```

#### Change 3: Azure CLI Example (Linux)
**Section:** "Setting the Node version" → "Azure CLI" (Linux section)
**Current:**
```azurecli
az functionapp config set --linux-fx-version "node|20" --name "<FUNCTION_APP_NAME>" \
 --resource-group "<RESOURCE_GROUP_NAME>"
```

**Updated:**
```azurecli
az functionapp config set --linux-fx-version "node|22" --name "<FUNCTION_APP_NAME>" \
 --resource-group "<RESOURCE_GROUP_NAME>"
```

#### Change 4: Documentation Text Update (Linux)
**Current:**
```markdown
This sets the base image of the Linux function app to Node.js version 20.
```

**Updated:**
```markdown
This sets the base image of the Linux function app to Node.js version 22.
```

**Rationale:** Update all CLI examples and explanatory text to reflect Node.js 22 as the recommended version for new deployments.

---

## PR #4: Update VS Code Quickstart Prerequisites (JavaScript & TypeScript)

**Target File:** `how-to-create-function-vs-code.md`
**URL:** https://learn.microsoft.com/en-us/azure/azure-functions/how-to-create-function-vs-code

### Changes Required:

#### Change 1: Prerequisites Section (JavaScript)
**Line:** ~15
**Current:**
```markdown
4. [Node.js 18.x](https://nodejs.org/en/about/previous-releases) or above. Use the `node --version` command to check your version.
```

**Updated:**
```markdown
4. [Node.js 22.x](https://nodejs.org/en/about/previous-releases) or above. Use the `node --version` command to check your version.
```

#### Change 2: Prerequisites Section (TypeScript)
**Line:** ~15
**Current:**
```markdown
4. [Node.js 18.x](https://nodejs.org/en/about/previous-releases) or above. Use the `node --version` command to check your version.
```

**Updated:**
```markdown
4. [Node.js 22.x](https://nodejs.org/en/about/previous-releases) or above. Use the `node --version` command to check your version.
```

**Rationale:** Update minimum version requirements to the latest supported Node.js version for optimal performance and security.

---

## PR #5: Update Containerized Functions Prerequisites

**Target Files:** 
- `functions-deploy-container.md` (JavaScript)
- `functions-deploy-container.md` (TypeScript)
- `functions-deploy-container-apps.md` (JavaScript)
- `functions-deploy-container-apps.md` (TypeScript)

### Changes Required:

#### Change 1: Prerequisites Text Update
**Current:**
```markdown
2. Install a version of [Node.js](https://nodejs.org/) that is [supported by Azure Functions](https://learn.microsoft.com/en-us/azure/azure-functions/functions-reference-node#supported-versions).
```

**Keep as-is** - This correctly references the supported versions table, which already shows the current support matrix.

**Rationale:** This reference is dynamic and correctly points to the authoritative support table, so no changes needed.

---

## PR #6: Update Durable Functions Quickstart Prerequisites

**Target File:** `durable/quickstart-js-vscode.md`
**URL:** https://learn.microsoft.com/en-us/azure/azure-functions/durable/quickstart-js-vscode

### Changes Required:

#### Change 1: Prerequisites Section
**Line:** ~20
**Current:**
```markdown
6. [Node.js](https://nodejs.org/) version 18.x+ installed.
```

**Updated:**
```markdown
6. [Node.js](https://nodejs.org/) version 22.x+ installed.
```

**Rationale:** Align Durable Functions prerequisites with the latest Node.js support for optimal functionality.

---

## Summary of Changes

### Documents Updated: 6
### Total Changes: 12

| Document | Changes | Impact |
|----------|---------|---------|
| CLI Quickstart | 1 | **High** - Core tutorial |
| AZD Quickstart | 2 | **High** - Core tutorial |
| Node.js Dev Guide | 4 | **High** - Reference docs |
| VS Code Quickstart | 2 | **High** - Core tutorial |
| Containerized Functions | 0 | Low - Dynamic reference |
| Durable Functions | 1 | Medium - Specialized tutorial |

### Next Steps for Implementation:

1. **Create GitHub Issues** for each PR to track the changes
2. **Test all CLI commands** with Node.js 22 to ensure they work correctly
3. **Update any linked resources** that might reference Node.js 20
4. **Coordinate release timing** with the Node.js 20 retirement timeline (April 30, 2026)

### Validation Checklist:

- [ ] All CLI commands tested with Node.js 22
- [ ] Links to nodejs.org still work correctly
- [ ] No other Node.js 20 references missed
- [ ] All language variations (JS/TS) updated consistently
- [ ] Portal screenshots updated if they show Node.js versions

**This systematic update ensures all customer-facing documentation reflects Node.js 22 as the recommended version while maintaining consistency across all Azure Functions documentation.**
