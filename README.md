[![DegateBanner](etc/degate_banner.png)](https://github.com/DegateCommunity)

<p align="center">
    <a href="https://gitter.im/DegateCommunity/Degate" alt="Gitter">
        <img src="https://badges.gitter.im/DegateCommunity/Degate.svg" /></a>
    <a href="https://github.com/DegateCommunity/Degate/blob/master/LICENSE.TXT" alt="License">
        <img src="https://img.shields.io/github/license/DegateCommunity/Degate" /></a>
    <a href="https://github.com/DegateCommunity/Degate/issues" alt="GitHub Issues">
        <img src="https://img.shields.io/github/issues/DegateCommunity/Degate" /></a>
    <a href="https://github.com/DegateCommunity/Degate/commits/develop" alt="Last Commit">
        <img src="https://img.shields.io/github/last-commit/DegateCommunity/Degate/develop" /></a>
    <a href="https://github.com/DegateCommunity/Degate/releases" alt="Last Release">
        <img src="https://img.shields.io/github/release-date-pre/DegateCommunity/Degate" /></a>
    <a href="https://github.com/DegateCommunity/Degate/graphs/contributors" alt="Contributors">
        <img src="https://img.shields.io/github/contributors/DegateCommunity/Degate" /></a>
</p>

&nbsp;

This is the Degate documentation repository. Degate is a multi-platform software for semi-automatic VLSI reverse engineering of digital logic in chips. This project is a fork of the initial Degate project, the final goal is to replace it. For more please visit our [wiki](https://github.com/DegateCommunity/Degate/wiki) page and, if you want to chat, visit our [Gitter](https://gitter.im/DegateCommunity/Degate). The current project maintainer is [Dorian Bachelot](https://github.com/DorianBDev).

&nbsp;

- [Build](#build)
  - [Dependencies](#dependencies)
  - [Quick start](#quick-start)
    - [For Linux (debian-like)](#for-linux-debian-like)
    - [For Windows](#for-windows)
    - [For all platform](#for-all-platform)
- [Localization](#localization)
  - [Add/Update a language](#addupdate-a-language)
  - [Generate documentation](#generate-documentation)
    - [For BSD/GNU:](#for-bsdgnu)
    - [For Windows cmd.exe:](#for-windows-cmdexe)
    - [For Windows PowerShell:](#for-windows-powershell)
- [License](#license)

&nbsp;

# Build

## Dependencies

- Python 3,
- Sphinx,
- Read the Docs Sphinx Theme.

## Quick start

Firstly, clone this repository (help [here](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository)).

### For Linux (debian-like)

Install dependencies:
```console
> sudo apt-get install python3
```

### For Windows

Install dependencies:
- CMake: https://cmake.org/download/
- Python 3: https://www.python.org/downloads/

### For all platform

Install sphinx and read-the-docs (with administrator privileges):
```console
> pip install sphinx
> pip install sphinx-rtd-theme
```

Then you just have to select the build type, for example:
```console
> make html
```

The documentation will be built in the 'build' folder.

# Localization

In these generated files (under 'locale/desired_language_identifier/' directory) you will be able to translate strings of the documentation.

To make the translation process easier you can use a '.po' file editor like [Poedit](https://github.com/vslavik/poedit).

## Add/Update a language

To add or update a language, please follow below steps.

Install dependencies:
```console
> pip install sphinx-intl
```

Then, generate pot files in the 'build/gettext' directory.
```console
> make gettext
```

Now we need to generate '.po' files. Use the command below and replace the 'desired_language_identifier' variable with the desired language identifier. A list is available [here](https://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language).
```console
> sphinx-intl update -p build/gettext -l desired_language_identifier
```

## Generate documentation

To generate documentation in a specific language, use these commands:

### For BSD/GNU:

```console
> make -e SPHINXOPTS="-D language='desired_language_identifier'" html
```

### For Windows cmd.exe:

```console
> set SPHINXOPTS=-D language=desired_language_identifier
> make.bat html
```

### For Windows PowerShell:

```console
> Set-Item env:SPHINXOPTS "-D language=desired_language_identifier"
> make.bat html
```

For more please see : https://www.sphinx-doc.org/en/master/usage/advanced/intl.html.

# License

Degate is released under the GNU General Public License Version 3. See LICENSE file for details.
