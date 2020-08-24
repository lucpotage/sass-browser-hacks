# Sass Browser Hacks

Browser hacks from [browserhacks.com](https://browserhacks.com/) for [Dart Sass](https://sass-lang.com/dart-sass).

## Usage

Install the dependency:
```
yarn add @lucpotage/css-hacks --dev
```

Add the library:
```scss
@use '<path>/css-hacks' as *;
```

This library includes three types of CSS hacks:

- Media query hacks
- Feature query hacks
- Selector hacks

Depending on the targeted version, the first type of hack is used.

Supported hacks:

| Browser | Mixin | Version |
| ------- | ----- | ------- |
| Firefox | `firefox` or `ff` | `*`, `1.5`, `>= 2`, `<= 3`, `>= 3`, `>= 3.5`, `>= 3.6`, `>= 4`, `>= 6`, `>= 8`, `>= 16`, `>= 21`, `>= 22`, `>= 24`, `>= 25`, `>= 26`, `>= 27`, `>= 28`, `>= 29`, `>= 30` |
| Internet Explorer | `internet-explorer` or `ie` | `<= 6`, `<= 7`, `7`, `<= 8`, `8`, `>= 10`, `>= 11`|
| Safari | `safari` | `2-3`, `2-3.1`, `5.1-6` |
| Opera | `opera` | `>= 9.5` |

## Examples

Here is how to target Firefox:

<table>
<tr>
  <th>Sass</th>
  <th>CSS</th>
</tr>
<tr>
<td>

```scss
.a {
  color: yellow;

  @include firefox {
    color: red;
  }
}
```

</td>
<td>

```css
.a {
  color: yellow;
}

_:-moz-tree-row(hover), .a {
    color: red;
}
```

</td>
</tr>
</table>

Another example with IE 7:

<table>
<tr>
  <th>Sass</th>
  <th>CSS</th>
</tr>
<tr>
<td>

```scss
.b {
  @include ie('8') {
    color: blue;
  }
}
```

</td>
<td>

```css
@media \0screen {
  .b {
    color: blue;
  }
}
```

</td>
</tr>
</table>