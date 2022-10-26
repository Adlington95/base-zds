# Zebra Design System React Components

## Install

```bash
  npm i @zebra-fed/zds-react
```

## Peer Dependencies

-`React`

## Usage

This library is build with theme in mind. To use the library, the entire react application must be wrapped in `<StripesTheme>`

```js
import { StripesTheme } from "@zebra-fed/zds-react";

<StripesTheme>
  <App />
</StripesTheme>;
```

Importing components:

```js
import { Button, Avatar, Pagination, Table } from "@zebra-fed/zds-react";
```

Importing and using Interfaces with Components

```js
import { Button, ButtonType, SizeType } from "@zebra-fed/zds-react";

return (
  <Button type={ButtonType.Basic} size={SizeType.Large}>
    Button
  </Button>
);
```

# Building a SVG Library for your Application

NOTE: By default the icons property below is being set to our default icon library. However, if you wish to override said library with your own icon library then please follow the following steps. However, it would be highly recommended to reach out to marc.adlington1@zebra.com before moving on to the next step.

The `<SVGIcon />` component requires the configuration of a iconLibrary passed through to the Stripes theme for it to pick up the symbols. This is configured like such:

```javascript
import { icons } from "../resources/iconLibrary";
const themeObj = {
  icons: icons,
};

<StripesTheme mode={"dark"} theme={themeObj}>
  // body of your app
</StripesTheme>;
```

The Stripes project exposes a script that will take a folder of SVG icons, iconography that is specific to your application, and compiles it into a single iconLibrary string that will be ingested into the Stripes theming engine.

The filename of the svg files will be used as the iconid property when referencing the icon in the `<SVGIcon />` tag within your app.

The script can be access via:

```bash
npm run buildIcons --folder ./resources/default
```

the argument that follows the --folder string will be the source folder for your svg files. It will recursively search through the folder and compile all svg objects into a single string.

## Development

You can easily develop and interact with your components. To run the local server, simply run:

```bash
$ yarn start
```
