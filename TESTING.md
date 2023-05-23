# **Testing and Validation** 
## **Table of contents:**
---
1. [**During Development Testing**](#during-development-testing)
    * [Manual Testing](#manual-testing)
    * [Bugs and Fixes](#bugs-and-fixes)
2. [**Post Development Testing**](#post-development-testing)
  * [**Validators**](#validators)
    * [HTML](#html---httpsvalidatorw3orgnu)
    * [CSS](#css---httpsjigsaww3orgcss-validator)
  * [**Lighthouse Scores**](#lighthouse-scores)
  * [**Accessibility**](#accessibility)
    *  [Experte]()
    *  [Wave]()

## **During Development Testing**
---
### **Manual Testing
Throughout the development of my project, I manually tested the outcome of my code using the preview option in Codeanywhere using this command in the terminal:
    python3 -m http.server

I shared my deployed site with fellow students in the #peer-code-review channel on Code Institute's Slack community.

My mentor gave me feedback during our planning sessions inlcuding identifying this UX issue I created when I accidentally removed a margin:
![]()

I viewed my website on the following browsers:
1. Chrome
2. Edge
3. Firefox

The DevTools feature in Chrome allowed me to simulate and accomodate screen sizes from 300px upwards.

### ***Bugs and Fixes:***

Here are a sample of the bugs I came across and how I addressed them while developing my site:

1. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
2. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
3. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
4. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
5. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
6. **Goal:** -
    * **Issue:**:
        * 
    * **Solution:** 
        * 
    
## **Post Development Testing**
### **Validators**

#### ***HTML*** - https://validator.w3.org/nu/

* ***Issue Found:***
    * My solution to point 6 of the "During Development Testing" section cause an error because I used a semantic tag ("section") on the community page with no heading. I had originally split the page into three sections leaving the two articles in a section by themselves. 
* ***Solution Used:***
    * I extended the section tag with the ID "ways-to-connect" to include the articles on the page and changed the third section tag containing the two articles into a div element within #ways-to-connect. All pages now return no error.

#### ***CSS*** - https://jigsaw.w3.org/css-validator/

* All pages tested, no issues found via URL or file upload.\
![CSS validator badge](https://jigsaw.w3.org/css-validator/images/vcss)

### **Lighthouse Scores**
### **Test conditions**
* I did all lighthouse tests in incognito mode to avoid interference from browser extensions. 
* I ran the tests for both mobile and desktop. 
* I asked people to run lighthouse tests from their own devices. 
#### ***Desktop Version:***
I have only included one screenshot for desktop as all pages were the same score, only changing by one or two points in performance if I ran it multiple times. 

![Desktop Lighthouse Score](docs/screenshots/lighthouse-desktop.jpg) 

**There were several actions required to get to this score:**

1. The initial SEO score was 90 due to having no Meta description tag in the page head. Once I added this, the score became 100.

1. The best practice score was first 93 and impacted by three factors:
    * Aspect ratio of the images on the teachings page. I fixed this by resizing the images proportionately with the calculator found on https://andrew.hedges.name/experiments/aspect_ratio/.

    * There were some anchor tags on the community page and the form feedback page where the contained text was "here". I changed these anchor texts to a more descriptive text indicating where the links would lead the user.

    * The graphic used as an anchor to download the book Modern Buddhism on index.html was the correct size with no need to specify width and height. However, the best practice scored suggested it should have a height and width specified. I used an extension called pesticide to get the dimension of the image and added these to the CSS file under an ID explicitly created for this element (#modbudd-ebook). Once I added the dimensions best practice score became 100.

1. The performance was 93 on the form feedback page but fluctuating around 93 each time I ran the test. I used https://tinypng.com/ to compress the hero image on this page, which took the score to a minimum of 95 or higher each time I ran the lighthouse test.

#### ***Mobile Version:***

* Due to the more significant variance in the performance score, I have included a screenshot for each mobile page. That being said when I asked one of my testers to check the mobile light house scores from his device his performance scores were all the high nineties.

1. ***index.html:***

    ![Mobile Lighthouse Score for index.html](docs/screenshots/lighthouse-mobile-indx.jpg) 

    * Originally, the performance score on the page was around 83. By using a slightly smaller version of the same hero image, I resolved the issue and maintained the responsiveness up to 4000 px in width.

2. ***teaching:***

    ![Mobile Lighthouse Score for teachings.html](docs/screenshots/lighthouse-mobile-teach.JPG)

3. ***community.html:***

    ![Mobile Lighthouse Score for community.html](docs/screenshots/lighthouse-mobile-comm.JPG) 

4. ***Contact.html:***

    ![Mobile Lighthouse Score for teachings.html](docs/screenshots/lighthouse-mobile-contact.jpg)

    * Best practice score has initially been 98 due to the spacing of the mailing list radio buttons. I added a padding bottom to the top div encasing the first input and label, which solved the issue.
    * The performance score is lower on this mobile page due to the hero image. I already compressed the image twice, which had little impact on the score, and unfortunately, there was no more petite version of the image available. To resolve this in the future, I intend to use GIMP to resize an image. However, it was not a viable solution for this project due to the time already spent on the project, and given I would need to learn GIMP from scratch. 

5.  ***form-feedback.html***

    ![Mobile Lighthouse Score for form-feedback.html](docs/screenshots/lighthouse-mobile-feedback.jpg) 
    * I found the performance score on this page lower due to the embedded video. I discovered this by looking at the original trace in the browser dev tools and saw the pages hero image and content loaded quickly. To test this theory, I removed the link from the iframe, and sure enough, the score increased a few points.

#### ***Lighthouse score Feedback From Third Party Testers***
On the whole all scores reported back from third party testers using the lighthouse tool concurred with my own. One interesting thing that was reported back to me was the following when tested outside of Incognito mode: -
  * The best practice score on the pages with a video embedded dropped to 93 due to a console error. 
    * I was able to replicate this to see the error specified that the set:cookie property on the embedded video was being set automatically by the browser to "lax" due to not being specified in my code. 
    * I reduced this error by using "no-cookie" in the youtube URL. However, I was unable to get rid of it outside of incognito mode completely. This error did not show at all in incognito mode.
    * All documentation found on the set:cookie attribute pointed towards Javascript/API, which was outside of my current knowledge base and the scope requirements for this project. 
    * Since, in reality, the browser was only alerting me that by default, the attribute was now "lax" and there was no user impact, I decided that this was not a bug but a browser feature. This is something I would be looking to fix in the future by replacing the embed url with an API call.
  
### **Accessibility**
In addition to the accessability score on light house I also used [WAVE - Web accessability evaluation tool](https://wave.webaim.org/) to check my pages for accessability and no errors were returned.
***   
[return to README.md](README.md)    * [HTML](#html)
    * [CSS](#css)
    * [Accessibility and Performance](#accessibility-and-performance)
    * [Browser Compatability](#browser-compatability)
    * [Testing User Stories](#testing-user-stories)
    * [Bugs and Fixes](#bugs-and-fixes)### HTML

###
testing throughout
feedback on language UX etc

e.g. success


### CSS
### Accessibility and Performance

Scores

Feedback from lighthouse on colour and names
click here

accordion


### Browser Compatability

### Testing User Stories

### Bugs and Fixes
git push

Initially, when you hovered on a list item on the Tips & Resources page, it would 'jump' and shift elements around it (pushing down the heading underneath for example):
![Hero Image zoom](assets/images/jumping-menu.gif "Jumping Menu before")

The menu after adding a transparent 'invisible' border:
![Hero Image zoom](assets/images/stabilized-menu.gif "Stabilized Menu after")



new color for contact #9a23c6



research click here https://uxmovement.com/content/why-your-links-should-never-say-click-here/