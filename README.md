# Tauri Webdriver Test
A demo to run [WebDriver Test](https://tauri.app/v1/guides/testing/webdriver/introduction) on macOS with Apple Silicon.

## Create Lima VM

```
limactl start --name=tauri-webdriver lima.yaml
```


## build and run tauri project
`cargo build` takes long time when tauri projects are shared between host and lima VM. Therefore, we need to copy tauri project files to lima-local location.

By default, user directories in macOS are mounted as readonly. Copy `tauri-webdriver-test` directory to lima-local location: 

```
cp /Users/<username_of_macos>/path/to/tauri-webdriver-test $HOME/
cd $HOME/tauri-webdriver-test
```

Then, you can build and run tauri project

```
yarn tauri dev
```

## developing tauri project
You can find ssh config for lima VM by hitting command below:

```
limactl show-ssh tauri-webdriver
```

You can edit tauri project using VSCode Remote-SSH.