# @yuri2/exec-shell

[Github](https://github.com/yuri2peter/npm-exec-shell)
@yuri2/exec-shell 是 nodejs 调用 shell 脚本的一个方法库。

## 安装

`npm i @yuri2/exec-shell`

## 使用

```ts
import { execShellScriptContent } from "@yuri2/exec-shell";

async function main() {
  const results1 = await execShellScriptContent(`echo hello`);
  console.log(results1);

  const results2 = await execShellScriptFile(__dirname + "/test.sh");
  console.log(results2);
}

main();
```

## 开发

### 源码编写

- `src` 目录下编写源码
- `test` 目录下编写测试
- `npm run test` 执行测试文件 `test/index.ts`

### 打包编译

```
按需求，修改rollup.config.js文件
npm run build 生成index.ts文件和.d.ts声明文件
```

### 发布前测试

1. 全局测试：把包链接到全局环境
   ` npm link`

2. 本地项目测试：把包链接到项目本地环境
   `cd 本地项目根目录`
   `npm link 包名`

3. 取消本地项目测试：把包从本地环境取消
   `cd 本地项目根目录`
   `npm unlink 包名`

4. 取消全局测试：把包从全局环境中取消
   `npm unlink 包名`

### npm 发布

第一次发布：

- 修改版本号
- 提交 github
  `npm publish --access public`

更新版本：
`npm run release`
