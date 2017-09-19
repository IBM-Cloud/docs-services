# Creating content for the Bluemix doc app in the docs-services repository

Welcome to the [docs-services repository](https://github.com/IBM-Bluemix/docs-services/tree/master/services) where you will create documentation for your service to be added to the Bluemix doc app.  

You will have your own folder in the docs-services repository in which to develop your doc app content. Your IBM Liaison will notify you when your folder has been created and send you a link to access it.

Your folder must contain two files:
* A [Getting Started template](https://github.com/IBM-Bluemix/docs-services/blob/staging/getting_started_template/index.md) that is always named [index.md]
* A [toc file](https://github.com/IBM-Bluemix/docs-services/blob/staging/toc) that has no file extension, which creates some of the page structure

**Important:** These files are required. You can link to any of your existing documentation using the related links in the toc file and you can add additional files, as needed.

These files are sourced in Markdown, a lightweight markup language, and managed in GitHub.  

The Bluemix doc app builds all 3rd party service Markdown files from this GitHub location for all regions.

## Prerequisites
Before getting started on your content, you will need to get a GitHub ID (https://github.com) and provide it to your IBM liaison who will enable write access to your GitHub folder.  You will also provide the IBM liaison with your official service name and the Bluemix catalog category it belongs in.

## Using the getting started template (Required)
The getting started template (and using the guideline comments it contains) provide a consistent look and feel to the documentation for all of the service across the Bluemix platform. The product documentation provided for a service should enable your potential users to quickly determine that they want your service and then quickly get up and running with it. Any supplemental information you choose to add should be task-based and it should support the productive use of the service.

### Using the Copyright and Last Updated header (Required)
Both the span of years your content has been published across, and the last date that you updated your content is included at the top of the getting started template.  It must apper in your file in exactly the format as it is in the getting started template, as shown in the following example:

```
---

copyright:

  years: 2017

lastupdated: "2017-09-18"

---
```

The copyright and lastupdated information must occur at the top of the MD file, before attributes are listed.  
  * It must be --- surrounded by 3 dashes ---
  * The value `years` can contain just one year or two years separated by a comma, for example, `years: 2016, 2017`. If the topic was created in the current year, provide just one year for the years variable. If you have updated the topic over a span of more than the current year, provide the first year and the last (current) year, separated by a comma. Don't include the intervening years. For example, for a topic created in 2016 and updated until 2017, then list the years:  `2016, 2017`
  * The value `lastupdated` must be followed by a machine date in quotes in the following format: "YYYY-MM-DD"
  * Ensure that each time you update your Markdown topic, you also update the `lastupdated` date.
  
### Adding a unique ID
After the H1 (`# Getting started with`) header, there is a `{: #gettingstarted}` ID tag that you need to edit to make it unique to your service.  If you are onboardind a service named, "All but the kitchen sink" for example, then your unique ID could be:

`{: #gettingstarted_allbutkitchensink}`

### Adding a short description (Required)
The short description should be 1-3 sentences that provide a very high level summary of your service. The purpose of the short description is to help your users determine, at a glance, that your service is the one they want to use.

On the line immediately following your 1-3 sentence description, ensure that you have preserved the following code in the getting started template so that the description displays properly:

`{:shortdesc}`

### Adding getting started steps (Required)
The getting started steps should include a brief introduction, which could be just a lead in sentence with a colon, for example:

`Use the following steps to install and set up the application:`

The getting started steps should follow and provide information about how to integrate the service into the app or use the service outside of Bluemix. Don't include steps to add the service from the catalog; always assume that your user is starting at the service dashboard.

**Tips**
 * With task-based, technical information, reduce the conversational style in favor of succinct and direct instructions.
 * Include the basic, most-common-use scenario steps to use the service or integrate it into the app. (Document edge cases in blogs as examples. If they become more common, consider moving them into the docs flow as child task flows.)
 * Include code snippets in all programming languages that can be copied. (The getting started template provides the quick and easy coding to make code snippets easily copied.)

If you have additional tasks to use your service (after the getting started topic), you can create additional task topics (files). See **Creating additional topics** for more information.

## Creating a table of contents (TOC) for your service catalog entry (Required)

To begin, you need to create a TOC map file in GitHub. This file must be in the root directory of your service. See the sample TOC in this (docs-services) folder.  You can copy it into the root directory of your service and edit it from there.

**Important note**:  The `toc` file has no extension; it is just named `toc`. When you create it in the root directory, do not add a file type.

The following toc file template is provided in the [base docs-services folder](https://github.com/IBM-Bluemix/docs-services/blob/staging/toc):

```
{:navgroup: .navgroup}
{:topicgroup: .topicgroup}

{: .toc subcollection="<FolderName>" audience="service" href="/docs/services/<FolderName>/index.html"}
<Name of service>

    {: .navgroup id="learn"}
    index.md

    {: .topicgroup}
    Related links
        [Link text](URL)
        [Link text](URL)
    {: .navgroup-end}

    {: .navgroup id="reference"}
    Reference
    [API Documentation](URL)
    {: .navgroup-end}
```

After you copy the entire toc file contents:
1. Do not alter the top two (navgroup and topicgroup) lines in the toc template.
2. Replace both of the `<FolderName>` placeholders with your folder name, in both locations.  
3. Replace `<Name of service>` with your service name.
4. And add any related links in the `[Link text](URL)` fields.  The `[Link text]` you provide is what is displayed in the left navigation panel and the `(URL)` is the external (`http` or `https`) link to your content when your user clicks the link text.  
5. If you only provide a single link, to your base documentation, for example, remove the second line of link text.  
6. Add your API documentation URL. You can change the link title `[API Documentation]` if you wish.
7. We recommend that you provide sample apps for your customers to use. Include links under the Reference section of your toc file that point to these sample apps. At a minimum, provide your sample apps in Node and Java.
8. If you want to add more files to your content, nesting additional files after the `index.md` file is as simple as indenting 4 spaces on the line beneath `index.md` and listiing the additional `<file>.md` files that you add to your folder. You can nest multiple levels of files.

Notice that the `(URL)` values in the toc file are exernal links. You can add as many external links as you want. For example if I wanted to add a TOC entry for an API in API explorer, I could add: `[REST API](https://sample-console.{DomainName}/apidocs)` to my toc map file under the Reference section of the toc.

**Tip**: Keep in mind that the search results are generated from your TOC. (A search is generated from the TOC JSON file.) One of the ways you can improve SEO is to ensure that your TOC contains the critical topics you want your customers to find.

After you have your toc file created in GitHub, the Bluemix doc build picks this file up and generates your table of contents.



## Creating additional topics (optional)
If you do not have your service fully documented outside of the Bluemix doc app, you might choose to add topics (files) in addition to the getting started template. Example topics could be "Configuring x", "Administering y", "Creating z".  Troubleshooting information would then be the last section in the flow, including specific troubleshooting topics and error messages. The following example outline shows possible additional topics that you might want to add:

**Example Outline:**

 * Getting started (index.md)
   * About (about.md)
   * Configuring x (configuring.md)
      * child topics
   * Administering y (administering.md)
      * child topics
   * Creating z (creating.md)
      * child topics
   * Troubleshooting (troubleshooting.md)
      * child topics

  The following toc file would create the structure for the previous example outline:

  ```
  {:navgroup: .navgroup}
  {:topicgroup: .topicgroup}

  {: .toc subcollection="FolderName" audience="service" href="/docs/services/FolderName/index.html"}
  Name of service

      {: .navgroup id="learn"}
      index.md
          about.md
          configuring.md
          administering.md
          creating.md
          troubleshooting.md

      {: .topicgroup}
      Related links
          [Link text](URL)
          [Link text](URL)
      {: .navgroup-end}

      {: .navgroup id="reference"}
      Reference
      [API Documentation](URL)
      {: .navgroup-end}
  ```

### Excluding unwanted headers

You might not want every single header in your markdown topic or topics to be rendered as part of your TOC. To exclude a header, simply add the notoc attribute to the header you to exclude in your md file, as shown in the following example:

```
# Header I want to exclude
{: #xreftext notoc}

## Another header nested underneath
{: #api}
```

**Note**: In the previous example, the notoc attribute is only on the H1 header. The notoc attribute cascades down and excludes any sub-headers nested beneath the header you specify to exclude. You can add the notoc attribute to any header at any depth; H1, H2, H3, etc…

## Authoring Bluemix content in Markdown
Markdown is a lightweight markup language with plain text formatting syntax designed so that it can be converted to HTML.

The Markdown used for Bluemix is based on GitHub-flavored Markdown. The following resources can be helpful in coding the markup for you content:
* https://help.github.com/articles/markdown-basics/
* https://help.github.com/articles/github-flavored-markdown/

Bluemix has designed a parser that transforms Markdown into HTML5. Because the syntax available in standard Markdown is limited, the Bluemix team has developed Extensions to provide an enhanced authoring experience. These extensions provide key features available in DITA today, adding, for example, the ability to use metadata attributes and content references in Markdown. This document provides instructions for using these extensions.

## How to suggest changes or updates to Bluemix documentation

All you need is a GitHub ID, and you can suggest edits and changes to Bluemix docs. A Bluemix team member will review any pull requests, and merge all or parts of your suggested changes as quickly as possible.
To make your changes:

1. Fork the project or create a branch right from the repository.
2. Edit files.
3. When your changes are complete, send a pull request from your branch with your changes.
4. Wait for a Bluemix team member to review your changes and merge all or parts of your suggested changes
5. After you are notified of your changes, tidy up your branches using the delete button in the pull request or on the branches page.

For more detailed information on how to contribute content to Bluemix documentation, see https://developer.ibm.com/bluemix/2016/01/13/bluemix-docs-now-open-source-on-github/. Also see the following help from GitHub:
https://help.github.com/articles/github-flow-in-the-browser/

## Markdown Editors
There are many free Markdown editors available, however, not all editors will honor the syntax used by Bluemix extensions. Notepad ++ is free, compatible, and also supports YAML, which is used to define content reference keywords.

# Markdown coding reference

## Mappings between MarkDown and HTML 5

|     Element     |   MarkDown (Git flavored)  |   HTML 5      |
|-----------------|--------------------------|---------------|
| **container**    | No equivalent.      | `<article>`   |
| **title**       | `# ## ### ####`          | `<h1>...<h6> `|
|**short description**| Bluemix enabled, placed beneath the description:  `{:shortdesc}`, though the first thing under the title must be a paragraph of text. |`<p>`|
| **section** | `No equivalent` | `<section>` |
| **unordered list** | `*` or `-`<br/><br/>**Note**: Nested lists need to be indented four spaces or a tab, and mixing ordered and unordered lists does not work (use html)| `<ul><li></li></ul>` |
| **ordered list** | `1.`<br>  `2.`<br> `3.` <br/><br/>**Note**: Nested lists need to be indented four spaces or a tab, and mixing ordered and unordered lists does not work (use html)   | `<ol><li></li></ol>`|
| **list item** | Use the appropriate list type; nested lists are supported: <br> `1. Item 1`<br>&nbsp;`1. A corollary to the above item.`<br>&nbsp;`2. Yet another point to consider.`<br>`2. Item 2`<br>&nbsp;`* A corollary that does not need to be ordered.`<br> &nbsp;&nbsp;` * This is indented four spaces, because it's two spaces further than the item above.`<br>&nbsp;&nbsp; `* You might want to consider making a new list.`<br>`3. Item 3`| `<ol>`<br>`<li>`<br>`<ol>`<br>`<li>`<br>`<li>`<br>`</ol>`<br>`<li>`<br>`<ul>`<br>`<li>`<br>`<li>`<br>`</ul>`<br>`<li>`<br>`</ol>` |
| **definition list** | No equivalent, use html coding. | `<dl>` |
| **term** | No equivalent, use html coding. | `<dt>` |
| **definition** | No equivalent, use html coding. | `<dd>` |
| **paragraph** | No equivalent; paragraphs in Markdown are just one or more lines of consecutive text followed by one or more blank lines. | `<p>` |
| **code** | ```` ```code``` ```` | <pre class="codeblock"><code> |
| **table** | `Header 1`  `|` `Header 2` <br> ------------- `|` ------------- <br> `Content`  `|` `Content` <br> `Content`  `|` `Content` <br> **Notes**: <br>1. Your cells do not need to line up on the page in Markdown when editing. <br>2. Tables in Markdown do not support explicit line breaks. To cheat, you can use the `<br>` HTML tag. | `<table>`<br>`<thead>`<br>`<tr>`<br>`<th>Header 1</th>`<br>`<th>Header 2</th>`<br>`</tr>`<br>`</thead>`<br>`<tbody>`<br>`<tr>`<br>`<td>`<br>`Content</td>`<br>`<td>Content</td>`<br>`</tr>`<br>`</tbody>`<br>`</table>` |
| **italics** | `*italic*` | `<em>` |
| **bold** | `**bold**` | `<strong>` |
| **strikethrough** | `~~strikethrough~~` | `<del>` |
| **monospace** | ``monospace`` | `<code>` | 	
| **links** | You can create an inline link by wrapping link text in square brackets `( [ ] )`, and then wrapping the link in parenthesis `( ( ) )` immediately following the square brackets. <br><br> GFM will autolink standard URLs, so if you want to link to a URL (instead of setting link text), you can simply enter the URL and it will be turned into a link to that URL. <br><br>**Note**: to create an external link that opens in a new window, place the following attribute defintion at the top of your file: `{:new_window: target="_blank"}` and then use the following attribute after your link `[link](url){: new_window}` | `<a href="https://www.link.com">Link Text</a>` |
| **blockquote** |  `In the words of Abraham Lincoln:`<br>`> Pardon my French` | `<blockquote>`<br>`<p>text</p>`<br>`</blockquote>` |
| **image** |  `![alt text for my graphic](images/image_name.jpg)` | `<p><img src="images/1.png" alt="alt text"></p>` |
| **video** |  `<video width="400px" controls>`<br>`<source src="mov_bbb.mp4" type="video/mp4">`<br>`<source src="mov_bbb.ogg" type="video/ogg">`<br>`Your browser does not support HTML5 video.`<br>`</video>` | `<video width="400px" controls>`<br>`<source src="video/BlueMix Mobile Data iOS Demo v2.mp4" type="video/mp4">`<br>`Your browser does not support HTML5 video.`<br>`</video>` |
| **keywords** | `currently not available` | `<meta name="keywords" content="keyword">` |
| **metadata** |  `{{site.data.product.bluemix}}` | `data-hd-metadata` |		
| **comments** |  `<!-– comment -->` | `<!-– comment -->` |
| **mdash** | `no equivalent` | `&mdash;` |



## Bluemix Extensions
 The following Bluemix extensions to Markdown are supported:
 * Output all MarkDown markup to standard, valid HTML5 tags
 * Attributes
 * Addition of headers and footers to the HTML output
 * Anchor IDs Generated for all Headers
 * Content References
 * TOC file
 * Output is fully accessible
 * Additional functionality


### Attributes
The Bluemix Markdown parser allows you to define additional attributes in Markdown. After your attributes are defined, you can apply these values to any markdown element, like headers, paragraphs, and codeblocks.

You can use the Bluemix attributes extension to map the following attributes to an element:
  * ID
  * Class
  * Custom value

**Note**: Attributes, when defined and applied within a Markdown file, are output by the Bluemix Markdown parser by default. No additional parameters or flags need to be passed to the parser when the command is run.

####How attributes are defined in Markdown
Attributes are defined at the top of your Markdown file. Each Attribute definition must be enclosed in curly brackets { }, and must contain a unique name. While you can provide attribute definition values for ID, Class, and Custom, none of these values are required, and you can define any combination of these different attribute values. The Bluemix Attribute Definitions implimentation is based on the Kramdown / Maraku Attribute Definiton extension: (http://kramdown.gettalong.org/syntax.html#attribute-list-definitions).

For Example:
```
<!-- Attribute definition -->
{:Name: #ID .Class Custom='custom attribute'}
<!-- Sample Attribute definition -->
{:java: #java .ph data-hd-programlang='java'}

```

* **:Name:** is the name of the attribute. This value does not get passed through to the output, it is an internal Markdown name that is used to map the attribute definition at the top of the page to one or more uses throughout the Markdown file. This value must be surrounded by colons (: :).
* **#ID** sets a value associated with the `id` attribute. This value is optional. If I define an ID of `#java` in my attribute, and I set this attribute on a Header, the HTML5 output will produce `<h1 id="java"></h1>`. This value must begin with a pound sign (#).
* **.Class** sets a value associated with the Class attribute. This value is optional. If I define a Class of `.ph` in my attribute, and I set this attribute on a Header, the HTML5 output will produce `<h1 Class="ph"></h1>`. This value must begin with a pound period (.).
* **.Custom** sets a custom attribute value. This value is optional. If I define a Custom value of `data-hd-programlang='java'` in my attribute, and I set this attribute on a Header, the HTML5 output will produce `<h1 data-hd-programlang='java'></h1>`.

####How attributes are applied in Markdown
After you define your attribute at the top of your Markdown file, you can apply the attribute by adding a call to the name of your attribute to the end of the Markdown tag you want to bind your attribute to. The implimentation of Bluemix attribute usage is based on the Kramdown / Maraku Block/Span Inline Attribute Lists: http://kramdown.gettalong.org/syntax.html#inline-attribute-lists

To apply a defined attribute, call the name of the attribute surrounded by curly brackets, and pre-pended by a colon and a space: `{: Name}`

For example:
I define a short description attribute at the top of my file and then apply it to a paragraph:
```
 {:shortdescription: .shortdesc}

 This is a short description paragraph
 {: shortdescription}

```
The Markdown parser will output HTML5 that looks like this:

```
<p class="shortdesc">This is a short description paragraph</p>

```

####Attributes in DITA vs Markdown  
In DITA, attributes are used to add metadata to elements. For example, you might add a `product`, `props`, or `otherprops` attribute on a phrase or paragraph element in order to associate a value with that phrase or paragraph. These values allow for filtering either during build or runtime. DITA transforms to HTML5 also apply Class attributes to HTML5 elements, and these values are used by the .CSS stylesheets at runtime to control the display.

Example of DITA attributes (from `using_rabbitmq_service.dita`):
Here we can see that the author has added a `props` attribute to 3 phrase tags, and added a unique programming language value to each `prop`.

```
<shortdesc>You can use the <ph props="programlang(javascript)">Node.js</ph> <ph
props="programlang(java)">Java</ph> <ph props="programlang(ruby)">Ruby</ph> sample
application to try the <keyword
conref="cloudoeconrefs.dita#cloudoeconrefs/rabbitmq">RabbitMQ</keyword> service.</shortdesc>

```
HTML5 output transformed with IDWB:

```
<p class="shortdesc">You can use the <span class="ph" data-hd-programlang="javascript">Node.js</span> <span class="ph" data-hd-programlang="java">Java</span> <span class="ph" data-hd-programlang="ruby">Ruby</span> sample
application to try the <span class="keyword">RabbitMQ</span> service.</p>

```

In Markdown, the Bluemix parser will apply whatever attributes you define to any of the supported Markdown elements, (For example, Header, Paragraph, Codeblock, Blockquote, Inline Code, Bold, Italics, Table, etc.). While Markdown does not support the Phrase tag, you can still bind attributes to single words or phrases by using inline tags like Code, Bold, or Italics.

The Bluemix doc framework provides runtime context switching functionality that looks for attributes on HTML5 elements and hides or displays this content depending on selections made by the user. Support for context switching in Markdown source is just one of the ways writers can use the Bluemix attribute extension. In addition, writers can add anchor IDs to multiple elements, overwrite anchor IDs on headers, add Class attributes like `shortdesc` to a paragraph to define the output as a shortdescription, as well as define their own custom attribute values on supported elements.

Example of Markdown attributes definitions and applications (from `using_rabbitmq_service.md`):
The DITA source example above from `using_rabbitmq_service.dita` is an example of a file that has been designed for context switching. When the HTML5 output is displayed at runtime in the Bluemix doc framework, if the user selects to view only Ruby, elements containing the attribute `data-hd-programlang="ruby"` will be displayed, and elements with the attribute of `data-hd-programlang` that contain anything other than `"ruby"` will be hidden. Below I have created a near-equivalent version of the DITA topic in Markdown, complete with attributes that support context switching.

```
<!-- Attribute definitions -->
{:javascript: #javascript .ph data-hd-programlang='javascript'}
{:java: #java .ph data-hd-programlang='java'}
{:ruby: #ruby .ph data-hd-programlang='ruby'}
{:shortdescription: .shortdesc}

<!-- Applying the above definitions to inline code tags and paragraph tags -->
You can use the `Node.js`{: javascript} `Java`{: java} `Ruby`{: ruby} sample application to try the RabbitMQ service.
{: shortdescription}

```

Output of HTML5 from Markdown parser:

```
<p class="shortdesc">You can use the <code id="javascript" class="ph" data-hd-programlang="javascript">Node.js</code> <code id="java" class="ph" data-hd-programlang="java">Java</code> <code id="ruby" class="ph" data-hd-programlang="ruby">Ruby</code> sample application to try the RabbitMQ service.</p>

```

### Headers and footers
Bluemix needed to add copyright and metadata to the header of the HTML 5 output. We have standard header and footer files that are called during transformation.

####Anchor IDs Generated for all Headers
When the Bluemix Markdown parser transforms Markdown to HTML5, it automatically binds an anchor ID to all Header elements. Any time the parser transforms a Markdown file that contains a header, the HTML5 output of that header tag will produce an `id` attribute, with a value that is unique. Unique anchor IDs on headers provide writers with the ability to link directly to a sub-topic that begins with a Header.

For example, here is a level 4 Header in Markdown:
```
####Content references in DITA vs Markdown
```
When the above Markdown is transformed into HTML5, the parser produces a unique id with a value that is equal to the name of the header:
```
<h4 id="content-references-in-dita-vs-markdown">Content references in DITA vs Markdown</h4>
```
**Note**: Header anchor IDs are output by the Bluemix Markdown parser by default. No additional parameters or flags need to be passed to the parser when the command is run.

####Changing an anchor ID on a Header

The Anchor ID is bound to a header by default, and it always uses the text of the header as its name, so you can always just link to that. However, any time you want to override the anchor tag of a header, you can use an attribute. See the Attribute section above for more details on using attributes.

Example of default anchor bound to a header:

Mardown source:
`##Visualizing your data sample`

HTML5 output:
`<h2 id="visualizing-your-data-sample">Visualizing your data sample</h2>`

Example of remapping using a simple attribute (we use the ID attribute, which is mapped with the # character):

Markdown source:
```
##Visualizing your data sample
  {: #my-renamed-anchor}
```

HTML5 output:
`<h2 id="my-renamed-anchor">Visualizing your data sample</h2>`

**Note**: You could produce the same results by making an attribute definition at the top of your file, and then you would call the name of the attribute definition, like so:
```
{:myanchor: #my-renamed-anchor}

##Visualizing your data sample
  {: myanchor}
```

####Linking to an anchor ID for a header

You can link directly to a header within a file using the header anchor ID. You can link to sub-headings; it does not need to be the top-level header. Use the automatically generated header value based on the text that is defined in the header (see Anchor IDs Generated for all Headers), or add your own anchor ID to use for linking (see Changing an anchor ID on a header). The following example for linking uses user-defined ID anchors for each header, and the goal is to provide a link to content that is further down in the same file.

```
Headings and user-defined header anchors for my file:

#Bluemix
{: #bluemix}

My short description links to the [Applications heading](filename.html#header_id).

##Services
{: #services}

##Applications
{: #applications}

I want to create a link within my short description that links to the second sub-heading, Applications.
To do this, I would use the following format: [Link text for header](filename.html#header_id).
For this example, I would use [Applications](readme.html#applications).
```

### Content References
The Bluemix conref extension is invoked by the parser by using the conrefFile flag: `--conrefFile=cloudoeconrefs.yml`.

 >node mdProcessor.js --sourceDir=C:\pilot\sourceMD --destDir=C:\pilot\outputMD --headerFile=header.txt --footerFile=footer.txt
 >**--conrefFile=cloudoeconrefs.yml** -overwrite

Conrefs are stored in `cloudoeconrefs.yml`. `cloudoeconrefs.yml` is a YAML file, and can be placed in any directory as specified in the `--conrefFile` parameter. Typically, `cloudoeconrefs.yml` can be found in `C:\Users\IBM_ADMIN\Documents\GitHub\markdownProcessor`.

Conref definitions in YAML are structured in nested keys, each key that contains a value or a subkey must be followed by a colon (:), and the next line must be indented 2 space. For example:
```
 key:
  subkey1:
    conref value 1
  subkey2:
    conref value 2

```
Conrefs in Markdown are called by using the following syntax: `{{site.data.key1.key2...keyN}}`
**Note:** While you can Nest keys as deep as you like in YAML, and call deeper sets of keys from markdown, Bluemix conrefs use only 2 keys. For example: `{{site.data.keyword.bluemix}}`  

####Content references in DITA vs Markdown
In DITA, a content reference, or conref, is a way of reusing or pulling content from one file into another file; effectively making a copy during the transform.

Example of conrefs sourced in DITA (stored in cloudoeconrefs.dita):
```
	<!--//Do not translate - Begin-->
	<p><keyword id="bluemix"><tm tmtype="reg" trademark="IBM">IBM</tm> <tm tmtype="tm" trademark="Bluemix">Bluemix</tm></keyword></p>
	<p><keyword id="bluemix_short"><tm tmtype="tm" trademark="Bluemix">Bluemix</tm></keyword></p>

```
Example of a conref being called from a DITA file (called from rails.dita):

```
	<p>This Ruby starter application is a boilerplate for <keyword conref="cloudoeconrefs.dita#cloudoeconrefs/bluemix_short">BlueMix</keyword> Ruby web application development.</p>

```

In the Bluemix Markdown extension, we create a similar mechanism for reusing or pulling content from one file into another file. The extension uses YAML as a source for the conrefs.  

Example of conrefs sourced in YAML (stored in cloudoeconrefs.yml):

```
	#Bluemix conref equivalent file to cloudoeconrefs.dita

	#//Do not translate - Begin
	keyword:
	  bluemix:
	    IBM&reg; Bluemix&trade;
	  bluemix_short:
	    Bluemix&trade;
	  IBM:
	    IBM&reg;
	  cloudoe:
	    Cloud Operating Environment
	  domainname:
	    DomainName
	  Appdomainname:
	    AppDomainName
	#Service names
	  activedeployshort:
	    Active Deploy
	  amashort:
	    Advanced Mobile Access
	  activedeployshort:
	    Active Deploy
	  amashort:
	    Advanced Mobile Access

```

Example of conrefs called from Markdown (called from test.md):

```
	This is a new paragraph all about using conrefs. This word here: {{site.data.keyword.bluemix}} is actually a conref! I can use {{site.data.keyword.bluemix}} multiple times in a paragraph.
	* I can use the full product name: {{site.data.keyword.bluemix}}
	* Or I can use the shortened product name: {{site.data.keyword.bluemix_short}}
	* {{site.data.keyword.activedeployshort}} is a Service.
	* So is {{site.data.keyword.amashort}}

```

Results:

```
	 This is a new paragraph all about using conrefs. This word here: IBM® Bluemix™ is actually a conref! I can use IBM® Bluemix™ multiple times in a paragraph.

		I can use the full product name: IBM® Bluemix™
		Or I can use the shortened product name: Bluemix™
		Active Deploy is a Service.
		So is Advanced Mobile Access

```

### TOC File
In addition to the standard HTML5 output that the Bluemix Markdown parser produces from each Markdown file, the parser also produces a Table of Contents file in different formats. Each TOC file produced from a markdown topic contains a nested set of structured headers or topicrefs that match the structure of headers in the original markdown source. Each TOC header or topicref also contains a link to a corresponding header anchor ID in the HTML5 output file that was generated from the Markdown source.

By default, for each Markdown file processed by the Bluemix parser, the following files are output:

**Source:** `index.md`

**Output:**
* `index.HTML`: standard HTML5 output
* `indexTOC.md`: Markdown file with nested Headers matching each Header in index.md. Each Header contains a link to  a corresponding header anchor ID in index.HTML
* `indexTOC.HTML`: HTML file with nested Headers matching each Header in index.md. Each Header contains a link to  a corresponding header anchor ID in index.HTML
* `index.ditamap`: DITA map file with nested topicrefs matching each Header in index.md. Each topicref contains a link to  a corresponding header anchor ID in index.HTML

**Note:** Each TOC format is produced and structured following the conventions of that format. Because DITA map files enforce a strict rule where headers must be incremented by only a single level, any Headers in your markdown that skip a level, (for example, H1 to H3, skipping H2), will not produce a valid *.ditamap TOC. Header values can decrease by skipping a level, (for example, H3 to H1, skipping H2), but they cannot increase.

**Note**: TOC files are output by the Bluemix Markdown parser by default. No additional parameters or flags need to be passed to the parser when the command is run. To disable TOC files, add the following parameter: `-disableToc`

### Accessible output
We have worked to output all Markdown markup to standard and valid HTML5 tags:
* Alt text for images: Included as part of the Markdown tagging for images
* Header row in tables: Output turns the first row into `<thead>`
* Elements having a WAI-ARIA 'article' role must have a label specified with aria-label or aria-labelledby.
* Use header elements where appropriate: Pass thru HTML tagging when Markdown markup is not available, for example definition lists (dl, dt, dd)
* There must be a non-empty title element in the head of the document: For the HTML output from Markdown, the `<head>` element does not contain a `<title>` element. We added this with a header file.

Additional accessibility *might* be needed as content is migrated to Markdown. And, as a result, updates to the parser and/or to the markup recommendations *might* be required.

### Additional functionality
 * Copy of non-.md files: Copies (doesn't process) image files (.bmp, .jpg, .png, .gif, .SVG) and other file extensions like .html, .pdf, .json, .js
 * Recurse sub-directories: Processes all directories in the specified source directory
 * Overwrite: Addition of an overwrite flag to replace previous output

### Tips for avoiding common errors

1. Using HTML within your Markdown topics is allowed, and in some cases encouraged (the only way to output a definition list is by using HTML). However, if you chose to use HTML, **always ensure your HTML is well-formed**. Any tag that does not have a closing tag associated with it will break the parser, and your build will fail. For example, the only way that you can create a line break inside a table cell in Markdown is to use a break tag, however, using `<br>` will actually break the build. You must close the break tag like so: `<br/>`. If you use HTML, carefully validate that your tags are matching and that you close all open tags.
2. Avoid using `<` and `>`. For all special characters, it is recommended that you use the `&` value. For example, for `>` use `&gt;`.  All of the following special characters are also supported: (http://www.w3.org/MarkUp/HTMLPlus/htmlplus_13.html)
