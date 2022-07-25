[//]: # (These are my styles for pretty HTML viewing.)
<style>

em {
	color: green;
}

code {
	color: red;
}

span {
	background-color: yellow;
}

</style>

# Linux experience

## About

I am using this file to detail my daily experience with Gentoo Linux. The idea is to document every step I make to improve my understanding of computers. For example, if I do some work on __udev__, I'll keep notes of every important action I take in order to use them for a blog post in the future.

<span>NOTE: to generate HTML for pleasant viewing experience run the following command:</span>

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

### Adding style to MD files

Simply add `<style></style>` to the file and define your __style__. I used a __span__ to wrap dates and notes in yellow, so I actually have to surround those elements with explicit span tags. I recorded a __macro__ using q in normal mode in Vim. Then pressing \@s will add a wrapper around the content of the line in span tag.

In addition __blockquotes__ have to cover every line for a block of code to be properly rendered on the page. Note that there is a difference between code and pre tags.

### Re-packing EPUB file

I have Verne's one of the greatest under Verne.epub. Epub is just a compressed file containing, for example, HTML files and layout schemes that are bundelled together to make EPUB document. I need to change font size because CoolReader3 renders tiny letters and does not allow to zoom the page.

I open Verne.epub with Archive Manager and extract the contents into a folder, say "files/". I edit styles.css and then run the following command:

>```
>zip -r ../Verne-remastered.epub *
>```

This will generate Verne-remastered.epub along Verne.epub and files/

### GitHub Android App

That is not a very useful tool to an active developer but I use it to explore projects. There is a lot of exciting stuff such as "Awesome lists" under Python's Audio projects in particular [dejavu](https://willdrevo.com/fingerprinting-and-audio-recognition-with-python/) (Yeah, an unfortunate choice of name). Have a look for yourselves!


