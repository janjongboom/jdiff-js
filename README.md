# JDiff.js

JavaScript adaptation of [JojoDiff](https://sourceforge.net/projects/jojodiff/) by Joris Heirbaut. For more information and to see the API, see the JojoDiff project page on SourceForge. The project is written in C++, then cross-compiled through Emscripten so it can be used by any JavaScript client.

JojoDiff is great because it generates linear patch files, which can be applied in a very memory-efficient manner. We're using this in [janpatch](https://github.com/janjongboom/janpatch) - a patching library for embedded systems that can run in very little memory. This allows us to bring delta updates to even the smallest devices. Having JojoDiff available as a JavaScript library makes it easier to integrate in our build tools.

Currently the library is only available as CLI application, but it'll be adapted into a proper library at some point in the near future.

## Usage

1. Install a recent version of Node.js.
1. Install the project:

    ```
    $ npm install jdiff -g
    ```

1. Use the application:

    ```
    $ jdiff ./file1 ./file2 ./patch-file
    ```

## Compiling

1. Install the [Emscripten SDK](https://kripken.github.io/emscripten-site/docs/getting_started/downloads.html) and make sure `emcc` is in your PATH.
1. Clone this repository:

    ```
    $ git clone https://github.com/janjongboom/jdiff-js
    ```

1. Build the project:

    ```
    $ cd src
    $ make js
    ```

1. Run the project:

    ```
    $ node ../jdiff.js
    ```

## License

GNU General Public License version 3.0 (GPLv3). See COPYING.
