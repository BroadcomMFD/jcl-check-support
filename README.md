<div id="header" align="center">

[![GitHub issues](https://img.shields.io/github/issues-raw/BroadcomMFD/jcl-check-support)](https://github.com/BroadcomMFD/jcl-check-support/issues)
[![downloads](https://img.shields.io/visual-studio-marketplace/d/broadcomMFD.jcl-check-support)](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.jcl-check-support)
[![Code4z](https://img.shields.io/badge/Code4z-marketplace-cc092f)](https://marketplace.visualstudio.com/search?term=code4z&target=VSCode)

</div>

# JCL Check

The JCL Check extension provides an interface in VS Code for developers and system administrators to interact with Job Control Language (JCL) on IBM z/OS mainframes.

The extension provides the following benefits:

- Edit JCL in VS Code to enhance developer productivity.
- Use the linting feature to write JCL efficiently.
- Ensure that JCL is valid prior to job submission by integrating with JCLCheck on the mainframe.
- Produce JCLCheck reports in markdown format to share with your team.

<br />
<img align="left" alt="This extension is part of the Code4z experience" width="80" height="82" src="https://raw.githubusercontent.com/BroadcomMFD/code4z/refs/heads/main/icon5.png" />

JCL Check is part of the [Code4z](https://techdocs.broadcom.com/code4z) experience from Broadcom, which offers a modern experience for mainframe application developers. To get started with Code4z, check out our foundational [extension pack](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.code4z-extension-pack).

<br />

## Contents

- [Address Software Requirements](#address-software-requirements)
- [Configuring](#configuring)
- [Using](#using)

## Address Software Requirements

You can use the JCL syntax highlighting/coloring and snippets generation features provided by the JCL Language support extension. The JCL Language Support extension is installed along with the JCL Check extension.

If you want to use JCLCheck's linting and reporting features, you must meet the following requirements:

- JCLCheck Workload Automation v12.0 is installed and configured on a mainframe system with the latest maintenance applied.
- An instance of JCLCheck Workload Automation v12.0 REST API server is running.
- Integrate this extension with [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) and set up a Zowe profile.
- If you are using this extension without Zowe Explorer then you should have [Zowe CLI](https://docs.zowe.org/stable/user-guide/cli-installcli.html) and the [JCLCheck Plug-in for Zowe CLI](https://techdocs.broadcom.com/us/en/ca-mainframe-software/devops/enterprise-support-for-zowe/1-0/zowe-cli/using-zowe-cli/available-cli-plug-ins/jclcheck-plug-in-for-zowe-cli.html) installed on your PC.

## Configuring

To connect with a JCLCheck instance on the mainframe, create a `jclcheck` service profile on your computer using the JCLCheck Plug-in for Zowe CLI.

To create a JCLCheck plug-in profile via config command, gather the following data:

1. The host name of the LPAR on which JCLCheck Web Services is running
2. A username that has authority to access JCLCheck Web Services
3. The password to the account tied to the username

To create a JCLCheck profile through configuration command, issue the following command and provide the above details as prompted:

```sh
zowe config init
```

After you create the profile in the CLI, it will become available for use in VS Code. You can now perform JCLCheck actions in the extension using your default profile.
The JCLCheck Features option must also be enabled as mentioned under Advanced configuration.

### Advanced configuration

To access extension settings, navigate to **File > Preferences > Settings**, then select **Extensions > JCL Check**.

You can configure the following options:

- **JCLCheck features -** Enable the linting and reporting features provided by the JCLCheck REST API. Ensure that you meet the software requirements before you use these features. (Default: Off)
- **Automatic linting on save -** Choose to perform linting manually, or automatically lint for each local save. You must enable the 'JCLCheckfeatures' option to use linting. (Default: On)
- **Reports location -** Specify the local folder where JCLCheck reports are saved. If you leave the setting blank, the extension prompts you for a location when you generate a report.
- **Server tracing -** Traces communication between VS Code and the language server. Specify Off, Messages, or Verbose. (Default: Off)

    ```json
    "[jcl]" : { "editor.rulers" : [71, 72, 80]},
    ```

## Using

Review the following use cases to understand how to use the JCL Check extension:

### Accessing JCL locally

This extension *does not* provide the ability for you to download from, upload to, or submit jobs on the mainframe. To access mainframe code on your computer, use a tool such as Zowe CLI or Zowe Explorer.

### JCL Linting

Perform linting to check your JCL for programmatic or stylistic errors. You can perform linting manually, or enable automatic linting on save.

**Note:** To use linting, you must meet the software requirements and enable the "JCLCheck features" option. Automatic linting is enabled by default. See [Configuring](#configuring) for more information.

**Follow these steps:**

1. Open the command palette with `Ctrl/Cmd + Shift + P`
2. Type "Check your JCL".
3. Click the command or press Enter to perform linting.

   JCL problems are highlighted in your code and displayed in the VS Code **Problems** view.

![JCLCheck linting](/docs/images/jck-linting.gif)

### Producing and sharing JCLCheck reports

Run JCLCheck against your code and produce convenient reports in markdown format.

**Note:** To use reporting, you must meet the software requirements and enable the "JCLCheck features" option. See [Configuring](#configuring) for more information.

**Follow these steps:**

1. Open the command palette with `Ctrl/Cmd + Shift + P`
2. Type "Generate JCL report".
3. Click the command or press Enter to generate a report.
4. When prompted for a filename, enter a location where the report should be saved and click **OK** to continue.

The report opens in VS Code after it is generated. Reports are created in the folder that you specified in the prompt, or that you specify in the extension settings.

![JCLCheck report generation](/docs/images/jck-report.gif)

**Tip:** If you want to convert your JCLCheck report from Markdown format into PDF, HTML, PNG, or JPEG, we recommend using the extension [Markdown PDF by yzane](https://marketplace.visualstudio.com/items?itemName=yzane.markdown-pdf).

### Integrate with Zowe Explorer and JCL Language Support

Integrate this extension with [Zowe Explorer](https://marketplace.visualstudio.com/items?itemName=Zowe.vscode-extension-for-zowe) and set up a Zowe profile to enable hyperlinks to PDS members and USS files in your JCL code. You can also use Zowe Explorer to submit jobs, and to access your mainframe data sets containing JCL directly from VS Code.

The JCL Language Support extension enables syntax awareness features and code snippets for JCL code. JCL Language Support is automatically installed along with JCL Check. For more information, see the [JCL Language Support documentation](https://marketplace.visualstudio.com/items?itemName=broadcomMFD.jcl-language-support).

<div align="center">
<a href="https://www.openmainframeproject.org/all-projects/zowe/conformance"><img alt="This extension is Zowe v3 conformant" src="https://artwork.openmainframeproject.org/other/zowe-conformant/zowev3/explorer-vs-code/color/zowe-conformant-zowev3-explorer-vs-code-color.png" width=208 height=156 /></a>
</div>

For more information about this extension, please visit the [documentation on Broadcom TechDocs](https://techdocs.broadcom.com/us/en/ca-mainframe-software/automation/ca-jclcheck-workload-automation/12-0/building/interfaces-with-other-products/jcl-check-extension-for-vs-code.html).

---------------------------------------------------------------

## **Technical Assistance and Support for JCL Check extension**

The JCL Check extension is made available to customers on Visual Studio Code Marketplace in accordance with the terms and conditions contained in the provided End-User License Agreement (EULA).

If you are on active support for JCLCheck Workload Automation, you get technical assistance and support in accordance with the terms, guidelines, details, and parameters that are located within the Broadcom [Working with Support](https://support.broadcom.com/external/content/release-announcements/CA-Support-Policies/6933) guide.

This support generally includes:

- Telephone and online access to technical support
- Ability to submit new incidents 24x7x365
- 24x7x365 continuous support for Severity 1 incidents
- 24x7x365 access to Broadcom Support
- Interactive remote diagnostic support
- Technical support cases must be submitted to Broadcom in accordance with guidance provided in “Working with Support”.

Note: To receive technical assistance and support, you must remain compliant with “Working with Support”, be current on all applicable licensing and maintenance requirements, and maintain an environment in which all computer hardware, operating systems, and third party software associated with the affected Broadcom software are on the releases and version levels from the manufacturer that Broadcom designates as compatible with the software. Changes you elect to make to your operating environment could detrimentally affect the performance of Broadcom software and Broadcom shall not be responsible for these effects or any resulting degradation in performance of the Broadcom software. Severity 1 cases must be opened via telephone and elevations of lower severity incidents to Severity 1 status must be requested via telephone.

------------------------------------------------------------------------------------------------
Copyright © 2020 Broadcom. The term "Broadcom" refers to Broadcom Inc. and/or its subsidiaries.
