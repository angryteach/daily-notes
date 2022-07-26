[//]: # (These are my styles for pretty HTML viewing.)
<style>

h3 {
	text-align: center;
	color: blue;
	font-size: 2.2rem;
}

p {
	font-size: 2rem;
}

em {
	color: green;
}

code {
	color: red;
	font-size: 1.2rem;
}

span {
	background-color: yellow;
}

</style>

# Linux experience

## About

I am using this file to detail my daily experience with Gentoo Linux. The idea is to document every step I make to improve my understanding of computers. For example, if I do some work on __udev__, I'll keep notes of every important action I take in order to use them for a blog post in the future.

<span>NOTE: to generate HTML for a more pleasant viewing experience run the following command:</span>

>```
>pandoc NOTES.md > index.html
>```

## My experience

### Inserting date in Vim
<span>Mon 25 Jul 2022 07:15:56 AM MSK</span>

This is my first entry in the journal. As I was working on the About section I realised among many things that I would like to add dates to my journal entries in __Vim__.

Here's the solution [from the wikia](http://vim.wikia.com/wiki/Insert_current_date_or_time) suggesting adding the following two lines to my __.vimrc__ file:

>```
>:nnoremap <F5> "=strftime("%c")<CR>P
>:inoremap <F5> <C-R>=strftime("%c")<CR>
>```

Now, by pressing F5 hotkey I can insert the date in normal and insert modes.

___________________________________________________________________________

### How to hide elements of web pages with CSS in Firefox

I used to be able to hide certain elements from any web page that I visit using a simple css file called __userContent.css__ in my browser's profile folder.

1. To find the folder go to "__about:support__" in the search bar
2. Create the file and add code to block something like a class.
3. To enable support for user styles, set "_toolkit.legacyUserProfileCustomizations.stylesheets_" to "true" in __about:config__.

This last line is the most important one because starting with version 69 of FF it is disabled by default.

Here is an example from my actual code:

>```
>.hD {
>	display: none !important;
>}
>```

___________________________________________________________________________

### Adding style to MD files

Simply add `<style></style>` to the file and define your __style__. I used a __span__ to wrap dates and notes in yellow, so I actually have to surround those elements with explicit span tags. I recorded a __macro__ using q in normal mode in Vim. Then pressing \@s will add a wrapper around the content of the line in span tag.

In addition __blockquotes__ have to cover every line for a block of code to be properly rendered on the page. Note that there is a difference between code and pre tags.

___________________________________________________________________________

### Re-packing EPUB file

I have Verne's one of the greatest under Verne.epub. Epub is just a compressed file containing, for example, HTML files and layout schemes that are bundelled together to make EPUB document. I need to change font size because CoolReader3 renders tiny letters and does not allow to zoom the page.

I open Verne.epub with Archive Manager and extract the contents into a folder, say "files/". I edit styles.css and then run the following command:

>```
>zip -r ../Verne-remastered.epub *
>```

This will generate Verne-remastered.epub along Verne.epub and files/

___________________________________________________________________________

### GitHub Android App

That is not a very useful tool to an active developer but I use it to explore projects. There is a lot of exciting stuff such as "Awesome lists" under Python's Audio projects in particular [dejavu](https://willdrevo.com/fingerprinting-and-audio-recognition-with-python/) (Yeah, an unfortunate choice of name). Have a look for yourselves!

___________________________________________________________________________

### Create a blog using Python's static site generator called Pelican
<span>Tue 26 Jul 2022 07:01:13 PM MSK</span>

Pelican can be installed using Portage but I like to work with my Python projects from inside virtual environments. So, I first set one up:

>```
>python -m venv myenv
>```

Then I activate it by using:

>```
>source myenv/bin/activate
>```

Now I am in chroot environment. Now I install pelican, markdown, envoke, livereload:

>```
>pip install pelican markdown invoke livereload
>```

invoke is only needed if you wish to use tasks.py.

Using `pelican-quickstart`, you can set up your project fairly quickly. After that you ought to create the source file, say index.md, in content/. That will be later used to generate index.html file in a folder of your choice. Now I am ready to generate the site:

>```
>pelican content -o output
>```

Where content is the content/ folder and output is the corresponding output/ folder.

Now you can explore the folder and Pelican [guide](https://docs.getpelican.com/en/4.8.0/index.html#) to suit your needs.

___________________________________________________________________________

### Create a GitHub Page to host my blog

I'd like to use GitHub's hosting to serve my static blog pages to users. This is going to be used to showcase my work or even replace this file.

I now realise that I can generate web pages for every repo I have in my profile. This is done through Settings - GitHub Pages for individual repos. To host my profile, I'd have to create a new repo called "angryteach.github.io" for it to be my default web page on GitHub Pages.

___________________________________________________________________________
