# HTML part b

[<- Home](README.md)

### Inputs
* The **input** element is used to create interactive controls for web-based forms in order to accept data from the user
* How it works varies considerably depending on the value of its `type attribute`
* If this attributes is not specified, the `default` type adopted is `text`
* The available types are as follows: button, checkbox, color, date, datetime-local, email, file, hidden, image, month, number, password, range, reset, search, submit, tel, text, time, url, week
* [MDN input doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

**Example:**
```html
<form>
  <input type="input-type" name="variable-name" >
</form>
```

#### Text
* Create basic single-line text fields (name, lastname, username, address)
* Use the type value of `text` to define this type of input
* You must remember to include name attribute on the **input** element, otherwise the text field's value won't be included with the submitted data
* [MDN input type text doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/text)

**Example:**
```html
<form>
  <input type="text" name="username" >
</form>
```

* The `value` attribute contains the value of the text input
* The user will see any predefined value
* To clear the input the user will have to manually delete the input content

**Example:**
```html
<input type="text" name="username" value="harryp" >
```

* The `placeholder` attribute is typically rendered in a lighter color than the element's foreground color, and automatically vanishes when the user begins to enter text into the field

**Example:**
```html
<input type="text" name="username" placeholder="Please input a username" >
```

* The **size** attribute specified the number of characters the text input can display at a time
* This affects the width of the element, letting you specify the width in terms of characters rather than pixels
* As it's only a visual effect we can update it with CSS

**Example:**
```html
<input type="text" name="username" value="harryp" size="20" >
```

* You can specify a minimum length (in characters) for the entered value using the `minlength` attribute
* Similarly, use `maxlength` to set the maximum length of the entered value, in characters

**Example:**
```html
<input type="text" name="username" value="harryp" minlength="3" maxlength="20">
```

* If you try to submit the form with less than 4 characters, you'll be given an appropriate error message (which differs between browsers). 
* If you try to enter more than 8 characters, the browser won't let you.
* If you specify a `minlength` but do not specify `required`, the input is considered valid, since the user is not required to specify a value

#### Password
* The input type passowrd provide a way for the user to securely enter a password 
* The element is presented as a one-line plain text editor control in which the text is obscured so that it cannot be read, usually by replacing each character with a symbol such as the asterisk ("*") or a dot ("•")
* Set the type attribute to password
* We can use the **name**, **value**, **size**, **minlength** & **maxlength** attributes
* Remember that this hidden text is just a visual effect
* Use HTTPS to send client data to the server
* [MDN input type password doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/password)

**Example:**
```html
<form>
  <input type="password" name="pass" >
</form>
```

#### Submit button
* The input type `submit` is just a button that submits the form
* This type of element's value attribute contains the button's label
* If you don't specify a value, the button will have a default label, chosen by the user agent
* [MDN input submit doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/submit)

**Example:**
```html
<form>
  <input type="submit" value="Submit this form">
</form>
```

#### Practice
[Exercise 11](exercises/html/ex_11.md)

### Labels
* The **label** element represents a caption for an item in a user interface
* A **label** can be associated with a control either by placing the control element inside the **label** element, or by using the for attribute
* Such a control is called the labeled control of the label element
* One input can be associated with multiple labels
* [MDN label doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)

**Example:**
```html
<form>
  <label>Name:</label>
  <input type="text" name="name" />
  <label>Surname:</label>
  <input type="text" name="surname" />
</form>
```

* Also we could use it this way:

**Example:**
```html
<form>
  <label>
    Name:
    <input type="text" name="name" />
  </label>
  <label>
    Surname:
    <input type="text" name="surname" />
  </label>
</form>
```

* The label element has a **for** attribute
* Once we set the **for** attribute, the user will be able to click on the **label** element to get focus in the set **for** value
* The id of a label form-related element in the same document as the label element.
* The first such element in the document with an ID matching the value of the for attribute is the labeled control for this label element

**Example:**
```html
<form>
  <label for="nameid">Name:</label>
  <input type="text" name="name" id="nameid" />
  <label for="surnameid">Surname:</label>
  <input type="text" name="surname" id="surnameid" />
</form>
```

### Fieldset
* The **fieldset** element is used to group several controls as well as labels within a web form
* [MDN fieldset doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset)

**Example**
```html
<form>
  <fieldset>
    <label>Name:</label>
    <input type="text" name="name" />
    <label>Surname:</label>
    <input type="text" name="surname" />
  </fieldset>
</form>
```

* The **legend** element represents a caption for the content of its parent **fieldset**

**Example**
```html
<form>
  <fieldset>
    <legend>User Form</legend>
    <label>Name:</label>
    <input type="text" name="name" />
    <label>Surname:</label>
    <input type="text" name="surname" />
  </fieldset>
</form>
```

#### Radio buttons
* The `input type radio` elements are generally used in radio groups—collections of radio buttons describing a set of related options
* Only one radio button in a given group can be selected at the same time
* Radio buttons are typically rendered as small circles, which are filled or highlighted when selected
* To define a radio group each of the radio buttons in the group must have same name attribute
* The user will see a legend next to each radio button by using a label element or just plain text
* [MDN input type radio doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/radio)

**Example**
```html
<form>
  Are you a Riders Fan?
  <input type="radio" name="ridersfan" value="true"> Oh Yeahhhhhh, Go Riders!!!
  <input type="radio" name="ridersfan" value="false"> No
</form>
```

* Use the `checked` attribute with a `checked` value to select the default selected value
* In HTML5 when the attribute name and value is the same we can just add the attribute `checked`

**Example**
```html
<form>
  Are you a Riders Fan?
  <input type="radio" name="ridersfan" value="true" checked="checked"> Oh Yeahhhhhh, Go Riders!!!
  <input type="radio" name="ridersfan" value="false"> No
  <!-- <input type="radio" name="ridersfan" value="true" checked> Oh Yeahhhhhh, Go Riders!!! -->
</form>
```

#### Checkboxes
* The input elements of `type checkbox` are rendered by default as square boxes that are checked (ticked) when activated
* They allow you to select single values for submission in a form (or not).
* Radio buttons are similar to checkboxes, but with an important distinction:
> radio buttons are grouped into a set in which only one radio button can be selected at a time, whereas checkboxes allow you to turn single values on and off. Where multiple controls exist, radio buttons allow one to be selected out of them all, whereas checkboxes allow multiple values to be selected.
* To select multiple values we need to use the same name input
* Use the value attribute to set each input selected value
* The checked attribute and value works the same way as radio buttons
* [MDN input type checkbox doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/checkbox)

**Example**
```html
<form>
  Select your favourite Harry Potter wizards
  <input type="checkbox" name="wizards" value="harry potter" checked="checked" > Harry Potter
  <input type="checkbox" name="wizards" value="hermione granger" checked> Hermione Granger
  <input type="checkbox" name="wizards" value="ron weasley"> Ron Weasley
  <input type="checkbox" name="wizards" value="aberforth dumbledore"> Aberforth Dumbledore
</form>
```

### Hidden
* The input elements of `type hidden` let web developers include data that cannot be seen or modified by users when a form is submitted
* A good example: the ID of the content that is currently being ordered or edited, or a unique security token 
* Hidden inputs are completely invisible in the rendered page, and there is no way to make it visible in the page's content
* A user will be able to see them on the source code

**Example:**
```html
<form>
  <input type="hidden" name="product-id" value="1" >
</form>
```

#### Image buttons
* The input elements of `type image` are used to create graphical submit buttons
* We can use a button image instead of the default submit one
* To define the image we use the **src** attribute (as the image element)
* [MDN input type image doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/image)

**Example:**
```html
<form>
  <input type="image" src="create_user_button.png" >
</form>
```

* To change the image size we can use the **height** & **width** attributes
* We'll use CSS to change the way elements have to look (friendly reminder)

#### Practice
[Exercise 12](exercises/html/ex_12.md)

### Text area
* The **textarea** element represents a multi-line plain-text editing control
* This element has an opening and close tag
* [MDN input textarea doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)

**Example**
```html
<textarea name="about">Rick Sanchez it's a great scientific..</textarea>
```

* Use the **placeholder** attribute to let the user know what to input

**Example**
```html
<textarea name="about" placeholder="Please let us know about yourself"></textarea>
```

* The **cols** attribute sets the textarea amount of columns
* The **rows** attribute sets the textarea amount of lines

**Example**
```html
<textarea name="about" cols="10" rows="2" >Initial textarea text!</textarea>
```

### Select
* The **select** element represents a control that provides a menu of options
* The **option** element is used to define an item contained in a **select** element
* As such, **option** can represent menu items in popups and other lists of items in an HTML document
* [MDN input select doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select)
* [MDN input option doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)

**Example**
```html
<form>
  <select name="options">
    <option>First Item</option>
    <option>Second Item</option>
  </select>
</form>
```

* The **option** element uses a **value** attribute to define the value the user selects
* Also we can show the user a different text as an **option** content

**Example**
```html
<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can">Canada</option>
  </select>
</form>
```

* We can use the **selected** attribute to select the default selected value
* This attribute uses the **selected** value and is the same attribute name we can just use the attribute name without a value (example: selected="selected")
* By default the first option is going to be selected

**Example**
```html
<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected="selected">Canada</option>
  </select>
</form>

OR

<form>
  <select name="countries">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected>Canada</option>
  </select>
</form>
```

* The **multiple** attribute will allow the user to select multiple options
* The **size** attribute configures the number o items we'll show at the same time
* To select many items we'll use the control key

**Example**
```html
<form>
  <select name="countries" multiple="multiple" size="4">
    <option value="">Please select a Country</option>
    <option value="arg">Argentina</option>
    <option value="bra">Brasil</option>
    <option value="chl">Chile</option>
    <option value="can" selected>Canada</option>
  </select>
</form>
```

### Buttons
* The **button** element represents a clickable button, which can be used in forms, or anywhere in a document that needs simple, standard button functionality
* To set the button content we need to use an opening and close tags
* Add the **value** attribute if you need to submit this element value
* [MDN button doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)

**Example**
```html
<form>
  <button value="create" name="create-user">+ User</button>
</form>
```

* We can add any html content like an image

**Example**
```html
<form>
  <button>
    <img src="plus-icon.png" alt="plus icon" />
    User
  </button>
</form>
```

#### File 
* The **file** input type is a control that lets the user select a file
* Use the accept attribute to define the types of files that the control can select
* As we're going to be submitting more than just text we need to change the form enctype to enctype="multipart/form-data" and use the post method
* By default we can only select one file
* Use the **multiple** attribute indicates whether the user can enter more than one value (only HTML5 and all browsers might not support it)
* [MDN input type file doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/file)

**Example**
```html
<form action="upload.php" method="post" enctype="multipart/form-data">
  <input type="file" name="filename" />
  <input type="file" name="filename" multiple="multiple" />
  <input type="file" name="filename" multiple />
</form>
```

#### Practice
[Exercise 13](exercises/html/ex_13.md)

#### New HTML5 input types
* HTML5 adds some new specific inputs
* If the browser doesn't support them it will show an input type text element
* [HTML5 forms input types](http://html5doctor.com/html5-forms-input-types/)
* [See them in action](https://robertnyman.com/html5/forms/input-types.html)

##### Date
* The input `type date` is a control for entering a date (year, month, and day, with no time)
* We can set a initial value using the **value** attribute
* [MDN input type date doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date)

**Example**
```html
<form>
  <input type="date" name="birthday" />
  <input id="date" type="date" value="1980-04-02">
</form>
```

##### Email
* The input `type email` is a field for editing an e-mail address
* [MDN input type email doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/email)

**Example**
```html
<form>
  <input type="email" name="email" />
</form>
```

##### URL
* The input `type url` is a field for entering a URL
* [MDN input type url doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/url)

**Example**
```html
<form>
  <input type="url" name="personalsite" />
</form>
```

##### Search
* The input `type search` is a single-line text field for entering search strings
* Line-breaks are automatically removed from the input value

**Example**
```html
<form>
  <input type="search" name="query" />
</form>
```

#### Practice
[Exercise 14](exercises/html/ex_14.md)


### Form validation
* To make sure that the data users fill out in forms is in the correct format we need to process the form inputs
* We can validate on client and server side
* We'll use some HTML elements attribute to validate our forms on the client side
* If we validate on the client side we avoid sending wrong data to the server so we have many requests
* HTML5 added element validations
* Also we can use JavaScript to validate our inputs too

#### Required
* The **required** attribute specifies that the user must fill in a value before submitting a form
* As it's a boolean attribute we can just write the attribute name without any value (required="required" or just required)
* The form won't submit until all required inputs are completed

**Example**
```html
<form>
  <input type="text" name="name" required />
  <input type="text" name="name" required="required" />
</form>
```

#### Regex
* A regular expressions is a pattern used to match character combinations in strings
* We can use them in many different languages
* The attribute **pattern** allows us to enter a valid regex as value
* This regular expression will be executed with the input value to see if it match
* The pattern must match the entire value
* This attribute applies when the value of the type attribute is text, search, tel, url, email, or password, otherwise it is ignored
* The regular expression language is the same as JavaScript RegExp algorithm
* The pattern is not surrounded by forward slashes
* It's a good practice to add the **title** attribute to explain the allowed values
* Add the placeholder if you use this attribute or it might not show the title content
* [Wikipedia - Regular_expression](https://en.wikipedia.org/wiki/Regular_expression)
* [Nice regex tutorial](https://regexone.com)

**Example**
```html
<form>
  <input type="text" name="name" pattern="^[a-zA-Z]+$" placeholder="name" title="Input only letters" /> 
  <input type="text" name="age" pattern="\d+" placeholder="age" title="Input only numbers" />
  <input type="submit" value="Submit">
</form>
```

* Use [caniuse.com](http://caniuse.com/#search=required) to find out if a feature is compatible with the browser you're targeting
* To know more about this subject you can read the [MDN form validation guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms/Form_validation)

## HTML5 new sections
*  HTML5 specification brings several new elements to web developers allowing them to describe the structure of a web document with standard semantics
* All content lying inside the **body** element is part of a section
* Sections in HTML5 can be nested
* Each section can have its own heading hierarchy. Therefore, even a nested section can have an **h1**
* HTML5 adds the following features:
  * Semantics: allowing you to describe more precisely what your content is
  * Connectivity: allowing you to communicate with the server in new and innovative ways
  * Offline and storage: allowing webpages to store data on the client-side locally and operate offline more efficiently
  * Multimedia: making video and audio first-class citizens in the Open Web
  * 2D/3D graphics  and effects: allowing a much more diverse range of presentation options
  * Performance and integration: providing greater speed optimization and better usage of computer hardware
  * Device access: allowing for the usage of various input and output devices
  * Styling: letting authors write more sophisticated themes
* [MDN HTML5 guide](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5)

* In the semantics section we find new outlining and sectioning elements like **section**, **article**, **nav**, **header**, **footer** and **aside**. 

* The **header** element represents introductory content, typically a group of introductory or navigational aids
* It may contain some heading elements but also other elements like a logo, a search form, an author name, and so on
* The **nav** element represents a section of a page whose purpose is to provide navigation links, either within the current document or to other documents
* The **aside** element represents a portion of a document whose content is only indirectly related to the document's main content
* The **section** element represents a standalone section — which doesn't have a more specific semantic element to represent it — contained within an HTML document
* The **footer** element represents a footer for its nearest sectioning content or sectioning root element
* A footer typically contains information about the author of the section, copyright data or links to related documents

**Example**
```html
<body>
  <header>
    <h1>Title of our document</h1>
  </header>
  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="bio.html">Bio</a></li>
    </ul>
  </nav>
  <aside>
    <p>Aside Content</p>
  </aside>
  <section>
    <h1>Section Main Title</h1>
    <p>Section Content</p>
  </section>
  <footer>
    <p>Site Footer</p>
  </footer>
</body>
```

* The *article element represents a self-contained composition in a document, page, application, or site, which is intended to be independently distributable or reusable. Examples include: a forum post, a magazine or newspaper article, or a blog entry
* The **address** element indicates that the enclosed HTML provides contact information for a person or people, or for an organization
* The HTML **time** element represents one of the following: a time on a 24-hour clock or a precise date in the Gregorian calendar

**Example**
```html
<body>
  <article>
    <p>Author Name</p>
    <time>02/02/2017</time>
    <address>
      136 Market Av.
    </address>
  </article>
</body>
```

## Iframe
* The **iframe** element represents a nested browsing context, effectively embedding another HTML page into the current page
* The **src** attribute accepts the URL of the page to embed as value
* Use the **height** & **width** attributes to set the iframe size
* The **seamless** is a boolean attribute indicates that the browser should render the inline frame in a way that makes it appear to be part of the containing document
* The **frameborder** attribute tells the browser to draw a border between this frame. If we set the value to 0 tells the browser not to draw a border between this frame
* [MDN iframe doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)

**Example**
```html
<body>
  <iframe src="other_document.html" height="200" width="200" seamless frameborder="0"></iframe>
</body>
```

#### Practice
[Exercise 15](exercises/html/ex_15.md)

## Video
* The **video** element embeds a media player which supports video playback into the document
* This element contains one or more video sources
* To specify a video source, use either the **src** attribute or the **source** element (the browser will choose the most suitable one)
* Different browsers might support different media types
  * H264: Internet Explorer & Safari
  * WebM: Android, Chrome, Firefox and Opera
* For a list of supported formats you can see the [MDN supported media formats guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats)
* Each browser will show the player in a different way
* Also we can still use flash plugin to reach more users
* This are some of the attributes that we can use to configure the video element
  * **src:** set this value with the video filename or path
  * **width:** & **height:** to set the video player size
  * **poster:** we can set a picture file or path that will show while the video is downloaded
* [MDN video doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

**Example**
```html
<body>
  <video src="myvideo.mp4" poster="myvideo.jpg" width="600" height="400">
    <p>Video description</p>
  </video>
</body>
```

* The video element has many attributes that works as a boolean value to turn on/off the different features
  * **controls:** if this attribute is present, the browser will offer controls to allow the user to control video playback, including volume, seeking, and pause/resume playback
  * **autoplay:** if specified, the video automatically begins to play back as soon as it can do so without stopping to finish loading the data
  * **loop:** upon reaching the end of the video the player automatically seek back to the start
  * **preload:** This enumerated attribute is intended to provide a hint to the browser about what the author thinks will lead to the best user experience.
    * It may have one of the following values:
      * **none:** indicates that the video should not be preloaded
      * **auto:** indicates that the whole video file could be downloaded, even if the user is not expected to use it
      * **metadata:** indicates that only video metadata (e.g. length) is fetched
      * **An empty string**: synonym of the auto values

**Example**
```html
<body>
  <video 
    src="myvideo.mp4" 
    poster="myvideo.jpg"
    width="600" 
    height="400"
    controls
  >
    <p>Video Description</p>
  </video>
</body>
```

## Audio
* The **audio** element is used to embed sound content in documents
* It may contain one or more audio sources, represented using the src attribute or the **source** element: the browser will choose the most suitable one 
* It can also be the destination for streamed media, using a MediaStream
* This element works in a similar way as the **video** one
* The **audio** element supports the same attribute video does: **src**, **controls**, **autoplay**, **preload** & **loop**
* Some browsers have better support for some media types:
  * **MP3:** Safari 5+, Chrome 6+ e IE9
  * **Ogg Vorbis:** Firefox 3.6, Chrome 6, Opera 1.5 e IE9
* Also if the browser doesn't support this tag it will render the element content (like the paragraph in the example)
* [MDN audio doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
* [MDN media stream doc](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream)

**Example**
```html
<body>
  <audio src="ejemplo-audio.ogg" autoplay controls>
    <p>Audio description.</p>
  </audio>
</body>
```

### Source
* The **source** element specifies multiple media resources for the **picture**, **audio** and **video** elements
* It is an empty element
* It is commonly used to serve the same media content in multiple formats supported by different browsers 
* If we use this element we don't have to use the **src** attribute
* This element supports the following attributes:
  * **src:** required for **audio** and **video**, address of the media resource
    * The value of this attribute is ignored when the **source** element is placed inside a **picture** element
  * **type:** the MIME-type of the resource, optionally with a codecs parameter
    * See [RFC 4281 guide](https://tools.ietf.org/html/rfc4281) for information about how to specify codecs
* [MDN source doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source)
* [MDN picture doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture)

**Example**
```html
<body>
  <video poster="myvideo.jpg" controls>
    <source src="myvideoo.mp4" type="video/mp4">
    <source src="myvideo.webm" type="video/webm"> 
    <source src="myvideo.ogv" type="video/ogg"> 
    <source src="myvideo.3gp" type="video/3gp">
    <p>Vide description</p>
  </video>
  <audio autoplay controls>
    <source src="myaudio.mp3" />
    <source src="myaudio.ogg" />
    <p>Audio description.</p>
  </audio>
</body>
```

## Metadata
* The **meta** element represents metadata that cannot be represented by other HTML meta-related elements
* This element will work as **head** element content only
* The user won't see this element content
* This are some of the attributes that we can configure:
  * **author:** author which defines the name of the document's author
  * **charset:** this attribute declares the page's character encoding
  * **description:** contains a short and accurate summary of the content of the page
  * **keywords:** contains words relevant to the page's content separated by commas
  * **viewport:** gives hints about the size of the initial size of the viewport
    * Used by mobile devices only
    * Read the viewport MDN guide section to find out more about the different values this attribute supports
* Read the [MDN meta doc](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) too know more about the different attributes that we can use

**Example**
```html
<head>
  <meta charset="UTF-8">
  <meta name="description" content="My Site description">
  <meta name="author" content="John Doe">
  <meta name="keywords" content="HTML,CSS,XML,JavaScript">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

* Read the [Wikipedia character encoding doc](https://en.wikipedia.org/wiki/Character_encoding) to know more about how encoding works
* [Wikipedia UTF-8 doc](https://en.wikipedia.org/wiki/UTF-8)

## HTML Entity
* An HTML entity is a piece of text ("string") that begins with an ampersand (&) and ends with a semicolon (;)
* Entities are frequently used to display reserved characters (which would otherwise be interpreted as HTML code), and invisible characters (like non-breaking spaces) 
* You can also use them in place of other characters that are difficult to type with a standard keyboard
[MDN entity doc](https://developer.mozilla.org/en-US/docs/Glossary/Entity)
* [List of HTML entities](https://www.freeformatter.com/html-entities.html)

**Example**
```html
<body>
  <p>&lt; less than</p>
  <p>&gt; greater than</p>
  <p>&amp; ampersand</p>
  <p>&copy; Copyright</p>
  <p>&reg; Registered Trademark</p>
  <p>&trade; Trademark</p>
</body>
```

#### Practice
[Exercise 16](exercises/html/ex_16.md)

[Exercise 17](exercises/html/ex_17.md)

## Extra:
[HTML5 Specs](https://dev.w3.org/html5/spec-preview/Overview.html)

## Congratulations, you made it, now you know HTML!!
![Super Hero HTML5](resources/images/html/html_superhero.jpg)

## Let's Checkout CSS
* [<- Git](git.md) - [CSS ->](css.md)
