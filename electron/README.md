This demonstrates how to package an Electron app using Batis.
It contains a copy of the [electron quick start](https://github.com/atom/electron-quick-start)
example (© Github, MIT licensed).

It uses [electron-packager](https://github.com/maxogden/electron-packager);
install this by running:

    npm install -g electron-packager

In this example, a launcher entry is set up (see the file `batis_info/desktop/batis-electron-example.desktop`),
but the application is not made available as a shell command (no `commands` key in `batis_info/metadata.json`).
To set up shell commands for your application, see the metadata files of other examples.
