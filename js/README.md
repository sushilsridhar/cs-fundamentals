Critical Rendering path

steps your browser goes through to convert the html, js, css into pixels on the screen

optimizing the CRP improves performance

DOM + CSSOM converts to render tree
layout -> size of the screen, viewport metatag - considering the size of the screen to render

optimize CRP

control the order in which resources are loaded
reduce the size (minify js,css compress images)
minimize the number of critical resources at initial load
- defer - execute after dom building
- async - invoke as soon as available

  both loading parallel

![Screenshot 2023-12-01 at 3 26 28 AM](https://github.com/sushilsridhar/cs-fundamentals/assets/16437905/eae5e409-115a-41f0-a211-4bef4a1e8cea)

  
