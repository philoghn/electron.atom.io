---
version: v0.30.0
category: API
title: 'Clipboard Ko'
source_url: 'https://github.com/atom/electron/blob/master/docs/api/clipboard-ko.md'
---

﻿# clipboard

`clipboard`는 복사/붙여넣기 작업을 수행하는 방법을 제공합니다. 다음 예제는 클립보드에 문자열을 씁니다:

```javascript
var clipboard = require('clipboard');
clipboard.writeText('Example String');
```

X Window 시스템에선 selection 클립보드도 존재합니다. 이를 사용하려면 인자 뒤에 `selection` 문자열을 같이 지정해주어야 합니다:

```javascript
var clipboard = require('clipboard');
clipboard.writeText('Example String', 'selection');
console.log(clipboard.readText('selection'));
```

## clipboard.readText([type])

* `type` String

클립보드 컨텐츠를 `plain text`로 반환합니다.

## clipboard.writeText(text[, type])

* `text` String
* `type` String

클립보드에 `plain text`로 문자열을 씁니다.

## clipboard.readHtml([type])

* `type` String

클립보드 컨텐츠를 `markup`으로 반환합니다.

## clipboard.writeHtml(markup[, type])

* `markup` String
* `type` String

클립보드에 `markup`으로 씁니다.

## clipboard.readImage([type])

* `type` String

클립보드로부터 [NativeImage](http://electron.atom.io/docs/v0.30.0/api/native-image-ko)로 이미지를 읽어들입니다.

## clipboard.writeImage(image[, type])

* `image` [NativeImage](http://electron.atom.io/docs/v0.30.0/api/native-image-ko)
* `type` String

클립보드에 `image`를 씁니다.

## clipboard.clear([type])

* `type` String

클립보드에 저장된 모든 컨텐츠를 삭제합니다.

## clipboard.availableFormats([type])

클립보드의 `type`에 해당하는 지원하는 `format`을 문자열로 반환합니다.

## clipboard.has(data[, type])

* `data` String
* `type` String

클립보드가 지정한 `data`의 형식을 지원하는지 확인합니다.

```javascript
var clipboard = require('clipboard');
console.log(clipboard.has('<p>selection</p>'));
```

**알림:** 이 API는 실험적인 기능이며 차후 최신버전에서 제외될 수 있습니다.

## clipboard.read(data[, type])

* `data` String
* `type` String

클립보드로부터 `data`를 읽어들입니다.

**알림:** 이 API는 실험적인 기능이며 차후 최신버전에서 제외될 수 있습니다.
