# android-weather-01-skeleton v1.0

天气应用的最早一版骨架：只建好 LitPal 的三张地区表（省 / 市 / 县）与一个空壳 `MainActivity`，作为后续 [`android-weather-02-textbook`](https://github.com/Xiaodoubi2333/android-weather-02-textbook) 与 [`android-weather-03-source`](https://github.com/Xiaodoubi2333/android-weather-03-source) 的起点。

包名 `com.oldweatherapp.android`，`compileSdk 34 / minSdk 23`。

## 文件结构

```text
app/src/main/java/com/oldweatherapp/android/
├── MainActivity.java      入口，仅有布局加载
└── db/
    ├── Province.java      省
    ├── City.java          市（provinceId 关联）
    └── County.java        县（cityId 关联）
app/src/main/res/layout/   1 个布局（activity_main.xml）
```

全部代码 6 个 Java 文件、1 个布局，业务逻辑尚未接入。

## 启动

1. Android Studio 打开工程并同步 Gradle；
2. 运行 `app` 模块，界面只会显示空白主界面 —— 这一版没有网络请求，也没有地区选择；
3. 可进入 `db/` 三个实体查看表结构与关联字段。

依赖：`appcompat 1.0.2`、`constraintlayout 1.1.3`、`litepal 1.3.2`、`okhttp 3.4.1`、`gson 2.7`、`glide 3.7.0`（除 LitPal 外均未调用）。

## 功能落点表

| # | 功能 | 状态 | 落点 |
|---|---|---|---|
| 1 | 省 / 市 / 县三级数据模型 | 完成 | `db/Province.java`、`db/City.java`、`db/County.java` |
| 2 | 表间关联字段 | 完成 | `City.provinceId`、`County.cityId` |
| 3 | 依赖库预留（网络 / 解析 / 图片） | 完成 | `app/build.gradle` |
| 4 | 地区选择界面 | 未实现 | 后续版本补到 `ChooseAreaFragment` |
| 5 | 天气数据接入 | 未实现 | — |

## 版本记录

### v0.1 · 建库

- `chore: 初始化仓库（LICENSE / .gitignore）`：GitHub 网页端建库。

### v0.2 · 工程首推

- `feat: 导入工程骨架与 LitPal 地区三表`：本地工程首推。

### v1.0 · 依赖就绪

- `build: 修正依赖声明（implementation 拼写），LitPal 可用`：补齐 LitPal / OkHttp / Gson / Glide 依赖，三张表的实体类落地。

## 已知限制

- `applicationId` 与 [`android-weather-02-textbook`](https://github.com/Xiaodoubi2333/android-weather-02-textbook)、[`android-weather-03-source`](https://github.com/Xiaodoubi2333/android-weather-03-source) **三者相同**（`com.oldweatherapp.android`），同一设备只能装其中一个。
- 本仓库只到「数据模型 + 依赖」阶段，不能实际查天气，可运行版本见 [`android-weather-05-navigation`](https://github.com/Xiaodoubi2333/android-weather-05-navigation)。
