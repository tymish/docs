## Tymish - Small Business Time Sheet Manager

Track, approve and manage incoming timesheets from your employees and contractors.

In development...

### Runtime Dependencies
* Node.js - [https://nodejs.org/en/](https://nodejs.org/en/)
* .NET Core SDK - [https://dotnet.microsoft.com/download](https://dotnet.microsoft.com/download)
* MySQL Server v8.0.* - [https://dev.mysql.com/downloads/mysql/](https://dev.mysql.com/downloads/mysql/) 
   * Requires [Python](https://www.python.org/downloads/)
   * [Windows MySQL Installer MSI](https://dev.mysql.com/downloads/windows/installer/8.0.html)

### Tools
* Visual Studio Code - [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download)
* MySQL Workbench - [https://dev.mysql.com/downloads/workbench/](https://dev.mysql.com/downloads/workbench/)
* Git - [https://git-scm.com/downloads](https://git-scm.com/downloads)
* Postman - [https://www.getpostman.com/downloads/](https://www.getpostman.com/downloads/)

### Setup Instructions
1. Create a directory/folder `Tymish`
2. Clone the three repositories into the `Tymish` directory
   * `git clone https://github.com/tymish/api`
   * `git clone https://github.com/tymish/azure-function-proxy`
   * `git clone https://github.com/tymish/angular-ui`
3. Setup MySQL Database - [MySQL data script](https://github.com/tymish/api/blob/master/src/timeish.sql)
4. Setup [tymish/api](https://github.com/tymish/api)
5. Setup [tymish/azure-function-proxy](https://github.com/tymish/azure-function-proxy)
6. Setup [tymish/angular-ui](https://github.com/tymish/angular-ui)

## Local Database User Connection string
`Server=localhost;Port=3306;Database=timeish;Uid=efuser;Pwd=password;`
