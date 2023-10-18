# Generate Allure Test Report with WebDriverIO

To generate an Allure test report with WebDriverIO, you can follow these steps:

## Prerequisites

Before you start, make sure you have the following prerequisites installed:

1. **Node.js**: You'll need [Node.js](https://nodejs.org/) installed on your machine.

2. **WebDriverIO**: Install WebDriverIO globally using npm:

    ```bash
    npm install -g webdriverio
    ```

3. **Java**: You need [Java](https://www.oracle.com/java/technologies/javase-downloads.html) installed to run Allure.

4. **Install Allure**: Install the Allurew dependencies using npm:

    ```bash
    npm install @wdio/allure-reporter --save-dev
    ```
    
5. **Allure Command Line**: Install the Allure command-line tool using npm:

    ```bash
    npm install -g allure-commandline
    ```

## Initialize a New WebDriverIO Project

1. Create a new directory for your WebDriverIO project and Initialize a new Node.js project using npm:

    ```bash
    npm init -y
    ```

2. Initialize WebDriverIO using npm:

    ```bash
    npm init wdio .
    ```

    This single command downloads the WebdriverIO CLI tool and runs a configuration wizard that helps you configure your test suite.

## Configure WebDriverIO

1. Open the `wdio.conf.js` file in your project directory.

2. Customize the configuration to suit your needs. For example, you can configure the specs to point to your test files, specify the browser, and other settings. Here's a minimal example:

    ```bash
    exports.config = {
        reporters: ['spec', ['allure', {
            outputDir: 'allure-results',
            disableWebdriverStepsReporting: false,
            disableWebdriverScreenshotsReporting: false,
            addConsoleLogs: false,
        }]],
    }
    ```

After writing the test case or setting up the test suite, run your spec file:
```bash
npx wdio run ./wdio.conf.js --spec <file-name>.js
```
## Generate Allure Report

After successfully running the test case, use the following command to generate the Allure Report:

```bash
allure generate allure-reports && allure open
```
https://github.com/iniyavans/Allure-Report-using-WebdriverIO/assets/88368294/fee5e662-3a8c-44e7-8ea4-80e41cb077a4

In the above command, allure-reports represents the outputDir specified in the configuration file.

Running the command above will generate a new report and open it on a local web server. The server typically starts at http://192.168.1.158:65524.

If you want to generate a new report after already having one, you'll need to clean the existing report. You can do this using the following command:

``` bash
allure clean
```

This command will remove the existing Allure report data, including any previously generated reports, screenshots, logs, and other related files. Alternatively, you can manually delete the allure-report folder.

After running allure clean, you can proceed to run your tests again. This will generate a new set of report data in the allure-results directory. You can then generate a fresh Allure report based on the new data when needed.

## Reference

[WebDriverIO](https://webdriver.io/docs/gettingstarted/)

[Allure Report](https://allurereport.org/docs/)

### Author

- [Iniyavan](https://github.com/iniyavans)
