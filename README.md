# vuevapor.watch

**Live Site:** [vuevapor.watch](https://vuevapor.watch/)

This repository serves two purposes:

## 1. Working Vue Vapor + TypeScript Example

Setting up Vue Vapor with TypeScript is tricky during the alpha. This repo provides a working reference in `example/`.

**Key workarounds:**

```typescript
// example/src/env.d.ts - Fix .vue imports
declare module '*.vue' {
  import type { createVaporApp } from 'vue'
  type VaporRoot = Parameters<typeof createVaporApp>[0]
  const component: VaporRoot
  export default component
}
```

```typescript
// example/src/main.ts - Entry point
import { createVaporApp } from 'vue'
import App from './App.vue'

createVaporApp(App as any).mount('#app')
```

```json
// tsconfig.app.json
{
  "vueCompilerOptions": {
    "target": 3.6
  }
}
```

These workarounds will become unnecessary once Vue 3.6 reaches stable.

## 2. Automated Benchmarks

Tracks Vue Vapor's bundle size evolution toward the ~10KB target.

A GitHub Action runs daily to:
1. Check for new Vue 3.6.x releases
2. Run benchmarks comparing Vapor vs Classic
3. Create a PR with results

**Why sizes are still large:** During alpha, Vue is porting features into Vapor. Once complete, apps can drop the Virtual DOM runtime and reach ~10KB.

See [vuevapor.watch](https://vuevapor.watch/) for live results or [benchmark/README.md](benchmark/README.md) for details.

## Quick Start

```bash
npm install
npm run dev           # Run example app
npm run benchmark     # Compare Vapor vs Classic
```

## Project Structure

```
vuevapor-watch/
├── example/           # Vue Vapor + TypeScript setup
├── benchmark/         # Bundle size comparison tooling
├── docs/              # Website (GitHub Pages)
└── .github/workflows/ # Daily release tracker
```

## Repository Settings

For automated PRs, enable: **Settings > Actions > General > "Allow GitHub Actions to create and approve pull requests"**

## Resources

- [Vue Vapor RFC](https://github.com/vuejs/rfcs/discussions/502)
- [Benchmark History](benchmark/results/build-history.json)

## License

MIT
