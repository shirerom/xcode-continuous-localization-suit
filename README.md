# What is it?

It's a collection of scripts that provide continuous localization for Xcode projects. Storyboards and XIB files will be processed.

`continueLocalization` diffs and patches base strings files with language strings files

* strings which are only existent in base files are copied to language files
* strings which are only existent in language files are deleted from it
* existent strings in language files won't be overwritten

`listDoubleLocalizations` counts and lists appearance of equal strings. 

### ContinousLocalizationStrings.h

A file named `ContinousLocalizationStrings.h` and added to the folder where `*.lproj` are placed will be processed by `continueLocalization`. The header file is meant for global strings.

### Storyboards / XIBs and angle brackets

It often happens that there dynamic labels, text fields and so on with placeholder (for convenience) in IB files. There is no need to translate such placeholders. `continueLocalisation` provides a functionality to omit placeholder from localization. Just put the placeholder text in angle brackets

e.g.: "Label" --> "\<Label\>"

# Why is it?

I needed an easy to use software providing continuous localization and didn't find any ... so I made my own.

# Requirements

* genstrings
* ibtool
* Xcode project with Base Internationalization

# Usage

    cd <Path where *.lproj folders are located>
	continueLocalization

## IMPORTANT

`Base.lproj/Localizable.strings` **MUST** exist, but **MUST NOT** be part of the bundle! Otherwise translations apart from the main language won't work

# License

MIT

Copyright (c) 2015-2016 Johannes Bauer

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
