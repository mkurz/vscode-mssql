# Change Log

## Version 1.1
* Release date: July 18, 2017
* Release status: GA


## What's new in this version
* Preview support for Integrated Authentication (aka Windows Authentication) on Mac and Linux. To use this you need to create a Kerberos ticket on your Mac or Linux machine - [see this guide](https://aka.ms/vscode-mssql-integratedauth) for the simple process. Once this is set up, you can say goodbye to SQL passwords when connecting to your servers!
  * This feature is in preview in .Net Core 2.0. The [corefx repository](https://github.com/dotnet/corefx) tracks issues related to SqlClient and we recommend issues setting up Kerberos tickets be raised there.
  * macOS "El Capitan" and older versions will not support this feature or any other features requiring a new SqlToolsService version. To benefit from Integrated Authentication, "Execute Current Statement" and other new features we recommend updating to the latest OS version.
* New code snippets:
  * `sqlGetSpaceUsed` shows space used by tables. Thanks to Rodolfo Gaspar for this contribution!
  * `sqlListColumns` shows columns for tables matching a `LIKE` query. Thanks to Emad Alashi for this contribution!
* Support for connecting using a connection string. When adding a connection profile you can now paste in an ADO.Net connection string instead of specifying server name, database name etc. individually. This makes it easy to get strings from the Azure Portal and use them in the tool.
* Support for empty passwords when connecting. Password is no longer required, though still recommended! This is useful in local development scenarios.
* Improved support for SQL Server 2017 syntax by refreshing IntelliSense and SMO dependencies.
* Fixed all code snippets so that tab ordering is improved and snippets no longer have syntax errors
* Fixed issue where snippets were not shown when `mssql.intelliSense.enableIntelliSense` was set to `false`.
* Fixed issue [#911](https://github.com/Microsoft/vscode-mssql/issues/911) where tools service crashed when Perforce source code provider is enabled in the workspace.
* Stability fixes to reduce the likelihood of SqlToolsService crashes.
* Fixed issue [#870](https://github.com/Microsoft/vscode-mssql/issues/870). Added an "Execute Current Statement" command that executes only the SQL statement where the cursor is currently located.
* Fix issue [#939](https://github.com/Microsoft/vscode-mssql/issues/939) "Show execution time for individual batches". To enable open your settings and set `mssql.showBatchTime` to `true`.
* Fix issue [#904](https://github.com/Microsoft/vscode-mssql/issues/904). Added a "Disconnect" option to the status bar server connection shortcut. Clicking on this now lists databases on the current server and a "Disconnect" option.
* Fix issue [#913](https://github.com/Microsoft/vscode-mssql/issues/913). OpenSuse Linux distributions are now supported.

## Version 1.0
* Release date: May 2, 2017
* Release status: GA

## What's new in this version
* We are please to announce the official GA of the MSSQL extension! This release focuses on stability, localization support, and top customer feedback issues
* The MSSQL extension is now localized. Use the `Configure Language` command in VSCode to change to your language of choice. Restart the application and the MSSQL extension will now support your language for all commands and messages.
* Community-added support for `Save as Excel`, which supports saving to .xlsx format and opening this in the default application for .xlsx files on your machine.
* Numerous bug fixes:
  * IntelliSense improvements to support configuration of Intellisense options from user settings, plus keyword fixes.
  * Query Execution fixes and improvements: [#832](https://github.com/Microsoft/vscode-mssql/issues/832), [#815](https://github.com/Microsoft/vscode-mssql/issues/815), [#803](https://github.com/Microsoft/vscode-mssql/issues/803), [#794](https://github.com/Microsoft/vscode-mssql/issues/794), [#772](https://github.com/Microsoft/vscode-mssql/issues/772)
  * Improved support for downloading and installing the tools service behind proxies
  * Improvements to `Go To Definition` / `Peek Definition` support [#769](https://github.com/Microsoft/vscode-mssql/issues/769)


## Contributions and "thank you"
We would like to thank all our users who raised issues, and in particular the following users who helped contribute features or localization of the tool:
* Wujun Zhou, for adding the `Save as Excel` feature
* The many contributors to our community localization. A full list is available on [this TechNet post](https://blogs.technet.microsoft.com/dataplatforminsider/2017/04/13/crossplatform-tools-for-sql-server-opened-for-community-localization/). Particular thanks to Mona Nasr for coordinating our community localization efforts.

## Version 0.3.0
* Release date: March 1, 2017
* Release status: Public Preview

## What's new in this version
* T-SQL formatting support is now included. This is a highly requested feature, and this release includes a basic parser
with configuration options for some of the most common T-SQL formatting styles.
  * To format a .sql file, right-click and choose `Format Document`.
  * To format part of a document, highlight a selection, right-click and choose `Format Selection`
  * To change the formatting settings, hit F1 and choose `Preferences: Open User Settings`. Type in `mssql.format` and
  change any of the options
* `Refresh Intellisense Cache` command added. This will rebuild the intellisense for a connected database to include any recent
schema changes
* `New Query` command added. This opens a new .sql file and connects to a server, making it quicker to get started with your queries
* Fixed support for SQL Data Warehouse connections.
* Prototype localization support added. We will be adding full localization support in a future update.
* Improved Peek Definition support. Multiple bug fixes, and additional supported types.
  * Supported types: Tables, Views, Procedures, User Defined Tables, User Defined Types, Synonyms, Scalar Functions, Table Valued Functions
* Support for Windows x86 machines
* Fix for issue #604 where results that included HTML were not rendered correctly
* Multiple fixes for syntax highlighting
* Fixed issues where query execution failed due to parser failures.

## Version 0.2.1
* Release date: February 2, 2017
* Release status: Public Preview

## What's new in this version
* HotFix for issue [#669] "Results Panel not Refreshing Automatically". This issue impacts users on VSCode 1.9.0 or greater.

## Version 0.2.0
* Release date: December, 2016
* Release status: Public Preview

## What's new in this version
* Peek Definition and Go To Definition support for Tables, Views and Stored Procedures. For a query such as `select * from dbo.Person` you can right-click on `dbo.Person` and see it as a `CREATE TABLE` script.
* Support for additional operating systems including Linux Mint and Elementary OS. See [Operating Systems] for the list of supported OSes.
* Output window now shows status of SQL tools service installation to make it easier to track install-time issues.
* Progressive Result Sets: when running multiple queries at once, you'll now see result sets appear as soon as they are done processing instead of waiting for all queries to complete.
The extension supports result set-level updates with per-row updates coming in a future update.
* Multiple results view improvements: improved keyboard navigation, configuration settings to alter default font style and size, support for copying with column headers.
* Multiple IntelliSense improvements: Support using  `[bracket].[syntax]`, handling of `"` at the end of a word, improved performance when connecting to same DB from a new file.

## Version 0.1.5
* Release date: Nov 16, 2016
* Release status: Public Preview

## What's new in this version

The SQL Tools team is excited to announce that the first public preview release of **mssql** for Visual Studio Code is available in the Visual Studio Code Marketplace. Try it and provide your feedback or report any issue to [GitHub Issue Tracker].

If you are new to VS Code and the mssql extension, see the [getting started tutorial] for step-by-step guides. For more about how-to guides see [the mssql extension wiki].

**Quick summary of the mssql extension features**

This extension makes it easy to connect to, query and modify your SQL Server, Azure SQL Database, and Azure SQL Data Warehouse instances.

* Create and manage your frequent connections to SQL Server, Azure SQL Database and Azure SQL Data Warehouse as a profile. The mssql extension keeps the recent history of your connection activities and saves passwords in a secure store, making connecting to your database easy. Create, Edit, Remove and Clear your recent connections. See [manage connection profiles] for more details.

* Productive T-SQL editor features including IntelliSense with suggestions and auto-completion, syntax highlighting and real-time T-SQL error checks and reporting.

* Execute T-SQL scripts and view results, all with a native Visual Studio Code look and feel. View query results and related messages without needing to tab between them.

* Save query results as CSV or JSON.

* Customize shortcuts, color themes and options to meet your preference.

* This is an open source project under the MIT license. Go check out how to [contribute].

## Upcoming changes and features

* Top customer reported issues in [GitHub Issue Tracker].

* Faster performance: Progressive query results. As soon as SQL Server returns results to the extension these should be shown to the user, even for large queries.

* Delivery of additional T-SQL editor features, for example support for Go To Definition and Find All References.

* More bugs fixes and fine tuning of features.

## Fixed Issues

Report issues to [Github Issue Tracker] and provide your feedback.

## Known Issues

* The mssql extension process may crash due to a bug in the product. It requires to restart VS Code to recover. Before restarting VS Code, please save your files.

* Installation Prerequisites: this extension requires the user to install some components needed by .Net Core applications, since this is used for connectivity to SQL Server.

    * For Mac OS, see [OpenSSL requirement on macOS]

    * For Windows 8.1, Windows Server 2012 or lower, see [Windows 10 Universal C Runtime requirement]

[getting started tutorial]:https://aka.ms/mssql-getting-started
[the mssql extension wiki]:https://github.com/Microsoft/vscode-mssql/wiki
[contribute]:https://github.com/Microsoft/vscode-mssql/wiki/contributing
[GitHub Issue Tracker]:https://github.com/Microsoft/vscode-mssql/issues
[manage connection profiles]:https://github.com/Microsoft/vscode-mssql/wiki/manage-connection-profiles
[OpenSSL requirement on macOS]:https://github.com/Microsoft/vscode-mssql/wiki/OpenSSL-Configuration
[Windows 10 Universal C Runtime requirement]:https://github.com/Microsoft/vscode-mssql/wiki/windows10-universal-c-runtime-requirement
[Operating Systems]:https://github.com/Microsoft/vscode-mssql/wiki/operating-systems
[#669]:https://github.com/Microsoft/vscode-mssql/issues/669
