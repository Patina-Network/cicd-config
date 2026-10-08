# cicd-config

Shared CI/CD script configuration files (linting, formating, tsc, etc.)

# how to use

install it as a specific github SHA value like so:

```sh
bun add -D '@Patina-Network/cicd-config@github:Patina-Network/cicd-config#<full-commit-sha>'
```

Replace <full-commit-sha> with the latest commit on `main` branch.

### TSConfig: .github/scripts/tsconfig.json

```json
{
  "extends": "@Patina-Network/cicd-config/tsconfig",
  "compilerOptions": {
    "paths": {
      "@/*": ["./src/*"]
    }
  },
  "include": ["./src/**/*", "oxfmt.config.ts", "oxlint.config.ts"]
}
```

### Formatter: .github/scripts/oxfmt.config.ts

```ts
import shared from "@Patina-Network/cicd-config/oxfmt" with { type: "json" };

export default {
  ...shared,
};
```

### Linter: .github/scripts/oxlint.config.ts

```ts
import shared from "@Patina-Network/cicd-config/oxlint" with { type: "json" };

export default {
  ...shared,
};
```
