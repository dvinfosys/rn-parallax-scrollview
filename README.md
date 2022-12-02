# rn-update-parallax-scrollview
rn-update-parallax-scrollview like a parallax and sticky header

## Installation

```
$ npm install rn-update-parallax-scrollview --save
```

## Basic Usage

```js
import ParallaxScrollView from 'rn-update-parallax-scrollview';

// Inside of a component's render() method:
render() {
  return (
    <ParallaxScrollView
      backgroundColor="blue"
      contentBackgroundColor="pink"
      parallaxHeaderHeight={300}
      renderForeground={() => (
       <View style={{ height: 300, flex: 1, alignItems: 'center', justifyContent: 'center' }}>
          <Text>Hello World!</Text>
        </View>
      )}>
      <View style={{ height: 500 }}>
        <Text>Scroll me</Text>
      </View>
    </ParallaxScrollView>
  );
}
```

## Usage (API)

All of the properties of `ScrollView` are supported. Please refer to the
[`ScrollView` documentation](https://facebook.github.io/react-native/docs/scrollview.html) for more detail.

The `ParallaxScrollView` component adds a few additional properties, as described below.

| Property | Type | Required | Description |
| -------- | ---- | -------- | ----------- |
| `backgroundColor` | `string` | No | The color of the header background. Defaults to `#000`) |
| `backgroundScrollSpeed` | `number` | No | The speed factor that the background moves at relative to the foreground. Defaults to 5. |
| `contentBackgroundColor` | `string` | No | This is the background color of the content. (Defaults to `'#fff'`) |
| `fadeOutForeground` | `bool` | No | If `true`, the foreground will fade out as the user scrolls up. (Defaults to `true`) |
| `onChangeHeaderVisibility` | `func` | No | A callback function that is invoked when the parallax header is hidden or shown (as the user is scrolling). Function is called with a `boolean` value to indicate whether header is visible or not. |
| **`parallaxHeaderHeight`** | `number` | **Yes** |This is the height of parallax header. |
| `renderBackground` | `func` | No | This renders the background of the parallax header. Can be used to display cover images for example. (Defaults to an opaque background using `backgroundColor`) |
| `renderContentBackground` | `func` | No | This renders the background of the content. Can be used to display cover images for example. (Defaults to a non-visible `View`) |
| `renderFixedHeader` | `func` | No | This renders an optional fixed header that will always be visible and fixed to the top of the view (and sticky header). You should set its height and width appropriately. |
| `renderForeground` |  `func` | No |This renders the foreground header that moves at same speed as scroll content. |
| `renderScrollComponent` | `func` | No | A function with input `props` and outputs an `Animated.ScrollView`-like component in which the content is rendered. This is useful if you want to provide your own scrollable component, remember however to make it an Animated component. (By default, returns a `Animated.ScrollView` with the given props) |
| `renderStickyHeader` | `func` | No | This renders an optional sticky header that will stick to the top of view when parallax header scrolls up. |
| `stickyHeaderHeight` | `number` | If `renderStickyHeader` is used | If `renderStickyHeader` is set, then its height must be specified. |
| `contentContainerStyle` | `object` | No | These styles will be applied to the scroll view content container which wraps all of the child views. (same as for [ScrollView](https://facebook.github.io/react-native/docs/scrollview.html#contentcontainerstyle)) |
| `outputScaleValue` | `number` | No | The value for the scale interpolation output value, default `5` |
| `scrollEvent` | `func` | No | Callback to recieve the animated scroll event values |
