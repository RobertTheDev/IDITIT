1. ENV - Create .env file and optionally can create a .env.development and a .env.production
2. ESLINT - Should be installed when selecting yes in the CLI
3. PRETTIER -

yarn add --dev eslint-config-prettier prettier prettier-plugin-css-order prettier-plugin-organize-imports prettier-plugin-tailwindcss

node --eval "fs.writeFileSync('.prettierignore','# Ignore artifacts:\nbuild\ncoverage\n')"

node --eval "fs.writeFileSync('.prettierrc','{}\n')"

{
"arrowParens": "always",
"bracketSameLine": false,
"bracketSpacing": true,
"embeddedLanguageFormatting": "auto",
"endOfLine": "lf",
"htmlWhitespaceSensitivity": "css",
"insertPragma": false,
"jsxSingleQuote": false,
"plugins": [
"prettier-plugin-css-order",
"prettier-plugin-organize-imports",
"prettier-plugin-tailwindcss"
],
"printWidth": 80,
"proseWrap": "preserve",
"quoteProps": "as-needed",
"requirePragma": false,
"semi": true,
"singleAttributePerLine": false,
"singleQuote": true,
"tabWidth": 2,
"trailingComma": "all",
"useTabs": false
}

{
"extends": ["next/core-web-vitals", "next/typescript", "prettier"]
}

"format": "prettier . --write",
"format:check": "prettier . --check",

4. COMMITIZEN

npm i -g commitizen

commitizen init cz-conventional-changelog --yarn --dev --exact

5. HUSKY

yarn add --dev husky

npx husky init

6. LINT STAGED

yarn add -D lint-staged

replace pre-commit with:

#!/bin/sh
. "$(dirname "$0")/\_/husky.sh"
npx lint-staged

lintstagedrc.json

{
"_.ts": [
"prettier --write",
"eslint"
],
"_.html": [
"eslint",
"prettier --write"
],
"\*.scss": "prettier --write"
}

7. COMMITLINT

yarn add --dev @commitlint/{cli,config-conventional}

echo "import type { UserConfig } from '@commitlint/types';

const Configuration: UserConfig = {
extends: ['@commitlint/config-conventional'],
};

export default Configuration;
" > commitlint.config.ts

ESLINT extensions - eslint-plugin-jsx-a11y eslint-plugin-import eslint-config-prettier

    "eslint-plugin-format": "^0.1.2",
    "eslint-plugin-jest-dom": "^5.4.0",
    "eslint-plugin-jsx-a11y": "^6.10.0",
    "eslint-plugin-playwright": "^1.7.0",
    "eslint-plugin-react-hooks": "^4.6.2",
    "eslint-plugin-react-refresh": "^0.4.12",
    "eslint-plugin-simple-import-sort": "^12.1.1",
    "eslint-plugin-tailwindcss": "^3.17.5",
    "eslint-plugin-testing-library": "^6.3.0",
