# `<SwipeRow />` API

Row that is generally used in a `<SwipeListView/>`.
If you are rendering a `<SwipeRow/>` explicitly you must pass the `<SwipeRow/>` exactly two children.
The first will be rendered behind the second.
e.g.
```javascript
<SwipeRow>
    <View style={hiddenRowStyle} />
    <View style={visibleRowStyle} />
</SwipeRow>
```

### Props

| Prop | Notes | Type | (func) Signature | Default |
|---|---|---|---|---|
| `closeOnRowPress` | Should the row be closed when it is tapped | `bool` | | `true`
| `directionalDistanceChangeThreshold` | Change the sensitivity of the row | `number` || `2`
| `friction` | Friction for the open / close animation. Controls "bounciness"/overshoot. https://facebook.github.io/react-native/docs/animated#spring | `number` || `7`
| `tension` | Tension for the open / close animation. Controls speed. https://facebook.github.io/react-native/docs/animated#spring | `number` || `40`  
| `leftOpenValue` | TranslateX value for opening the row to the left (positive number) | `number` || `0`
| `rightOpenValue` | TranslateX value for opening the row to the right (negative number) | `number` || `0`
| `stopLeftSwipe` | TranslateX value for stop the row to the left (positive number). This number is the stop value corresponding to the `leftOpenValue` (while the row is swiping in the right direction) | `number` |
| `stopRightSwipe` | TranslateX value for stop the row to the right (negative number). This number is the stop value corresponding to the `rightOpenValue` (while the row is swiping in the left direction) | `number` |
| `onRowPress` | Called when row is pressed. | `func` | `{ } : void`
| `onRowOpen` | Called when row is animating open. Used by the SwipeListView to keep references to open rows. | `func` | `{ toValue: number } : void`
| `onRowDidOpen` | Called when row has animated open | `func` | `{ toValue: number } : void`
| `onRowClose` | Called when row is animating closed | `func` | `{ } : void`
| `onRowDidClose` | Called when a swipe row has animated closed | `func` | `{ } : void`
| `swipeToOpenPercent` | What % of the left/right openValue does the user need to swipe past to trigger the row opening. | `number` || `50`
| `swipeToClosePercent` | What % of the left/right openValue does the user need to swipe past to trigger the row closing. | `number` || `50`
| `setScrollEnabled` | Used by the SwipeListView to close rows on scroll events. You shouldn't need to use this prop explicitly. | `func` |
| `disableLeftSwipe` | Disable ability to swipe the row left | `bool` || `false`
| `disableRightSwipe` | Disable ability to swipe the row right | `bool` || `false`
| `recalculateHiddenLayout` | Enable hidden row onLayout calculations to run always | `bool` || `false`
| `style` | Styles for the parent wrapper View of the SwipeRow | `object` |
| `preview` | Should the row do a slide out preview to show that it is swipeable | `bool` || `false`
| `previewDuration` | Duration of the slide out preview animation | `number` || `300`
| `previewOpenValue` | TranslateX value for the slide out preview animation | `number` || 0.5 * props.rightOpenValue
| `onSwipeValueChange` | Callback invoked any time the translateX value of the row changes | `func` | `{ swipeData: { value: number, direction: 'left' | 'right', isOpen: bool }`
| `swipeGestureBegan` | Called when the row is animating swipe | `func` | `{ } : void`
| `swipeToOpenVelocityContribution` | Describes how much the ending velocity of the gesture affects whether the swipe will result in the item being closed or open. A velocity factor of 0 (the default) means that the velocity will have no bearing on whether the swipe settles on a closed or open position and it'll just take into consideration the swipeToOpenPercent. Ideal values for this prop tend to be between 5 and 15. | `number` || `0`
| `shouldItemUpdate` | Callback to determine whether component should update | `func` | `{ currentItem: any, newItem: any }`
| `forceCloseToLeftThreshold` | TranslateX amount(not value!) threshold that triggers force-closing the row to the Left End (positive number) | `number` |
| `forceCloseToRightThreshold` | TranslateX amount(not value!) threshold that triggers force-closing the row to the Right End (positive number) | `number` |
| `onForceCloseToLeft` | Callback invoked when row is force closing to the Left End | `func` |
| `onForceCloseToRight` | Callback invoked when row is force closing to the Right End | `func` |
| `onForceCloseToLeftEnd` | Callback invoked when row has finished force closing to the Left End | `func` |
| `onForceCloseToRightEnd` | Callback invoked when row has finished force closing to the Right End | `func` |
| `useNativeDriver` | useNativeDriver: `true` for all animations | `bool` | `true` |
