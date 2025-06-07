### Note for nvm Users

If you are using [nvm (Node Version Manager)](https://github.com/nvm-sh/nvm), you need to create a wrapper script.

Create a new file at `/usr/local/bin/npx-for-claude` with the following content:

```bash
#!/usr/bin/env bash

export PATH="/Users/YOUR-USERNAME/.nvm/versions/node/YOUR-NODE-VERSION/bin:$PATH"
exec npx "$@"
```

Make the wrapper script executable:

```bash
chmod +x /usr/local/bin/npx-for-claude
```
