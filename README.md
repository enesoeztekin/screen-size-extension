# Screen Size Extension

### What is it for?

It might be used when you need to check screen size to decide your website's responsive behaviours such as media breakpoints. Indeed I built this extension for me to help in my projects. Then, I wanted to share it here on Github in case there might be someone who wants to check screen sizes without the need to check from developer tools of browsers.

### Preview:

![Preview](./Screen-Size-Extension.gif)

### How to use?

1. First, implement an HTML tag which has an ID as 'extension'

   ```
   <div id="extension"></div>
   ```

2. Then, add the JS code into your JS file or HTML file where you want to use the extension.

   ```
   const extension = document.querySelector("#extension");
       var screenSize = window.innerWidth;
       var screenType = "Desktop";
       function checkScreenSize(screenSize) {
           switch (true) {
               case screenSize >= 1440:
                   screenType = "XL - Desktop";
                   break;
               case screenSize < 1440 && screenSize >= 1024:
                   screenType = "Desktop";
                   break;
               case screenSize < 1024 && screenSize >= 768:
                   screenType = "Tablet";
                   break;
               case screenSize < 768 && screenSize >= 425:
                   screenType = "L - Mobile";
                   break;
               case screenSize < 425 && screenSize >= 375:
                   screenType = "M - Mobile";
                   break;
               case screenSize < 375 && screenSize >= 320:
                   screenType = "S - Mobile";
                   break;
               case screenSize < 320:
                   screenType = "XS - Mobile";
                   break;
               default:
                   screenType = "Desktop";
                   break;
           }
       }
       checkScreenSize();
       extension.textContent = `${window.innerWidth} px (${screenType})`;
       window.addEventListener(
           "resize",
           () => {
               checkScreenSize(window.innerWidth);
               extension.textContent = `${window.innerWidth} px (${screenType})`;
           },
           true
       );
   ```

3. Lastly, add the style code of the extension to your CSS file.

   ```
    #extension {
           position: fixed;
           top: 0;
           left: 0;
           background-color: #f76b00;
           color: white;
           font-weight: 900;
           font-size: 18px;
       }
   ```

If you find this useful, please don't forget to leave a star :)
