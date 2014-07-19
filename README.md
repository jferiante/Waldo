## Waldo (Current Version: 0.4)

Waldo is a port of TextMate's Find-in-Project feature, designed to work with [MacVim.app](https://github.com/b4winckler/macvim)

![Waldo Screenshot](https://github.com/jtaby/Waldo/raw/master/resources/waldo_shot.png)

### [Screencast Demo](https://github.com/jtaby/Waldo/raw/master/resources/waldo_demo.mov)

The original developer of this plugin has been inactive for a few years. Here's what I had to do to get this working (in addition to his original instructions below). Note: my latest update makes this plugin compatible with pathogen (but you must still install the Waldo app first as explained below).

**1-Install Xcode**<br>
First, to build this, you'll be forced to use XCode 5.0.1 or older. (5.1 disallows garbage collection & this app uses it, so you can't use Xcode 5.1.X). <br>
If you have the latest version of Xcode like me, you'll need instructions like this on how to install multiple versions of Xcode at once: http://iosdevelopertips.com/xcode/download-and-install-older-versions-of-xcode-xcode-previous-releases.html<br>
Here's where apple has old versions of Xcode:<br>
https://developer.apple.com/downloads/index.action

**2-Build the project (open Waldo.xcodeproj in Xcode and hit the "play" button)**<br>
Most likely the app will be here: `~/Library/Developer/Xcode/DerivedData/Waldo-<hash>`<br>
My compiled `Waldo.app` was in this directory: `~/Library/Developer/Xcode/DerivedData/Waldo-<hash>/Build/Products/Debug`

**3-If you get the "macruby.h file not found" error**<br>
add `/Library/Frameworks` to “Framework Search Paths" in the project settings<br>
Add a symbolic link to help Xcode find the MacRuby.framework
`cd /Applications/Xcode.app/Contents/Developer/Library/Frameworks`
`sudo ln -s /Library/Frameworks/MacRuby.framework MacRuby.framework`

Once you have a Waldo.app to install you can continue with the instructions below.

## Usage

- Download Waldo.zip and put the .app in your Applications folder
- Launch Waldo.app to install the Vim plugin
- Open MacVim.app and trigger Waldo using the `<leader>f` mapping.
  
**NOTE**: `<leader>` is a programmable prefix for commands. By default, it's '\' (backslash), though you can change it in your .vimrc file.
	
*NOTE:* If you do not have your `.vim/` folder in your home directory, you must manually place Waldo.vim (found inside the .app package) in your `.vim/plugins` directory.
	
*NOTE:* Make sure you `cd` into directory you want to search.

## Changelog

### Version 0.4
- Fix crashes introduced in 0.2
- Rename "literal match" to "regex"
- Rename "case sensitive" to "ignore case"
- Code Refactoring
- Opening Waldo without specifying a project path in the command line will present an "Open" dialog
- Launch as menu item only
- Thanks to [alloy](http://twitter.com/alloy) for helping!

### Version 0.3
- Rename project to Waldo (previously known as VimAck)
- Auto-install vim plugin on first launch (thanks zef)
- Add support for case-sensitive searches (thanks zef)
- Add support for regex searches (thanks zef)
- Launch Waldo as a menu item (thanks ashchan)

### Version 0.2
- Perform ack subprocess on a separate thread
- Support for Sparkle.framework to ship updates automatically
- Prevent multiple instances of Waldo to open when you trigger `<leader>f`

## Roadmap

### Version 0.5
- Add history to search field
- Add ignore-directories feature
- Keyboard navigation

## Contributing

I highly encourage you to fork my project and implement any of the features in the Roadmap. Just submit a pull request and be sure to give yourself credit here!

### Contributors
- [Zef Houssney](http://madebykiwi.com)
- [James Chen](http://ashchan.com)
- [Martin Schürrer](http://github.com/MSch)

## License

	Copyright (C) 2011 by Majd Taby

	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:

	The above copyright notice and this permission notice shall be included in
	all copies or substantial portions of the Software.

	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
	THE SOFTWARE.
