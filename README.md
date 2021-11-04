# Accessibility

Accessibility is essential for developers and organizations that want to create high quality websites and web tools, and not exclude people from using their products and services.
Access to information and communications technologies, including the Web, as a basic human right, but also accessibility support social inclusion for people with disabilities as well as others, such as older people, people in rural areas, and people in developing countries.
There is also a strong business case for accessibility. Accessibility overlaps with other best practices such as mobile web design, device independence, multi-modal interaction, usability, design for older users, and search engine optimization (SEO). Case studies show that accessible websites have better search results, reduced maintenance costs, and increased audience reach, among other benefits. 

 

The World Wide Web Consortium (W3C) is an international community where Member organizations and the public work together to develop Web standards. 

https://www.w3.org/standards/webdesign/accessibility

 

They have create a guideline: Web Content Accessibility Guidelines (WCAG) currently at version 2.2

https://www.w3.org/WAI/standards-guidelines/wcag/

 

#PRINCIPLES of ACCESSIBILITY:

#PERCEIVABLE
1.1 Text Alternatives
1.2 Time-Based Media
1.3 Adaptable
1.4 Distinguishable

#OPERABLE
2.1 Keyboard Accessible
2.2 Enough Time
2.3 Seizures and Physical Reactions
2.4 Navigable
2.5 Input Modalities

#UNDERSTANDABLE
3.1 Readable
3.2 Predictable
3.3 Input Assistance

#ROBUST
4.1 Compatible

 

#PRINCIPLES EXPLAINED:
#1.1 TEXT ALTERNATIVES
all non-text content has a text alternative. ex:

on images always have alt

captcha image can’t have the alt but maybe add the audio option, so people with visual impediment can listen to it

#1.2 TIME-BASED MEDIA
To have alternative options for time based media, ex:

Video with close captions that not only write the dialog but also describes the sound for context + audio description

#1.3 ADAPTABLE
Content can be presented in different ways without losing context, ex:

mobile, rotating device: different for different format

#1.4 DISTINGUISHABLE
content can be separated from background

Contrast Ratio: Easily calculate color contrast ratios. Passing WCAG was never this easy! 

colors: 4.5 contrast most text, large text can have 3
audio: background music should be 20 decibels quieter than speaking voice

 

#2.1 KEYBOARD ACCESSIBLE
All parts of a website can be accessible using a keyboard

by default the button element is clickable and accordion works with only keyboard


if we are using only div then we would still be able to click but it would not be keyboard accessible 


to solve this and make the element equivalent to a button from an accessibility point of view, so that you can tab on it basically, you add role='button' and tabindex='0'

 

+ links: if you need to have a function/action need to use buttons and links only for links (from an accessibility point of view)


#2.2 ENOUGH TIME
People are given enough time to use the content on your website, ex:

video need to have controls (so user can pause and play the video at their time) + animations that last more than 5s (they can be distracting)

pages that have sensitive information and have sessions that expire like banking or forms, need to give user a reasonable time, a warnings and chance to cancel the logout

#2.3 SEIZURES AND PHYSICAL REACTIONS
Animations and video should not flash more than 3 times per second

#2.4 NAVIGABLE
user can navigate + understand where they are

focus and outline css

unique titles for each of their pages

breadcrumb

table of content

#2.5 INPUT MODALITIES
all parts of a website can be accessed using other input devices besides a keyboard

 

#3.1 READABLE
Content is readable and easy to understand
Use simple language and avoid jargon hen possible

abbreviations should be in tag <abbr> with title explaining the abbreviations
```rd
<html lang="en"> 
 ```
 
 important to have the lang! so that screen readers will know the language used, when having text in other languages in the page then wrap it up in a span with tag lang 



#3.2 PREDICTABLE
predictable in how they appear and operate, consistence between pages to avoid mistakes

#3.3 INPUT ASSISTANCE

help the user suggesting how to field the data with labels or placeholders

 


and colors and text to help individuate the error and correct it

 

 

#4 ROBUST - COMPATIBLE
work with different technologies:
use valid HTML + ARIA to extend HTML

 
#CHECKLIST
 
Developer checklist:
Do all images have meaningful alternative text?

Is every focusable element operable using the keyboard alone?

Is there a consistent visible focus indicator when navigating using the keyboard?

Have all controls, frames, and page titles been labeled meaningfully and uniquely?

If custom controls/components have been implemented, have these been tested to assure that assistive technology recognizes name, role, state, and value (where applicable)?

Have custom controls/components been verified to work as expected using assistive technology, such as a screen reader?

Are error messages interpretable by assistive technology?

Do you have sufficient foreground and background color contrast?

Have captions been included with any audio or audio/visual media?

Designer checklist:
Do I have sufficient contrast between text and my background?

Do I have sufficient contrast between UI elements and my background?

Are there any places where I’m color or other visual means alone to indicate something (ie, no text equivalent)?

Is my written content simple and easy to understand?

Are there any cases where the screen is flashing or flickering?

Does every mouse interaction have a keyboard-only equivalent interaction?

Have captions been included with any audio or audio/visual presentation?

If any interaction involves a timed response or session timeout, is this communicated well?

link to other tips on writing core for accessibility and source where I got the checklist:

Teach Access Portal  
https://teachaccess.github.io/tutorial/#/2
 

#RESOURCES

Powermapper (SortSite)

SortSite checks any website for broken links, spelling errors, browser compatibility, accessibility, web standards validation and search engine issues.


LIGHTHOUSE (on chrome)

Open-source automated tool for improving the quality of the web pages.


#Other free tools:

WAVE by WebAIM for general website accessibility: http://wave.webaim.org/ 

Juicy Studio’s Readability Test: http://juicystudio.com/services/readability.php 

Vischeck’s Color Blindness Checker: http://www.vischeck.com/ 

Color contrast check: https://contrast-ratio.com/  

 

#FINAL THOUGHTS
challenges? most seen scenes when working with accessibility?

what I have seen:

OUTLINE removed from css
always need to have it or find a way around, 3 solutions:
1 style the outline, instead of using the default, but still need to be within limits, ex contrast
2 style the element itself (focus element has different style than not focused element)
3 remove outline for mouse user only 

```rd
[data-whatintent='mouse'] *:focus {
  outline: none;
}
 ```
SEARCH input need a label
encountered this before and just added a hidden label

```rd
<form role='search' action="/" method="get">
  <label for='header-search'>
    <span class='visually-hidden'>Search</span>
  </label>
  <input type='text' id='header-search'/>
  <button type='submit'>
    <span class='visually-hidden'>Submit Search</span>
  </button>
</form>
 ````
IFRAMES could be real pickles, always have the title

SLIDER dots and arrows, usually just increase size & change colors

VIDEO when they play more than 5 second they need the pause button. I have seen video as background or on slider longer than that without the possibility to pause and that is an issue for accessibility. Either shorter video or show the commands

Content added with CSS, for example for slider arrows, material icons or other commands, usually adding a text on the html before it get replaced or a hidden label or aria label will fix it.

CAPTCHA
