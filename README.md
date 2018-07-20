# @gurinder/vue-loader-page
Full Page Loader  inspired by https://github.com/nzbin/three-dots
### Usage

```html
<vue-loader-page :loading="true"></vue-loader-page
```

```js
import VueLoadingFullPage from '@gurinder/vue-loading-full-page';
Vue.component('vue-loading-full-page', VueLoadingFullPage);
```

```css
body.ovf-h {
  overflow-x: hidden;
}

// ==============================================
// Variables
// ==============================================

$dotWidth: 10px;
$dotHeight: 10px;
$dotRadius: $dotWidth / 2;

$dotColor: $primary;
$dotBgColor: $dotColor;
$dotBeforeColor: $dotColor;
$dotAfterColor: $dotColor;

$dotSpacing: $dotWidth + $dotWidth/2;

// ==============================================
// Mixins
// ==============================================

@mixin dot($width: $dotWidth, $height: $dotHeight, $radius: $dotRadius,$bgColor: $dotBgColor, $color: $dotColor ) {
  width: $width;
  height: $height;
  border-radius: $radius;
  background-color: $bgColor;
  color: $color;
}

/**
 * ==============================================
 * Dot Bricks
 * ==============================================
 */

$spacing: $dotWidth + 6px;
$topPos: $spacing/2;
$leftPos: -9999px;
$x1: - $leftPos - $topPos;
$x2: - $leftPos - $topPos + $spacing;
$y1: 0;
$y2: -$spacing;

.dot-bricks {
  position: relative;
  top: $topPos;
  left: $leftPos;

  @include dot;

  box-shadow:
          $x1 $y2 0 0 $dotBeforeColor,
          $x1 $y1 0 0 $dotColor,
          $x2 $y1 0 0 $dotAfterColor;
  animation: dotBricks 2s infinite ease;
}

@keyframes dotBricks {
  0% {
    box-shadow:
            $x1 $y2 0 0 $dotBeforeColor,
            $x1 $y1 0 0 $dotColor,
            $x2 $y1 0 0 $dotAfterColor;
  }

  8.333% {
    box-shadow:
            $x2 $y2 0 0 $dotBeforeColor,
            $x1 $y1 0 0 $dotColor,
            $x2 $y1 0 0 $dotAfterColor;
  }

  16.667% {
    box-shadow:
            $x2 $y2 0 0 $dotBeforeColor,
            $x1 $y2 0 0 $dotColor,
            $x2 $y1 0 0 $dotAfterColor;
  }

  25% {
    box-shadow:
            $x2 $y2 0 0 $dotBeforeColor,
            $x1 $y2 0 0 $dotColor,
            $x1 $y1 0 0 $dotAfterColor;
  }

  33.333% {
    box-shadow:
            $x2 $y1 0 0 $dotBeforeColor,
            $x1 $y2 0 0 $dotColor,
            $x1 $y1 0 0 $dotAfterColor;
  }

  41.667% {
    box-shadow:
            $x2 $y1 0 0 $dotBeforeColor,
            $x2 $y2 0 0 $dotColor,
            $x1 $y1 0 0 $dotAfterColor;
  }

  50% {
    box-shadow:
            $x2 $y1 0 0 $dotBeforeColor,
            $x2 $y2 0 0 $dotColor,
            $x1 $y2 0 0 $dotAfterColor;
  }

  58.333% {
    box-shadow:
            $x1 $y1 0 0 $dotBeforeColor,
            $x2 $y2 0 0 $dotColor,
            $x1 $y2 0 0 $dotAfterColor;
  }

  66.666% {
    box-shadow:
            $x1 $y1 0 0 $dotBeforeColor,
            $x2 $y1 0 0 $dotColor,
            $x1 $y2 0 0 $dotAfterColor;
  }

  75% {
    box-shadow:
            $x1 $y1 0 0 $dotBeforeColor,
            $x2 $y1 0 0 $dotColor,
            $x2 $y2 0 0 $dotAfterColor;
  }

  83.333% {
    box-shadow:
            $x1 $y2 0 0 $dotBeforeColor,
            $x2 $y1 0 0 $dotColor,
            $x2 $y2 0 0 $dotAfterColor;
  }

  91.667% {
    box-shadow:
            $x1 $y2 0 0 $dotBeforeColor,
            $x1 $y1 0 0 $dotColor,
            $x2 $y2 0 0 $dotAfterColor;
  }

  100% {
    box-shadow:
            $x1 $y2 0 0 $dotBeforeColor,
            $x1 $y1 0 0 $dotColor,
            $x2 $y1 0 0 $dotAfterColor;
  }
}
```