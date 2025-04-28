# TypeScript Exercises Project

This project is a simple setup for running TypeScript exercises and LeetCode problems with Node.js, supporting hot reload using the native `--watch` functionality from newer Node.js versions or using `ts-node-dev` for an even faster workflow.

## Project Setup

### 1. Create the project folder
```bash
mkdir ts-exercises
cd ts-exercises
npm init -y
```

### 2. Install TypeScript and ts-node-dev as development dependencies
```bash
npm install typescript ts-node-dev --save-dev
```

### 3. Generate the TypeScript configuration file
```bash
npx tsc --init
```

Replace the generated `tsconfig.json` with a simplified version:
```json
{
  "compilerOptions": {
    "target": "ES2022",
    "module": "ES2022",
    "moduleResolution": "node",
    "outDir": "./dist",
    "rootDir": "./src",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  },
  "include": ["src"],
  "exclude": ["node_modules", "dist"]
}
```

### 4. Create the project structure
```bash
mkdir src
```
Create an example file:
```bash
echo "console.log('Hello, World!');" > src/index.ts
```

### 5. Update `package.json` scripts
Modify your `package.json` to add build, watch, start, and dev scripts:

```json
{
  "name": "ts-exercises",
  "version": "1.0.0",
  "main": "dist/index.js",
  "scripts": {
    "build": "tsc",
    "watch": "tsc --watch",
    "start": "node dist/index.js",
    "dev": "ts-node-dev --respawn --transpile-only src/index.ts"
  },
  "devDependencies": {
    "typescript": "^5.x.x",
    "ts-node-dev": "^2.x.x"
  },
  "type": "module"
}
```

### 6. Running the Project

#### Option 1: Using TypeScript Compiler (`tsc`)
- **Start watching files**:
  ```bash
  npm run watch
  ```
- **Run the program** (in a separate terminal):
  ```bash
  npm start
  ```

#### Option 2: Using `ts-node-dev`
- **Start the development server with hot reload**:
  ```bash
  npm run dev
  ```
This will automatically recompile and rerun your TypeScript files on changes without needing separate terminals.

---

## (Optional) Notes
If you prefer even faster iteration, `ts-node-dev` is a great option. Otherwise, using the native `tsc --watch` setup provides a more standard Node.js workflow.
