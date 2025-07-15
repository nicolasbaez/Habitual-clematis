# Habitual-clematis
predicting chaos

![buh](https://github.com/nicolasbaez/Habitual-clematis/blob/main/xp051.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
k = 0;
draw = (_) => {
  clear();
  noFill();
  rotateX(k);
  rotateY(k / 2);
  for (i = 0; i < 6; i += 0.1)
    for (j = 0; j < 3; j += 0.1) {
      r = map(sin(k), -1, 1, noise(i, j, k) * w, -noise(k, j, i) * w);
      stroke(noise(i, j, k) * 255);
      point(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  if (k == 0) saveGif("xp051.gif", 600, { delay: 0, units: "frames" });
  k += 0.01;
};
