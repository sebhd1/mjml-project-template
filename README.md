# MJML Boilerplate

This repository contains a project boilerplate for [MJML](https://mjml.io) email.

**MJML** is a framework that uses a custom Markup Language that transpiles to an extreme compatible HTML, 
optimized for mails.

Further information can be found on the [Official documentation](https://documentation.mjml.io).

_**Notes for JetBrains users:** it's suggested to use [MJML Support plugin](https://plugins.jetbrains.com/plugin/16418-mjml-support)._

## Requirements

- [Node.js](https://nodejs.org)

## Installation Steps

The first step is to initialize the project with npm:

```shell
npm init -y
```

The next step is to install the [MJML package](https://www.npmjs.com/package/mjml) 
as a development dependency:

```shell
npm install -D mjml
```

The installation process is finished!

## Useful commands

| Command                              | Description                                                   |   Use case    |
|--------------------------------------|---------------------------------------------------------------|:-------------:|
| `npx mjml -w input.mjml`             | Compiles the MJML file everytime the file is modified         |  Development  |
| `npx mjml --validate input.mjml`     | Validates the MJML syntax in the given file                   | Before deploy |
| `npx mjml input.mjml -o output.html` | Compiles the MJML file once without watching (`-w`) for edits |   To deploy   |

## Notes

- All the self-closing tags should be closed inline as in XHTML;
- All the email content must be inside a `mj-column` (which must be inside a `mj-section`);
- MJML has an HTML `style` tag counterpart named `mj-style`, it also provides an attribute to convert the given CSS to inline style (`inline="inline"`);
- MJML supports external stylesheet files that can be imported using `mj-include` tag, but keep in mind to specify the file type like this: `type="css"`;
- External stylesheet files can also be used inline via the attribute `css-inline="inline"` on the `mj-include`;
- `mj-include` can even import other MJML files or HTML files (specifying the type like this: `type="html"`);
- Be careful when using CSS on MJML components because most of them converted to a div. Keep in mind to focus on the resulting HTML and less on the MJML source;
- MJML doesn't support `id` attribute;
- MJML has two kind of classes: `css-class` (taken from CSS) and `mj-class` (which are declared via `mj-class` tag);
- `mj-class` uses MJML attributes to stylize a component, and it gets automatically converted to inline style;