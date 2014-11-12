## Synopsis

`pan.el` is a library that helps launching the tests when used with tox and testrunner. It's very much tailored to [OpenStack workflow](https://wiki.openstack.org/wiki/Gerrit_Workflow) and was the main motivation of the author to develop this tool.

The name `pan` has no meaning at all, it just came randomly in my head :)

## Installation

It's not available (yet) in [melpa](http://melpa.org) or [marmalade](https://marmalade-repo.org/) so you would have to do the manual way for now by checking out the module and put it in your load-path. A good documentation about how the load-path and how it works is available [here in the emacswiki](http://www.emacswiki.org/emacs/LoadPath).

## Usage

At first `pan.el` will try to get your tox environment of your project and detect if the environment has testtools installed and ask you if you want to use it. It will cache that variable but if you do press a `C-u` it will ask for it again. That env will be used to launch or detect the tests after.

You can choose a different function to run the tests :

* `pan-run-all`: Will run all tests no matter if one fails.
* `pan-run-all-until-fail`: Will run all tests until one fails.
* `pan-current-class`: Will run the test of the current class.
* `pan-run-current-test`: Will run the current test directly.
* `pan-choose-test-to-run`: Will ask you for a test to run.
* `pan-switch-test-func`: Will switch between the function and the test and records it (see below).
* `pan-venv-workon`: Will setup the virtualenv variable with the help of the [virtualenvwrapper](https://github.com/porterjamesj/virtualenvwrapper.el) emacs mode of your tox environment.

## Switch between test and function

This idea come from an [intelij](https://www.jetbrains.com/idea/help/navigating-between-test-and-test-subject.html) feature. If you are in your code and have a function there you can run the function to `pan-switch-test-func` and it will ask you for a test (taken directly from testr) and jump to it directly. If you call `pan-switch-test-func` again from the function test it will jump back to the function and same again since it will be recorded. Just specify `C-u` again if you need to specify an another test.

![A GiF image demonstrating the feature](http://i.imgur.com/pzP7dHr.gif)

## Motivation

I was quite bugged by the testr *UI* and launching with [tox](https://github.com/chmouel/tox.el) directly was taking way too much time for me for a specific test. I started to develop a [quick shell script](https://gist.github.com/chmouel/60a374ba24ebd2e12061) to do that directly from the terminal with the help of zsh but doing it from Emacs is (obviously :)) much quicker. I still use that tool to switch quickly between venv in shell and I kept the name :)

![A GiF image demonstrating the feature](http://i.imgur.com/kJsJTjj.gif)

## Author

Chmouel Boudjnah - <chmouel@chmouel.com>

## License

GPL (see the top of [pan.el](pan.el) file)
