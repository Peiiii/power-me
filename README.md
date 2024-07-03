# 项目快速启动套路

`tyarn create vite <project-name> --template react-ts`

pnpm i

pnpm add -D sass

## 配置pnpm

.npmrc

```shell
ignore-workspace-root-check = true
```

pnpm-workspace.yaml

```yaml
packages:
  - 'packages/*'
```

## 配置 @/xxx
### 修改tsconfig.json

```json
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["src/*"]
    }
  }
}
```

pnpm add -D @types/node vite-tsconfig-paths

### 修改 vite.config.ts

```ts
import tsconfigPaths from 'vite-tsconfig-paths';
```

## 配置tailwindcss 和 shadcn
参考链接：https://ui.shadcn.com/docs/installation/vite

### tailwindcss
```shell
pnpm add -D tailwindcss postcss autoprefixer

npx tailwindcss init -p
```

### shadcn
```shell
pnpm dlx shadcn-ui@latest init
```
如果要安装某个组件，示例：
```shell
pnpm dlx shadcn-ui@latest add button
```