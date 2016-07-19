项目编辑器

原文：[https://gavofyork.gitbooks.io/turboethereum/content/project_editor.html](https://gavofyork.gitbooks.io/turboethereum/content/project_editor.html)

You can use projects to manage the creation and testing of a dapp. The project will contain data related to both backend and frontend as well as the data related to your scenarios (blockchain interaction) for debugging and testing. The related files will be created and saved automatically in the project directory.

你可以使用项目来管理 dapp 的创建和测试。项目包括前端和后端相关的数据，以及你的方案（区块链交互）相关的数据（用于 debug 和测试）。项目相关的文件会在项目目录里自动的创建和保存。

**Creating a new project**

**创建新项目**

The development of a dapp start with the creation of a new project. Create a new project in the “edit” menu. Enter the project name, e.g. "Ratings" and select a path for the project file.

dpp 的开发从创建新项目开始。在 "edit" 菜单中创建新项目。输入项目名称，例如 "rating" ，然后为项目文件选择一个路径。

**Editing backend contract file**

**编辑后端合约文件**

By default, a new project contains a contract “Contract” for backend development on the blockchain using the Solidity language and the “index.html” for the frontend. Check the Solidity tutorial for references.

默认情况下，一个新的项目会包含一个合约 "Contract"，用于使用 Solidity 语言的后端区块链开发，还会包含用于前端的 "index.html"。可参考 Solidity 教程。

Edit the empty default contract “Contract”, e.g.

   contract Rating {

        function setRating(bytes32 _key, uint256 _value) {

            ratings[_key] = _value;

        }

        mapping (bytes32 => uint256) public ratings;

    }

编辑默认的空白合约 "Contract"，例如:

   contract Rating {

        function setRating(bytes32 _key, uint256 _value) {

            ratings[_key] = _value;

        }

        mapping (bytes32 => uint256) public ratings;

    }

Check the Solidity tutorial for help getting started with the solidity programming language.

查看 Solidity 教程，学习如何开始使用 Solidity 编程语言。

Save changes

保存更改。

Editing frontend html files

编辑前端 HTML 文件

Select default index.html file and enter the following code

   <!doctype>

    <html>

    <head>

    <script type="text/javascript">

    function getRating() {

        var param = document.getElementById("query").value;

        var res = contracts["Rating"].contract.ratings(param);

        document.getElementById("queryres").innerText = res;

    }

    function setRating() {

        var key = document.getElementById("key").value;

        var value = parseInt(document.getElementById("value").value);

        var res = contracts["Rating"].contract.setRating(key, value);

    }

    </script>

    </head>

    <body bgcolor="#E6E6FA">

        <h1>Ratings</h1>

        <div>

            Store:

            <input type="string" id="key">

            <input type="number" id="value">

            <button onclick="setRating()">Save</button>

        </div>

        <div>

            Query:

            <input type="string" id="query" onkeyup='getRating()'>

            <div id="queryres"></div>

        </div>

    </body>

    </html>

选择默认的 index.html 文件，输入以下代码：

   <!doctype>

    <html>

    <head>

    <script type="text/javascript">

    function getRating() {

        var param = document.getElementById("query").value;

        var res = contracts["Rating"].contract.ratings(param);

        document.getElementById("queryres").innerText = res;

    }

    function setRating() {

        var key = document.getElementById("key").value;

        var value = parseInt(document.getElementById("value").value);

        var res = contracts["Rating"].contract.setRating(key, value);

    }

    </script>

    </head>

    <body bgcolor="#E6E6FA">

        <h1>Ratings</h1>

        <div>

            Store:

            <input type="string" id="key">

            <input type="number" id="value">

            <button onclick="setRating()">Save</button>

        </div>

        <div>

            Query:

            <input type="string" id="query" onkeyup='getRating()'>

            <div id="queryres"></div>

        </div>

    </body>

    </html>

Then it is possible to add many contract files as well as many HTML, JavaScript, css files.

然后，就可以添加许多合约文件和 HTML / JavaScript / CSS 文件了。
