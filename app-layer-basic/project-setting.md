# プロジェクトのセッティング  
「開発環境のインストール」で、npmとAngularをインストールし、新規プロジェクトを作成するところまでいきました。  
次はそのプロジェクトに、見栄えをよくするためのAngular Materialと、nemを使うためのnem-libraryをインストールします。  
[Angular Material](https://material.angular.io/)  
[nem-library](https://nemlibrary.com/)  

## Angular Formsのインポート  
[プロジェクト名]/src/app/app.module.tsに、Angular Animationsを使うことを書き込みます。
```./src/app/app.module.ts 
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppRoutingModule } from './app-routing.module';

import { FormsModule } from '@angular/forms';
//↑追加

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule
    //↑追加
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Angular Materialのインストール  
コマンドラインが、新規作成したプロジェクトのフォルダを指している状態で以下を入力します。  
```
npm install --save @angular/material @angular/cdk
```

### Angular Coreのアップデート  
Angular Materialのインストールの際、@angular/coreと@angular/commonのバージョンが古いと警告が出る時があります。  
```
npm update @angular/core @angular/common
```
と入力してアップデートしてあげてください。  

## Angular Animationsのインストール  
コマンドラインが、新規作成したプロジェクトのフォルダを指している状態で以下を入力します。  
```
npm install --save @angular/animations
```

[プロジェクト名]/src/app/app.module.tsに、Angular Animationsを使うことを書き込みます。
```./src/app/app.module.ts 
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppRoutingModule } from './app-routing.module';

import { FormsModule } from '@angular/forms';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
//↑追加

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule,
    BrowserAnimationsModule
    //↑追加
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## Angular FlexLayoutのインストール  
コマンドラインが、新規作成したプロジェクトのフォルダを指している状態で以下を入力します。  
```
npm install --save @angular/flex-layout
```

[プロジェクト名]/src/app/app.module.tsに、Angular FlexLayoutを使うことを書き込みます。
```./src/app/app.module.ts 
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppRoutingModule } from './app-routing.module';

import { FormsModule } from '@angular/forms';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { FlexLayoutModule } from "@angular/flex-layout";
//↑追加

import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule,
    BrowserAnimationsModule,
    FlexLayoutModule
    //↑追加
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
## hammerjsのインストール  
タッチによる操作を便利にします。  
```
npm install --save hammerjs
```

[プロジェクト名]/src/main.tsに、hammerjsを使うことを書き込みます。  
```./src/main.ts
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

import 'hammerjs';
//↑追加

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.log(err));
```

## Material Iconsの参照  
[Material Icons](https://material.io/tools/icons/)にあるアイコンを使えるようにします。  

```./src/index.html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>ProjectTemplate</title>
  <base href="/">

  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">

  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
</head>
<body>
  <app-root></app-root>
</body>
</html>
```

## nem-libraryのインストール
```
npm install nem-library rxjs --save
```

## Strictモードにする  
strictモードにすると、曖昧な記述をエラーにしてくれるので、勉強には最適です。  
```
"strict": true
```
を、[プロジェクト名]/tsconfig.jsonに書き込みます。
```./tsconfig.json
{
  "compileOnSave": false,
  "compilerOptions": {
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "moduleResolution": "node",
    "emitDecoratorMetadata": true,
    "experimentalDecorators": true,
    "target": "es5",
    "typeRoots": [
      "node_modules/@types"
    ],
    "lib": [
      "es2017",
      "dom"
    ],
    "strict": true
  }
}
```
