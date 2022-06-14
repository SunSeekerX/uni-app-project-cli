# uniapp 技术中台

- 项目地址: [Github](https://github.com/SunSeekerX/uniapp-project)
- 博客地址: [https://yoouu.cn/](https://yoouu.cn/)
- 当我们日复一日年复一年的搬砖的时候，你是否曾想过提升一下开发效率，如果一个通用的架构摆在你的面前，你还会选择自己搭架构么，但是搭建出一个好的架构并非易事，有多少人愿意选择去做，还有多少人选择努力去做好，可能寥寥无几，但是你今天看到的，正是你所想要的，一个真正能解决你开发新项目时最大痛点的架构工程，你不需要再麻木 Copy 原有旧项目的代码，只需改动少量代码就能得到想要的效果，你会发现开发新项目其实是一件很快乐的事。

## 快速上手

**Clone**

```shell
git clone https://github.com/SunSeekerX/uniapp-project.git
```

**安装**

```shell
yarn # 记得安装 yarn! 已经配置了淘宝镜像仓库，配置文件在 .yarnrc.yml
```

把项目拖到 `HbuilderX` 运行就行了。

## 项目亮点

- 常用集成：[uView UI](https://www.uviewui.com/)、[windi-css-uni](https://github.com/SunSeekerX/uni-app-starter/tree/main/packages/windi-css-uni)、[utools](https://utools.yoouu.cn/)
- 代码注释：项目内有非常完善的代码注释，对每个模块的作用做了仔细的说明
- 代码统一：对项目中常见的代码进行了封装，或是封装到工具类中、或者封装到框架中，不追求过度封装，根据实际场景和代码维护性考虑，尽量保证同一个功能的代码在项目中不重复。
- 敏捷开发：一个 App 大概率会出现的功能已经写好，对项目的敏捷开发起到了至关重要的作用，可用于新项目开发或者旧项目重构，可将开发周期缩短近一半的时间，并且后续不会因为前期的快速开发而留下成堆的技术遗留问题，万丈高楼平地起，uniapp-project 属于基建工程，而在软件行业我们称之为技术中台。
- 开发约束：集成 eslint + prettier + stylelint + lint-staged + husky 对从开发到提交至仓库过程进行代码质量把控，保持团队整体风格统一。

## 食用指南

### 项目结构

```
uniapp-project
├── .husky						# Husky 的 Git 钩子配置
│   ├── _						# Husky 的 Git 钩子配置，执行 yarn 会自动安装出来，不提交到 git
│   │   └── husky.sh
│   └── pre-commit				# Husky 的 Git 钩子配置, 代码 commit 之前会执行这里面的命令
├── .vscode						# Vscode 插件配置目录
│   └── settings.json			# └── 目前只有拼写检查插件的配置 “Code Spell Checker”
├── assets						# 项目资源目录，可以存放一些说明，设计稿，历史 logo 等资源
│   └── logo.png				# └── 存放的 logo
├── public
│   └── index.html
├── src
│   ├── apis					# 网络请求的 api
│   ├── components				# 组件
│   ├── config					# 环境变量
│   ├── constant				# 常量
│   ├── pages					# 项目内的页面
│   ├── static					# 静态文件目录
│   │   ├── images				# └── 静态的图片
│   │   └── js					# └── 不需要被打包的 js 库
│   ├── store					# Vuex
│   ├── styles					# 公共样式
│   ├── uni_modules				# uni_modules
│   │   └── uview-ui
│   ├── utils					# 工具
│   │   ├── libs				# 需要打包的 js 库
│   │   ├── request				# 网络请求
│   ├── App.vue
│   ├── androidPrivacy.json		# 安卓用户隐私和服务政策说明
│   ├── main.js					# 项目入口
│   ├── manifest.json			# uni-app 项目配置
│   ├── pages.json				# uni-app 页面配置
│   └── uni.scss				# uni-app 全局的 scss 变量
├── unpackage					# uni-app 生成的 logo 等未打包的资源
├── .eslintignore				# eslint 检查忽略配置
├── .eslintrc.js				# eslint 配置
├── .prettierignore				# prettier 格式化忽略配置
├── .stylelintignore			# stylelint 检查忽略配置
├── README.md					# 项目说明
├── babel.config.js
├── jsconfig.json				# Vscode 能识别项目类型提供代码跳转到定义的功能
├── package.json
├── postcss.config.js
├── prettier.config.js			# prettier 配置
├── stylelint.config.js			# stylelint 配置
```

### 额外命令

scripts 里面包含了一些额外的命令

`yarn gc`

我提交代码喜欢用这个，但是用到了 commitizen 这个插件（用来规范提交信息的），你想用可以看 [规范提交代码](https://doc.yoouu.cn/front-end/npm/#%F0%9F%93%8C-%E8%A7%84%E8%8C%83%E6%8F%90%E4%BA%A4%E4%BB%A3%E7%A0%81) 说明

`yarn lint:eslint`

检查 `src` 目录下 `vue` 和 `js` 后缀结尾的文件是否有错误

`yarn lint:prettier`

使用 `prettier` 格式化 `src` 目录下的 `js,json,tsx,css,less,scss,vue,html,md` 后缀结尾的文件

`yarn lint:stylelint`

使用 `stylelint` 校验和格式化 `src` 目录下的 `vue,less,postcss,css,scss` 后缀结尾的文件内的样式代码

`yarn pkg:sort`

强迫症专用的，对 `package.json` 内的 `key` 值进行排序

### 你需要修改的信息

- `package.json`
  - `name`
  - `version`
  - `repository`
  - `license`
  - `author`
- `src/manifest.json` 到 `HbuilderX` 内的可视化界面去修改吧，如果没出现可视化界面，把项目从 `HbuilderX` 移除重新添加，或者右键`重新构建项目索引`、`重新识别项目类型`，关闭 `manifest.json` 再打开就会出现可视化配置界面了
  - `uni-app 应用标识`
  - `应用名称`
  - `应用描述`
  - `版本名`
  - `版本号`
  - `App 图标配置`
- 删除本项目说明

## 注意

- 不要使用 `npm`

## 关于和联系

如果对项目使用有问题可以提交 issue 或者直接联系 `QQ: 1647800606`。解决了问题记得请我喝咖啡 🥹。
