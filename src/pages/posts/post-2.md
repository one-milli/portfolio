---
layout: ../../layouts/MarkdownPostLayout.astro
title: "Array.prototype.reduce()メソッドについて"
pubDate: 2024-02-10
description: ""
author: "Kazuma Ohara"
image:
  url: "https://docs.astro.build/assets/full-logo-light.png"
  alt: "The full Astro logo."
tags: ["astro", "blog", "first post"]
---

# Array.prototype.reduce()

# JavaScript の`Array.prototype.reduce`メソッドについて

`Array.prototype.reduce`は、JavaScript の配列に対して使用できるメソッドです。このメソッドは、配列の要素を 1 つの値に集約（reduce）することができます。

## 構文

```jsx
array.reduce(callback[, initialValue])
```

- `callback`: 各要素に対して実行するコールバック関数
  - `accumulator`: 累積値（前の要素までの処理結果）
  - `currentValue`: 現在処理している要素の値
  - `currentIndex`: 現在処理している要素のインデックス
  - `array`: `reduce`メソッドを呼び出した配列
- `initialValue`: 初期値（オプション）

## 使用例

### 配列の合計値を求める

```jsx
const numbers = [1, 2, 3, 4, 5];
const sum = numbers.reduce(
  (accumulator, currentValue) => accumulator + currentValue
);
console.log(sum); // 出力: 15
```

この例では、`reduce`メソッドを使用して配列`numbers`の要素の合計値を求めています。コールバック関数では、`accumulator`に前の要素までの合計値が格納され、`currentValue`に現在の要素の値が格納されます。これらを足し合わせることで、配列の合計値を求めることができます。

### 初期値を指定する

```jsx
const numbers = [1, 2, 3, 4, 5];
const product = numbers.reduce(
  (accumulator, currentValue) => accumulator * currentValue,
  1
);
console.log(product); // 出力: 120
```

この例では、`reduce`メソッドに初期値`1`を指定しています。初期値を指定すると、`accumulator`の初期値として使用されます。この例では、配列の要素の積を求めるために、初期値を`1`に設定しています。

### オブジェクトの配列から特定のプロパティの合計を求める

```jsx
const books = [
  { title: "Book 1", pages: 100 },
  { title: "Book 2", pages: 150 },
  { title: "Book 3", pages: 200 },
];

const totalPages = books.reduce(
  (accumulator, currentBook) => accumulator + currentBook.pages,
  0
);
console.log(totalPages); // 出力: 450
```

この例では、`reduce`メソッドを使用してオブジェクトの配列`books`から、各オブジェクトの`pages`プロパティの合計値を求めています。初期値を`0`に設定し、コールバック関数内で`currentBook.pages`を`accumulator`に加算することで、合計ページ数を求めることができます。

## まとめ

`Array.prototype.reduce`メソッドは、配列の要素を 1 つの値に集約するために使用されます。コールバック関数を使用して、配列の各要素に対して処理を行い、累積値を更新していきます。初期値を指定することもでき、柔軟性の高いメソッドです。配列の合計値や積、オブジェクトの配列から特定のプロパティの合計を求めるなど、様々な場面で活用できます。
