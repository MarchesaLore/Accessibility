# Accessibility

Accessibility is essential for developers and organizations that want to create high quality websites and web tools, and not exclude people from using their products and services.
Access to information and communications technologies, including the Web, as a basic human right, but also accessibility support social inclusion for people with disabilities as well as others, such as older people, people in rural areas, and people in developing countries.
There is also a strong business case for accessibility. Accessibility overlaps with other best practices such as mobile web design, device independence, multi-modal interaction, usability, design for older users, and search engine optimization (SEO). Case studies show that accessible websites have better search results, reduced maintenance costs, and increased audience reach, among other benefits. 

 

The World Wide Web Consortium (W3C) is an international community where Member organizations and the public work together to develop Web standards. 

https://www.w3.org/standards/webdesign/accessibility

 

They have create a guideline: Web Content Accessibility Guidelines (WCAG) currently at version 2.2

https://www.w3.org/WAI/standards-guidelines/wcag/

<h1>PRINCIPLES of ACCESSIBILITY:</h1>
<h3 class="a1">PERCEIVABLE</h3>
<a href="#1.1" class="a1">1.1 Text Alternatives</a><br/>
<a href="#1.2" class="a1">1.2 Time-Based Media</a><br/>
<a href="#1.3" class="a1">1.3 Adaptable</a><br/>
<a href="#1.4" class="a1">1.4 Distinguishable</a><br/>

<h3 class="a2">OPERABLE</h3>
<a href="#2.1" class="a2">2.1 Keyboard Accessible</a><br/>
<a href="#2.2" class="a2">2.2 Enough Time</a><br/>
<a href="#2.3" class="a2">2.3 Seizures and Physical Reactions</a><br/>
<a href="#2.4" class="a2">2.4 Navigable</a><br/>
<a href="#2.5" class="a2">2.5 Input Modalities</a><br/>

<h3 class="a3">UNDERSTANDABLE</h3>
<a href="#3.1" class="a3">3.1 Readable</a><br/>
<a href="#3.2" class="a3">3.2 Predictable</a><br/>
<a href="#3.3" class="a3">3.3 Input Assistance</a><br/>

<h3 class="a4">ROBUST</h3>
<a href="4.1" class="a4">4.1 Compatible</a><br/>



<h1 id="PRINCIPLESex">PRINCIPLES EXPLAINED:</h1>
<h3 id="1.1" class="a1">1.1 TEXT ALTERNATIVES</h3>
<p>
all non-text content has a text alternative, example on file: 11TextAlternatives.html
    
CAPTCHA<br/>
google supports captcha with sound
https://support.google.com/recaptcha/answer/6175971?hl=en
</p>

<h3 id="1.2" class="a1">1.2 TIME-BASED MEDIA</h3>
<p>
To have alternative options for time based media, ex:
Video with close captions that not only write the dialog but also describes the sound for context + audio description

</p>

<h3 id="1.3" class="a1">1.3 ADAPTABLE</h3>
<p>
Content can be presented in different ways without losing context, ex:<br/>
mobile, rotating device: different for different format
    
</p>

<h3 id="1.4" class="a1">1.4 DISTINGUISHABLE</h3>
<p>    
    COLOR + RESIZE TEXT
content can be separated from background, different type of text (headers, content) or buttons have different requirements, generically a 4.5 works for reaching a Level A with buttons/anchors: headers, navigation, controls, content.. some large text 3 can work.

here is a tool I used before:
https://webaim.org/resources/contrastchecker/ 
just need to set the background color and text color:
 ![image](https://user-images.githubusercontent.com/22336407/140417205-c352cf08-d11e-4ca1-a0e3-92545874c642.png)

another useful tool:
https://contrast-ratio.com/ 

 

hover and focus effect to give feedback to the user 
hover is important when using the tab (keyboard access) so make sure to leave in the hover effect! or if the client ask to remove it remove it only for the mouse:
 
```rd
[data-whatintent='mouse'] *:focus {
  outline: none;
}
 ```
 

If any audio on a Web page plays automatically for more than 3 seconds, either a mechanism is available to pause or stop the audio, or a mechanism is available to control audio volume independently from the overall system volume level.

Also less used from us but to keep in mind, same role works with audio: background music should be 20 decibels quieter than speaking voice.
    
</p>

<h3 id="2.1" class="a2">2.1 KEYBOARD ACCESSIBLE</h3>
 <p>
 All parts of a website can be accessible using a keyboard example on file 2.1KeyboardAcc.html
    
 </p>
<h3 id="2.2" class="a2">2.2 ENOUGH TIME</h3>
 <p>
People are given enough time to use the content on your website, ex:

video need to have controls (so user can pause and play the video at their time) + animations that last more than 5s (they can be distracting)

pages that have sensitive information and have sessions that expire like banking or forms, need to give user a reasonable time, a warnings and chance to cancel the logout

 but also see this example for the slider with pause and play buttons
 https://github.com/MarchesaLore/SlickSliderPausePlay
 
 </p>
 <h3 id="2.3" class="a2">2.3 SEIZURES AND PHYSICAL REACTIONS</h3>
<p>Animations and video should not flash more than 3 times per second</p>
  <h3 id="2.4" class="a2">
    2.4 NAVIGABLE</h3>
   <p>
       

user can navigate + understand where they are

focus and outline css

unique titles for each of their pages

breadcrumb

table of content
   </p>
   <h3 id="2.5" class="a2">2.5 INPUT MODALITIES</h3>
<p>all parts of a website can be accessed using other input devices besides a keyboard
</p>


<h3 id="3.1" class="a3">3.1 READABLE</h3>
Content is readable and easy to understand
 Use simple language and avoid jargon hen possible
 abbreviations should be in tag &lt;abbr&gt; with title explaining the abbreviations
```rd
<html lang="en">
```
important to have the lang! so that screen readers will know the language used, when having text in other languages in the page then wrap it up in a span with tag lang 
    
<h3 id="3.2" class="a3">3.2 PREDICTABLE</h3>
predictable in how they appear and operate, consistence between pages to avoid mistakes


<h3 id="3.3" class="a3">3.3 INPUT ASSISTANCE</h3>

help the user suggesting how to field the data with labels or placeholders
and colors and text to help individuate the error and correct it


<h3 id="4.1" class="a4">4 ROBUST - COMPATIBLE</h3>
work with different technologies:
use valid HTML + ARIA to extend HTML



 





<h1>CHECKLIST</h1>

<h4>Developer checklist:</h4>

<ul>
<li>Do all images have meaningful alternative text?
</li>
<li>Is every focusable element operable using the keyboard alone?
</li>
<li>Is there a consistent visible focus indicator when navigating using the keyboard?
</li>
<li>Have all controls, frames, and page titles been labeled meaningfully and uniquely?
</li>
<li>If custom controls/components have been implemented, have these been tested to assure that assistive technology recognizes name, role, state, and value (where applicable)?
</li>
<li>Have custom controls/components been verified to work as expected using assistive technology, such as a screen reader?</li>
<li>Are error messages interpretable by assistive technology?</li>
<li>Do you have sufficient foreground and background color contrast?</li>
<li>Have captions been included with any audio or audio/visual media?</li>
</ul>


<h4>Designer checklist:</h4>

<ul>
    <li>Do I have sufficient contrast between text and my background?</li>
 <li>Do I have sufficient contrast between UI elements and my background</li>
 <li>Are there any places where I’m color or other visual means alone to indicate something (ie, no text equivalent)?
    </li><li>Is my written content simple and easy to understand?
    </li><li>Are there any cases where the screen is flashing or flickering?
    </li><li>Does every mouse interaction have a keyboard-only equivalent interaction?
    </li><li>Have captions been included with any audio or audio/visual presentation?    
    </li><li>If any interaction involves a timed response or session timeout, is this communicated well?
    </li>
</ul>

link to other tips on writing core for accessibility and source where I got the checklist: 
https://teachaccess.github.io/tutorial/#/2


<h1>RESOURCES</h1>

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
