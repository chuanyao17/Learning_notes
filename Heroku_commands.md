# Heroku-Java

## pom.xml

pom.xml 是 Maven 中的核心檔案，其中 "pom" 代表 "Project Object Model"。它是一個 XML 檔案，用於描述 Java 專案的資訊和設定。

## Procfile

是一個 Heroku 特定的設定檔，用於告訴 Heroku 如何運行你的應用程序。當你部署一個應用到 Heroku 時，Heroku 需要知道如何正確啟動你的應用程序，特別是在多種語言和框架中。Procfile 是這個目的的解決方案。

在 Procfile 中，你可以定義多種不同的進程類型，但最常見的進程類型是 web。這告訴 Heroku 如何啟動你的 web 伺服器。

java -jar target/java-getting-started-1.0.0-SNAPSHOT.jar：這是啟動應用程序的命令。它告訴 Heroku 使用 Java 執行 JAR 檔（Java Archive）來啟動應用程序。在這種情況下，應用程序已被打包成名為 java-getting-started-1.0.0-SNAPSHOT.jar 的 JAR 檔，並存放在 target 目錄下。

## ./mvnw clean install 

是一個用於 Maven 專案的命令，它使用 Maven Wrapper 執行 Maven 的兩個生命週期階段：clean 和 install，當執行 ./mvnw clean install 命令時，Maven 根據你專案中的 pom.xml 文件去安裝依賴並進行建構(compile app的意思)。

# Commands

## heroku create

When you create an app, a git remote called heroku is also created and associated with your local git repository.

## heroku addons:create heroku-postgresql:mini

Add a addon to the created app

Add-ons are cloud services that provide out-of-the-box additional services for your application, such as logging, monitoring, 
databases, and more.

## heroku addons:create papertrail

Papertrail 是一個流行的日誌管理工具，它提供即時查看、搜索和警報功能，使你能夠輕鬆監控、排查和解決應用程序問題。

使用命令 heroku addons:open papertrail 打開 Papertrail 來查看日誌

## heroku addons

See all the add-ons provisioned

## git push heroku main

Push the main branch of the current repo to the heroku remote

## heroku ps

Check how many dynos(container) are running.

## heroku open

查找你heroku 遠端 repo與當前目錄關聯的 Heroku 應用程序的 URL並打開，也可以做類似heroku open /convert 直接確認該route

## heroku ps:scale web=0
Horizontal scaling an application on Heroku is equivalent to changing the number of running dynos.

Scale the number of web dynos to zero

## heroku logs --tail
heroku logs can check the latest log, with --tail, it will check the log lively until stop with Ctrl+C command.

## heroku config

查詢 Heroku 應用的環境變量。這些環境變量通常用於存儲應用程序設定、秘密或任何其他配置資料

heroku config:set ENERGY="20 GeV" 可以直接添加var

## heroku pg

Provides more in-depth information on your app’s Heroku Postgres databases

## heroku pg:psql

Connect to the remote database and see all the rows, and able to do the query.

## heroku open /database

heroku open /database，CLI 將試圖打開瀏覽器至 https://your-app-name.herokuapp.com/database。除非你的應用程序實際上在這個路徑下提供內容，否則這可能不是你想要的結果。

## heroku local --port 5001

heroku local examines your Procfile to determine what command to run.

## heroku run java -version

Heroku will spin up a temporary one-off dyno, execute the java -version command inside that dyno, display the output (Java version information) back to you, and then shut down the one-off dyno.

One-off dynos 在 Heroku 平台上是一種特殊類型的 dyno，用於執行短暫或一次性的任務，而不是長時間運行的 web 或 worker 服務。

## echo $?

在 Unix 和 Linux 系統中，$? 是一個特殊的 shell 變量，它保存了最後執行命令的退出狀態碼。退出狀態碼是一個數字，用來表示命令執行成功與否。

## heroku addons:destroy heroku-postgresql

This action removes your add-on and any data saved in the database.

## heroku apps:destroy

This action permanently deletes your application.