# VGG Browser

VGG browser is a web-compatible browser that is based on VGG specs and runtime, which renders everthing as vector graphics.

## Motivation

The modern web browser is not only a browser for hyper-linked documents, but also a foundation for GUI applications. Modern GUI applications are heavily relying on the web browser or its variants like WebView/CEF/Electron and so on.

However, the web browser itself is a HUGE project that is hardly possible to build from scratch, as there are many different specifications like HTML, CSS, SVG, and etc. Each specification at least requires a separate parser implementation and a render implementation, not even to mention that these specifications need to fit each other.

Luckily, VGG specs and runtime happen to provide an alternative way for building a web-compatible browser by converting any web codes into VGG's vector graphics as well as utilizing the power provided by VGG runtime. So why not just build it for fun?

## Web Compatibility

This outlines how we might handle each web standards

| Web Standards       | How to be compatible | Status                          |
| ------------------- | -------------------- | ------------------------------- |
| HTML/CSS            | converted to VGG     | Just staring                    |
| SVG                 | converted to VGG     | Just staring                    |
| JS/WebAssembly      | Use Nodejs           | Already provided by VGG runtime |
| Network related     | Use Nodejs           | Already provided by VGG runtime |
| Canvas              | Use Skia             | Already provided by VGG runtime |
| Audio/Video/WebRTC  | TBD                  | Will be provided by VGG runtime |
| WebGL/WebGPU        | TBD                  | Will be provided by VGG runtime |
| WebAI (it's a joke) | TBD                  | No such a standard exists yet   |

Please note that this outline is not a complete list of web techs. For starting, we will focus on the HTML/CSS/SVG conversion, which will takes a long time to be mature.

## Benefits

The benefits are mainly for modern GUI application developers.

- **Design-as-Code Paradigm** will help you accelerate your application building process. As you can do all the UI design stuff in tools like Figma/Sketch, then you program the logic into it, and the application is alive in VGG browser.
- **A True Web Container**. You do not have to reinvent fake web containers just to letting Nodejs application running in your browser, because we already embed a whole native Nodejs runtime in VGG browser to be used as the core executor engine!
- **Embeddable & Modular & Hackable**. Just like VGG runtime, VGG browser will be embeddable into any of your applications, which means it'll be an alternative to WebView/CEF/Electron. Furthermore, not only VGG browser will be designed to be modular for you to customize for your needs, but also it will provide internal APIs for hacking in a normal VGG application. This feature is heavily needed in some Web applications (like Figma) but is not provided in common web browsers.



## Tests (TBD)

- [ACID](http://www.acidtests.org/)

## License

MIT License