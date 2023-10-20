## pom.xml

pom.xml 是 Maven 中的核心檔案，其中 "pom" 代表 "Project Object Model"。它是一個 XML 檔案，用於描述 Java 專案的資訊和設定。

## Procfile

是一個 Heroku 特定的設定檔，用於告訴 Heroku 如何運行你的應用程序。當你部署一個應用到 Heroku 時，Heroku 需要知道如何正確啟動你的應用程序，特別是在多種語言和框架中。Procfile 是這個目的的解決方案。

在 Procfile 中，你可以定義多種不同的進程類型，但最常見的進程類型是 web。這告訴 Heroku 如何啟動你的 web 伺服器。

java -jar target/java-getting-started-1.0.0-SNAPSHOT.jar：這是啟動應用程序的命令。它告訴 Heroku 使用 Java 執行 JAR 檔（Java Archive）來啟動應用程序。在這種情況下，應用程序已被打包成名為 java-getting-started-1.0.0-SNAPSHOT.jar 的 JAR 檔，並存放在 target 目錄下。


# Commands

## heroku create

When you create an app, a git remote called heroku is also created and associated with your local git repository.

## heroku addons:create heroku-postgresql:mini

Add a addon to the created app

Add-ons are cloud services that provide out-of-the-box additional services for your application, such as logging, monitoring, databases, and more.

## heroku addons

See all the add-ons provisioned

## git push heroku main

Push the main branch of the current repo to the heroku remote

## heroku ps

Check how many dynos(container) are running.

## heroku open
查找你當前目錄關聯的 Heroku 應用程序的 URL並打開