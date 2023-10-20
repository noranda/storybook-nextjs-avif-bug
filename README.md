# Storybook + Next.js AVIF Import Bug

## Reproduction

To reproduce:

- `yarn install`
- `yarn storybook`

You should get an error like:

```
ERROR in ./src/components/avif-test-image.avif
Module build failed (from ./node_modules/@storybook/nextjs/dist/next-image-loader-stub.js):
TypeError: unsupported file type: undefined (file: ./src/components/avif-test-image.avif)
    at lookup (./node_modules/image-size/dist/index.js:42:11)
    at imageSize (./node_modules/image-size/dist/index.js:113:16)
    at Object.nextImageLoaderStub (./node_modules/@storybook/nextjs/dist/next-image-loader-stub.js:1:1144)
 @ ./src/components/Example.tsx 4:0-51 7:9-26
 @ ./src/stories/Example.stories.tsx 1:0-44 6:13-20
 @ ./src/ lazy ^\.\/.*$ include: (?:\/src(?:\/(?%21\.)(?:(?:(?%21(?:^%7C\/)\.).)*?)\/%7C\/%7C$)(?%21\.)(?=.)[^/]*?\.stories\.(js%7Cjsx%7Cmjs%7Cts%7Ctsx))$ chunkName: [request] namespace object ./stories/Example.stories.tsx ./stories/Example.stories
 @ ./storybook-stories.js 23:11-27:5
 @ ./storybook-config-entry.js 6:0-50 25:21-29 28:2-31:4 28:58-31:3 30:31-39
```

- Running `yarn dev` to verify that next.js is able to load the image

## Info

```
Storybook Environment Info:

  System:
    OS: macOS 13.5.1
    CPU: (10) arm64 Apple M1 Pro
    Shell: 5.9 - /bin/zsh
  Binaries:
    Node: 18.17.1 - ~/.asdf/installs/nodejs/18.17.1/bin/node
    Yarn: 3.6.4 - ~/.asdf/installs/nodejs/18.17.1/.npm/bin/yarn <----- active
    npm: 9.6.7 - ~/.asdf/plugins/nodejs/shims/npm
  Browsers:
    Chrome: 118.0.5993.88
    Safari: 17.0
  npmPackages:
    @storybook/addon-essentials: ^7.5.1 => 7.5.1
    @storybook/addon-interactions: ^7.5.1 => 7.5.1
    @storybook/addon-links: ^7.5.1 => 7.5.1
    @storybook/addon-onboarding: ^1.0.8 => 1.0.8
    @storybook/blocks: ^7.5.1 => 7.5.1
    @storybook/nextjs: ^7.5.1 => 7.5.1
    @storybook/react: ^7.5.1 => 7.5.1
    @storybook/testing-library: ^0.2.2 => 0.2.2
    eslint-plugin-storybook: ^0.6.15 => 0.6.15
    storybook: ^7.5.1 => 7.5.1
```
