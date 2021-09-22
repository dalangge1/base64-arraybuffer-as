# base64-arraybuffer-as

一个用 AssemblyScript 编写的 base64-arraybuffer

## 性能

```yml
CPU: i9 10900es
Input: tests/screen.jpg(3.95MB)

Node: 16.8.0
JS Cost: 314ms(4.13x)
Wasm Cost: 76ms(1.00x)
Buffer.toString Cost: 4ms(0.05x)

Chrome: 96
JS Cost: 256ms(2.20x)
Wasm Cost: 116ms(1.00x)

Firefox: 94
JS Cost: 327ms(0.95x)
Wasm Cost: 343ms(1.00x)

Phone: Redmi note 10 Pro
WeChat WebView: 
JS Cost: 359ms(2.28x)
Wasm Cost: 157ms(1.00x)

QQ Browser: 11.9.6
JS Cost: 366ms(2.61x)
Wasm Cost: 140ms(1.00x)
```

## 使用

```sh
> npm/pnpm i -S base64-arraybuffer-as
```

### NodeJS

```js
const fs = require('fs');
const base64ArrayBuffer = require('base64-arraybuffer-as');

const imgData = fs.readFileSync(__dirname + './tests/screen.jpg');
const base64 = base64ArrayBuffer(imgData);

// 当然NodeJS下应该使用Buffer.toString('base64');
```

## TODO

1. 支持浏览器 (done 火狐下js比wasm快
2. 支持微信小程序
3. 增加构建wasm inline版本
4. 增加base64 to arraybuffer

## 赞助

如果项目对您有帮助，欢迎打赏

<img src="https://upload-images.jianshu.io/upload_images/252050-d3d6bfdb1bb06ddd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240" alt="赞赏码" width="300">
