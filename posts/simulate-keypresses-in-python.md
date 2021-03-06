title: "Simulate Keypresses In Python"
date: 2017-12-16
category: YouTube
tags: [Python, Keyboard, pynput]
feature: feature.jpg
description: "This demonstrates how to press keys with Python. Using pynput we are able to simulate key presses into any window. This will show you how to press and release a key, type special keys and type a sentence."

[TOC]

{% with video_id="DTnz8wA6wpw" %}{% include 'blog-post-embedYouTube.html' %}{% endwith %}

## PIP
If you haven't used or setup pip before, go to my tutorial at [how-to-setup-pythons-pip]({{ url_for('blog_post', path='how-to-setup-pythons-pip') }}) to setup pip.

## Installing Pynput
We will be using the punput module to listen to mouse events. To install this module execute ```pip install pynput``` in cmd. Watch the output to make sure no errors have occurred; it will tell you when the module has been successfully installed.

![Installing pynput](/post-assets/how-to-get-mouse-clicks-with-python/pynput1.png)

To double check that it was installed successfully, open up IDLE and execute the command ```import pynput```; no errors should occur.

![Testing pynput](/post-assets/how-to-get-mouse-clicks-with-python/pynput2.png)

## Simulating Keys
Create a new script and save it somewhere so you can easily run the script. Import Key and Controller from pynput.keyboard.

```python
from pynput.keyboard import Key, Controller
```

Make a variable called keyboard and set it to an instance of Controller. Now using the keyboard variable we can press and release keys.

```python
keyboard = Controller()
```

### Pressing and Releasing Keys
Using keyboard.press we can press keys and with keyboard.release we can release a key. This allows us to type a key by pressing and releasing. You can only supply this method with one key at a time. Here is an example of how to type the letter 'a'.

```python
keyboard.press('a')
keyboard.release('a')
```

### Pressing and Releasing Special Keys
For special keys that can't be put into a string like shift or control, you will need to refer to the page [here](https://pynput.readthedocs.io/en/latest/keyboard.html#pynput.keyboard.Key) to look at the Key class for supported keys. Using these in the press or release methods will press/release the key matching it. For example, if I wanted to press the windows key, I would look at [that](https://pynput.readthedocs.io/en/latest/keyboard.html#pynput.keyboard.Key) page for the key. 'cmd' has the description "A generic command button. On PC platforms, this corresponds to the Super key or Windows key, and on Mac it corresponds to the Command key" which is what I am looking for. Now for the code.

```python
keyboard.press(Key.cmd)
keyboard.release(Key.cmd)
```

This method also allows us to press a key while holding another key, for example ctrl+c to copy. To do this we will need to press ctrl, press and release c and then release ctrl.

```python
keyboard.press(Key.ctrl)
keyboard.press('c')
keyboard.release('c')
keyboard.release(Key.ctrl)
```

### Typing Multiple Keys
A cool feature supplied by the class is the type method. This method allows us to type more than one key at a time but it has to be a string of characters. So if we wanted to type "Nitratine" we would execute:

```python
keyboard.type('Nitratine')
```

This method does also support spaces but when it comes to enters, use a new line character (\n) and a tab character (\t) for tabs.

## Common Issues and Questions

### How can I use the keyboard and mouse controllers at the same time?
When you import the classes, Controller will be set to the last one imported. To show what the issue was, ask yourself, what controller did you use to set the mouse and what one to set the keyboard? You would have used the same, but they need to be from the different classes.  So then you should use:
```python
from pynput.keyboard import Key, Controller as KeyboardController
from pynput.mouse import Button, Controller as MouseController
```

Now when you want to use the controller for the mouse use MouseController and KeyboardController for the keyboard.
```
keyboard = KeyboardController()
mouse = MouseController()
```

### ModuleNotFoundError/ImportError : No module named 'pynput'
Did you install pynput? This error will not occur if you installed it properly. If you have multiple versions of Python, make sure you are installing pynput on the same version as what you are running the script with.

### I got a SyntaxError
Syntax errors are caused by you and these is nothing I can offer to fix it apart from telling you to read the error. They always say where the error is in the output using a ^. Generally people that get this issue have incorrect indentation, brackets in the wrong place or something spelt wrong. You can read about SyntaxError on Python's docs [here](https://docs.python.org/2/tutorial/errors.html#syntax-errors).
