Thanks for showing interest in contributing to MyCrypto! Here are some basic
guides for how to best help out, depending on how you're looking to contribute.

* [I'm Having a Problem With My Wallet / Transaction / Swap / ENS](#getting-support)
* [I Want to Report a Bug or Issue](#reporting-a-bug)
* [I Want to Suggest a Feature](#suggesting-a-feature)
* [I Want to Help With Translations](#providing-translations)
* [I Want to Contribute Some Code](#contributing-code)

If your contribution doesn't fit in to those, feel free to send us an email
at [support@mycrypto.com](mailto:support@mycrypto.com) or hit us up on Twitter
at [@MyCrypto](https://twitter.com/mycrypto).

---

<br/>
<br/>

## Getting Support

If you're having a problem with the site that you do not believe to be a bug
with the software, you'll get help from our support team by emailing
[support@mycrypto.com](mailto:support@mycrypto.com). The Github issue queue
is used for development, not support, so your question probably won't get
answered here.

<br/>
<br/>

## Reporting a Bug

If you've found a bug, or something confusing about MyCrypto, here's what you
should do:

1. **Search for your issue** - If you're experiencing something, the chances are
    good that someone else is too. Search the issue queue or our
    [Knowledge Base](support.mycrypto.com) before posting. You may even find an
    answer to your problem!
2. **Describe the issue in detail** - Instead of describing something as "not
    working" or being "broken", explain what you expected to happen, and what's
    happening instead, or just not happening.
3. **Provide console logs** - Every browser has the ability to view logs from
    Javascript, which is where many error messages will get displayed if
    there's a bug in the code. Here's how in [Firefox](https://developer.mozilla.org/en-US/docs/Tools/Browser_Console),
    [Chrome](https://developers.google.com/web/tools/chrome-devtools/console/),
    [Internet Explorer](https://msdn.microsoft.com/en-us/library/dn255006(v=vs.85).aspx),
    [Microsoft Edge](https://docs.microsoft.com/en-us/microsoft-edge/devtools-guide/console),
    and [Safari](https://www.wickedlysmart.com/hfjsconsole/). You'll want to
    provide us with as many of the logs as possible, especially anything in red.
4. **Provide browser information** - Let us know what operating system, browser,
    browser version, and mobile device (if applicable.) This will help us debug
    your issue on an identical device.

Following the above steps will ensure that your bug is addressed in a timely and
efficient manner. Thanks for keeping MyCrypto bug free!


<br/>
<br/>


## Suggesting a Feature

If there's a feature that you think would make MyCrypto a better product, we
want to know. Here's the best way to do it:

1. **Search for your suggestion** - If you've thought of a good new feature,
    chances are someone else may have too. To consolidate issues, we'll keep
    feature requests in one thread. Show your support for a request by using
    the thumbs up response on the Github issue.
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


<br/>
<br/>



## Contributing Code

If you're a developer looking to pitch in, you're more than welcome to help out.
Here are some suggestions for diving in:

### Read the Documentation

Make sure you read the entire Readme to understand some basics about the project
and how to run it. You can also check out our
[style guide](https://github.com/MyCryptoHQ/MyCrypto/wiki/Style-Guides) for how
to write code that matches the way we write things.


### Find a Good First Issue

If this is your first time contributing to MyCrypto, you'd probably do well to
start small. We often mark good tasks for this on our issue queue with the
"good first issue" label. You can find those
[over here](https://github.com/MyCryptoHQ/mycrypto/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22).

### Make an Issue First

Before you dive into coding your change, it's often good to first make an issue,
or work on an existing issue before you start. This will allow anyone to provide
feedback about what you're going to work on before you spend time on something
that may change. Likewise, it will prevent someone else from working on the same
issue as you. Pull requests against an existing issue have a much higher chance
of getting merged.

### Write Unit Tests

If your changes touch the more structural parts of the codebase, you'll be asked
to write tests for them, and make sure the existing tests pass. Detailed
documentation of writing and running tests is forthcoming, but for now, just try
to follow the example of existing tests.

### Make a Detailed Pull Request

Make sure you follow the format of a new pull request, where applicable. You'll
want to:

* Provide a detailed explanation for what your code does
* List all of the high-level technical changes you've made
* Provide a list of steps for testing your change (if applicable)
* Provide screenshots / gifs of the visual changes (if applicable)

Pull requests that have the above information are much more likely to be
accepted.
