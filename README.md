```typescript
export const aspectRatio = (
  parentWidth: number,
  parentHeight: number,
  childWidth: number,
  childHeight: number
): {
  width: number;
  height: number;
  offsetX: number;
  offsetY: number;
} => {
  const doRatio = childWidth / childHeight;
  const cRatio = parentWidth / parentHeight;
  let width = parentWidth;
  let height = parentHeight;

  if (doRatio < cRatio) {
    height = width / doRatio;
  } else {
    width = height * doRatio;
  }

  return {
    width,
    height,
    offsetX: (parentWidth - width) / 2,
    offsetY: (parentHeight - height) / 2,
  };
};

```
