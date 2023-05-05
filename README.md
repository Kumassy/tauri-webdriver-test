# Tauri Webdriver Test
A demo to run [WebDriver Test](https://tauri.app/v1/guides/testing/webdriver/introduction) on macOS with Apple Silicon.

## Create Lima VM

```
limactl start --name=tauri-webdriver lima.yaml
```


## Running Test on Lima VM
You can use file sharing features to build tauri project.
However, `cargo build` on shared filesystem is slow and unstable. 
Please copy tauri project to Lima-local directory.

You can see tauri project as read-only:

```
ls /Users/<macOS user name>/path/to/tauri-webdriver-test
```

Copy tauri project to Lima-local writable directory:

```
cp -r /Users/<macOS user name>/path/to/tauri-webdriver-test $HOME/
```

Then, you can build tauri project

```
cd $HOME/tauri-webdriver-test
yarn install
yarn test
```

## Develop on Lima VM
You can use VSCode Remote-SSH features to edit files located at Lima-local diretory.


This command gives ssh settings to connect to Lima VM:

```
limactl show-ssh tauri-webdriver
```

Open VSCode and paste the output. Then, you can use Remote-SSH feature to edit files inside Lima VM.
