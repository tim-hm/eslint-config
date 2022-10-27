# My personal eslint config

## Usage

1. Add repo as dependency in `package.json` (I'm using yarn link protocol below):

    ```jsonc
    {
        "devDependencies": {
            "@tim-hm/eslint-config": "link:../eslint-config"
        }
    }
    ```

2. Run `yarn install`
3. Setup your eslint config:

    ```js
    module.exports = {
        root: true,
        extends: ["@tim-hm/eslint-config"],
        parserOptions: {
            project: "./tsconfig.eslint.json",
        }
    }
    ```

4. If desired, modify the import order for your projects namespace:

    ```js
    {
        settings: {
            "import/internal-regex": "^@tim-hm"
        },
        rules: {
            "import/order": [
            "warn",
            {
                "newlines-between": "always",
                alphabetize: {
                order: "asc"
                },
                groups: ["builtin", "external", "internal", "parent", "sibling", "index"]
            }
            ]
        }
    }
    ```

5. Restart your workspace and verify linting works as expected 🥳 🚀
