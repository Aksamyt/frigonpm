# `frigonpm`

Simple utility to freeze dependencies in your `package.json` files.

## Installation

```sh
npm i --global frigonpm
```

### Prerequisites
- `npm`
- `jq`

## Overview

Basically does this:
- `npm i`
- backup `package.json`
- replace version numbers with those found with `npm ls`

<table>
<thead>
<tr><th>Before</th><th>After</th></tr>
</thead>
<tbody>
<tr>
<td>

```json
{
  "name": "sample",
  "version": "1.0.0",
  "description": "A sample package.json file",
  "dependencies": {
    "@sveltejs/adapter-auto": "^2.0.0",
    "@sveltejs/kit": "^1.5.0",
    "prettier": "^2.8.0",
    "prettier-plugin-svelte": "^2.8.1",
    "svelte": "^3.54.0",
    "svelte-check": "^3.0.1",
    "tslib": "^2.4.1",
    "typescript": "^5.0.0",
    "vite": "^4.2.0",
    "vitest": "^0.25.3"
  },
  "devDependencies": {
    "nodemon": "^1.18.10"
  }
}
```

</td>
<td>

```json
{
  "name": "sample",
  "version": "1.0.0",
  "description": "A sample package.json file",
  "dependencies": {
    "@sveltejs/adapter-auto": "2.0.0",
    "@sveltejs/kit": "1.15.7",
    "prettier": "2.8.7",
    "prettier-plugin-svelte": "2.10.0",
    "svelte": "3.58.0",
    "svelte-check": "3.2.0",
    "tslib": "2.5.0",
    "typescript": "5.0.4",
    "vite": "4.3.1",
    "vitest": "0.25.8"
  },
  "devDependencies": {
    "nodemon": "1.19.4"
  }
}
```

</td>
</tr>
</tbody>
</table>
