#Java #library 

JavaFX is a Java library and a GUI toolkit designed to develop and facilitate Rich Internet applications, web applications, desktop applications and even games.

The applications written using this library can run on multiple operating systems like Windows, Linux, iOS, Android, and several platforms like Desktops, Web, Mobile Phones, TVs, Tablets, etc. This characteristic of the JavaFX library makes it very versatile across operating systems and different platforms.

## JavaFx Arcitecture
![[Pasted image 20241127140913.png]]

As we can see in the above figure that, JavaFX architecture comprises many different components. These components are briefly described as follows:

1. **JavaFX API –** The topmost layer of JavaFX architecture holds a JavaFX public API that implements all the required classes that are capable of producing a full-featured JavaFX application with rich graphics. The list of all the important packages of this API is as follows.
2. **javafx.animation:**  It includes classes that are used to combine transition-based animations such as fill, fade, rotate, scale and translation, to the JavaFX nodes (collection of nodes makes a scene graph).
3.  **javafx.css −** It comprises classes that are used to append CSS–like styling to the JavaFX GUI applications.
4. **javafx.geometry −** It contains classes that are used to represent 2D figures and execute methods on them.
5. **javafx.scene −** This package of JavaFX API implements classes and interfaces to establish the scene graph. In extension, it also renders sub-packages such as canvas, chart, control, effect, image, input, layout, media, paint, shape, text, transform, web, etc. These are the diverse elements that sustain this precious API of JavaFX.
6. **javafx.application −** This package includes a collection of classes that are responsible for the life cycle of the JavaFX application.
7. **javafx.event −** It includes classes and interfaces that are used to perform and manage JavaFX events.
8. **javafx.stage −** This package of JavaFX API accommodates the top-level container classes used for the JavaFX application.
9. **Scene Graph –** A Scene Graph is the starting point of the development of any of the GUI Applications.  In JavaFX, all the GUI Applications are made using a Scene Graph only. The Scene Graph includes the primitives of the rich internet applications that are known as nodes. In simple words, a single component in a scene graph is known as a node. In general, a scene graph is made up of a collection of nodes. All these nodes are organized in the form of a hierarchical tree that describes all of the visual components of the application’s user interface (UI). A node instance can be appended to a scene graph only once. The nodes of a scene graph can have numerous segments like Effects, Opacity, Transforms, Event Handlers, Application Specific States. The nodes are of three general types.
	![[Pasted image 20241127141530.png]]
**10. Quantum Toolkit –** Quantum Toolkit is used to connect prism and glass windowing tool kits collectively and makes them prepared for the above layers in the stack. In simple words, it ties Prism and GWT together and makes them available to JavaFX.

**11. Prism –** The graphics of the JavaFX applications are based on the hardware-accelerated graphics rendering pipeline, commonly known as Prism. The Prism engine supports smooth JavaFX graphics that can be executed swiftly when utilized with a backed graphics card or graphics processing unit (GPU). In the situation where the system does not contain the graphic cards, then the prism engine defaults to the software rendering stack. To interpret graphics, a Prism practice −

- DirectX 9 on Windows XP and Vista.
- DirectX 11 on Windows 7.
- OpenGL on Mac and Linux, Embedded Systems.

**12. Glass Windowing Toolkit –** Glass Windowing Toolkit or simply Glass is a platform-dependent layer that assists in connecting the JavaFX platform to the primary operating system (OS). Glass Windowing Toolkit is very useful as it provides services such as controlling the windows, events, timers, and surfaces to the native operating system.

**13. WebView –** JavaFX applications can also insert web pages. To embed web pages, Web View of JavaFX uses a new HTML rendering engine technology known as WebKitHTML. WebView is used to make it possible to insert web pages within a JavaFX application. JavaScript appearing in WebView can call Java APIs and vice-versa. This element promotes different web technologies like HTML5, CSS, JavaScript, DOM, and SVG. Using web view, we can execute the HTML content from the JavaFX application and can also implement some CSS styles to the user interface (UI) part of the application.

**14. Media Engine –** Like the graphics pipeline, JavaFX also possesses a media pipeline that advances stable internet multimedia playback at low latency. This high-performance media engine or media pipeline is based on a multimedia framework known as Gstreamer. By applying the Media engine, the JavaFX application can support the playback of audio and video media files. The package **javafx.scene.media** covers all the classes and interfaces that can provide media functionalities to JavaFX applications.

The foregoing were the components that constitute the architecture of JavaFX.

![[Pasted image 20241127142325.png]]




 