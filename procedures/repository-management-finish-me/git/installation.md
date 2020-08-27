# Installation

{% tabs %}
{% tab title="Windows" %}
For windows, use this link \([https://gitforwindows.org/](https://gitforwindows.org/)\) and get the "Git for Windows setup" one. When you're given the option, choose to use git from windows command line \(NOT using gitbash\)
{% endtab %}

{% tab title="Mac" %}
First install `brew` using

```text
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew doctor
```

Then install git using

```text
brew install git
```

  Run `git --version` in your command line to confirm that git installed properly and is working\`
{% endtab %}

{% tab title="Linux" %}
Most distributions include `git` by default, though the vast majority of distributions include `git` in the `git` package.
{% endtab %}
{% endtabs %}

