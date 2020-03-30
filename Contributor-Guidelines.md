Thanks for showing interest in contributing to MyCrypto! Here are some tips that are
hopefully helpful.

Github is primarily for developers and is mostly monitored by MyCrypto developers. 
If you need help or support using our product or simply want to chat with us:

- Email us at support@mycrypto.com
- Join our [Discord](https://discordapp.com/invite/VSaTXEA)!

If you have a critical or security-related issue, please reach out to us via a more private channel, like security@mycrypto.com or via [HackerOne](https://hackerone.com/mycrypto). 

<br/>

## Contributing Code

If you're a developer looking to pitch in, you're more than welcome to help out.
Here are some suggestions:

### Read the Documentation

Make sure you read the readme to understand some basics about the project
and how to run it. You can also check out our
[style guide](https://github.com/MyCryptoHQ/MyCrypto/wiki/Style-Guides) for how
to write code that matches the way we write things. *Note: this is somewhat out
of date.*

### Make an Issue First

It's often good to make an issue first or work on an existing issue before you
start. This will allow anyone to provide feedback about what you're going to
work on before you spend time on something that may change. Likewise, it will
prevent someone else from working on the same issue as you.

### Write Relevant Tests

If your changes touch the more structural parts of the codebase, you'll be asked
to write tests for them, and make sure the existing tests pass. Try to follow the
example of existing tests or chat with us if you need help determining what tests
to write or how to write them.

### Make your code translatable

If you are adding any new strings to the codebase which are shown to the user, please make sure those strings are translatable, using [this guide](https://github.com/MyCryptoHQ/MyCrypto/wiki/Contributing---Translatable-strings).

### Make a Pull Request! 🎉 

* Provide a detailed explanation for what your code does
* List all of the high-level technical changes you've made
* Provide a list of steps for testing your change (if applicable)
* Provide screenshots / gifs of the visual changes (if applicable)

This helps us quickly understand what the pull request does and allows us to test
it and merge it faster.

Again, if you want to talk before you start coding away, feel free to join 
our [Discord](https://discordapp.com/invite/VSaTXEA)!

<br />

## Reporting a Bug

1. **Search for your issue** - If you're experiencing an issue, it's likely 
    someone else is too. Search the issue queue or our
    [Knowledge Base](https://support.mycrypto.com/) to see if you can find the
    answer to your problem first.
2. **Describe the issue in detail** - Explain what you were doing when the
   issue happened, what you expected to happen what's happening instead, or
   what is just not happening. Please include relevant information about your
   machine and operating system. 
3. **Console logs & screenshots** - Every browser has the ability to view logs from
    Javascript, which is where many error messages will get displayed if
    there's a bug in the code. Here's how in [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Browser_Console),
    [Chrome](https://developers.google.com/web/tools/chrome-devtools/console/),
    [Internet Explorer](https://msdn.microsoft.com/en-us/library/dn255006(v=vs.85).aspx),
    [Microsoft Edge](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide/console),
    and [Safari](https://www.wickedlysmart.com/hfjsconsole/). You'll want to
    provide us with as many of the logs as possible, especially anything in red. 🙇

Thanks for keeping MyCrypto bug free!


<br/>
<br/>


## Suggesting a Feature

If there's a feature that you think would make MyCrypto a better product, we
want to know. Here's the best way to do it:

1. **Search for your suggestion** - If you've thought of a good new feature,
    perhaps other's have too. To consolidate issues, we'll keep
    feature requests in one thread. Show your support for a request by adding
    your thoughts to existing feature requests.
2. **Describe your suggestion** - Describe, in detail, how you would want this
    new feature to work. If something doesn't work very well, it helps to know
    the pain points. If you have an idea of how to make it better, feel free to
    suggest!
3. **Provide examples** - If it's something another website or app is doing,
    shoot us a link or a screenshot. We build better projects by working with
    other developers in our community.

Features that are requested with the above information have a better chance of
getting implemented. Thanks for the suggestions!


<br/>
<br/>


## Providing Translations

Our team is somewhat multi-lingual, but we rely on the community to help out
with languages we don't know. If you're willing to help, we'd really appreciate
it.

1. **Find your language file** - Language files are located in
    `common/translations/lang/[language-code].json`. If you don't see your
    language in here, feel free to create a new one by copying `en.json`, and
    naming it after your language's 2 letter ISO 639-1 code.
2. **Make your edits** - Simply find the phrases that you want to translate,
    and change the text on the right side of the key. Make sure that you
    following JSON formatting, or the code won't be able to read it.
3. **Maintain the meaning** - Try to stay as close to the original english
    intent as much as possible, and keep words consistent. Learning how to
    interact with the blockchain is difficult, so by sticking with the wording
    our team uses, and using the same names for things consistently will make
    it easier for users.
4. **Do only as much as you want** - We use _a lot_ of copy around the site,
    so it's daunting to translate it all in one go. Don't worry about doing
    everything, just do as much as you want. We'll take in even single line
    changes.
5. **File a pull request** - To submit your translations, you'll need to make
    a [pull request](https://help.github.com/articles/about-pull-requests/). If
    you're not familiar with git, don't worry. You can easily make one online
    by clicking the pencil edit button on the file when you're viewing it, and
    it'll make one for you when you're ready to suggest your edits.

If you follow the steps above, we'll be sure to provide your translations to all
of our users. Thanks a for helping out your fellow language speakers!

