# libjxtd
A selection of custom controls (widgets) for use with [gammasoft71's C++ xtd gui framework](https://github.com/gammasoft71/xtd).

This library contains a selection of custom controls that I have built for use with [jimoSDR](https://github.com/jimorc/jimoSDR) and possibly other projects. While they are hardly mainstream widgets, they may prove useful to you as they are, you may be able to modify them to your needs, or they may simply show you what is possible with xtd.

# Why I Use xtd
- There is no standard C++ GUI library or framework that works on all desktop/laptop computers, tablets, and smart phones.
  - Each major operating system has one or more GUI libraries, and they are all incompatible with one another: 
     - Microsoft Windows has Win32 API (written in C), MFC, WTL, UWP, C++/CX, and C++/WinRT among others.
     - MacOS has Cocoa.
     - Linux has gtk and Qt.
   - gtk and Qt are two cross-platform GUI libraries/toolkits. The disadvantage to these is that they retain the same look and feel on all operating systems that they support. Not all funcitonality is available on all systems.
   - There are some special purpose, minimalist GUIs based on OpenGL that again do not have native look and feel on all systems. In some cases, they do not match the look and feel of any specific operating system's desktop.
   - A number of attempts have been made to create cross-platform GUI toolkits that retain each system's look and feel. For example:
     - wxWidgets: Development of this toolkit began in the 1990's, before C++98. This is before the C++ standard library was defined, so wxWidgets contains a large number of classes and functions whose functionality is available in the C++ standard library. Because of the necessity to maintain backwards compatibility, wxWidget's API is stuck in the 1990's. The biggest concern to me is the use of naked pointers.
     - nana: A GUI library, not a toolkit or framework. A C++11/14 API.
     - xtd: A C++17/20-based toolkit.
     - several others that are actively supported, or not. I even dabbled a bit in producing one myself, although I did not get very far.
- Advantages of xtd:
  - free and open source (MIT License).
  - a collection of native C++ classes libraries to complete the std.
  - API is close to the .net Winforms API.
  - designed to manage GUI controls (widgets) and dialog in pure native mode or with CSS styles.
  - written in efficient, modern C++17/20 using the RAII programming idiom.
  - highly portable and available on Windows, macOS, Linux, iOS, and Android. Because it is available on Linux, it can
  be ported to the various BSD Unix variants.
  - native look and feel on all supported platforms.
  - currently uses wxWidgets on the backend, but will use native GUI APIs (Win32, Cocoa, and gtk) in future.
  - developer is very quick to address bugs in existing code, and to answer questions.
  - easy to build and install.
  - lots of examples to show how to use the various classes.
  - lots of documentation with links to the examples.
- Disadvantages
  - of course, there are disadvantages as well:
    - under active development, but not nearly complete.
    - mainly a one person project.
    - as is almost always the case, the examples are simplistic, so they don't usually show how to do what you want.

So why do I use xtd? xtd:
- provides a modern, C++17/20 standards compliant interface and uses the latest, recommended idioms, such as RAII.
- is easy to use and has good documentation with examples. 
- is easy to understand, and in general, it is easy to follow what is going on. 
- supports just about anything I want to do. Over the last 30+ years, I have programmed using a number of different GUI toolkits or frameworks, and what I have learned can easily be applied to xtd. 

 