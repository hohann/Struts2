# 構建 Struts 2 的工作環境

### 1.JDK

首先安裝並配置JDK,至官網下載（本範例是採用JDK 8 +MAC ）：   
https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/Mac%20JDK.png)



## 2.Web 服務器

Web 服務器包括Tomcat,Resin,WebSphere,JRun,WebLogic等，本範例採用的是Tomcat 8。
登入Apache 軟體基金會的官網 https://tomcat.apache.org/download-80.cgi ，下載Tomcat 8，在Binary Distributions 的Core中選擇zip即可。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/Tomcat8.png)

將下載的apache-tomcat-8.5.69.zip 解壓後檔案名稱改為Tomcat，並將檔案移到磁盤的某個分區中，比如下圖所示的目錄結構：
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/003.png)

測試Tomcat

執行Tomcat根目錄中bin文件夾中的startup.bat來啟動Tomcat服務器，測試步驟如下：（以我的為例,檔案放在  /Users/weather/Library  路徑低下）
1.  打開terminal 輸入 cd /Users/weather/Library/Tomcat/bin/    (根據自己的路徑改，cd到Tomcat的bin檔案)
2.  chmod u+x *.sh
3.   ./startup.sh
4. 在網址輸入   http://localhost:8080/   （有一隻貓出現就算成功了,如下圖所示）
5. ./shutdown.sh           //關閉tomcat
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/004.png)

## 3.Struts 2 的下載與安裝

至官網下載：https://struts.apache.org/download.cgi （本範例採用 Struts 2.5.26版本），如下圖所示：

建議安裝完整版（Full Distribution）
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/005.png)
將下載到的zip文件解壓縮，解壓縮後的目錄結構如下圖：
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/006.png)
(i)apps:包基於Struts2的示例應用。

(ii)docs:包含Struts2 的快速入門，Struts 2 的文檔，以及API文件等內容。

## 4.使用 Eclipse開發Struts 2 的Web 應用

到Eclipse官網下載Eclipse https://www.eclipse.org/downloads/ ，如下圖所示：
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/007.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/008.png)



前面四項都下載完成後，接下來就開始對Eclipse 進行一些必要的配置。

## 5.Tomcat在Eclipse中的配置

(1)啟動Eclipse 接著選擇Preferences 命令，在彈出的對話框中選擇Server - Runtime Environments ,如下圖：
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/009.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/010.png)


(2)單擊Add按鈕後，彈出如下圖所示的New Server Runtime Environment窗口，在此可以配置各種版本的Web服務器。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/011.png)

(3)選擇Apache Tomcat v8.5服務器版本，單擊Next 按鈕，進入下圖所示窗口。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/012.png)
單擊Browse按鈕，選擇Tomcat所在的目錄位置，點擊Finish按鈕即可完成Tomcat配置。

## 6.創建 Web 應用

(1)選擇菜單中的File > New > Project 命令,接著在new Project對話框中選擇Web節點下的Dynamic Web Project 子節點，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/013.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/014.png)
(2)點擊Next按鈕,打開 New Dynamic Web Project 窗口,在Project name 輸入項目名稱,這裡為 HelloWorld。選擇Target runtime 區域中的服務器,如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/015.png)
(3)修改 java build path的路徑, 將其預設的路徑 Remove 掉(我們後面在進行設定)，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/016.png)
(4)將Content directory 改為 WebContent ，並選中Generate web.xml deployment descriptor ,如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/017.png)
(5)點擊Finish按鈕，完成項目HelloWorld的創建,在Eclipse左側將顯示該項目,如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/018-2.png)


## 7.Java Build path 設定
(1)在HelloWorld項目點擊右鍵，接著再單擊Properties，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/019.png)

(2)在Java Build Path 處選擇 Source ,並點擊Add Folder 以新建文件夾，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/020.png)

(3)在Source Folder Selection中選擇src資料夾，若沒有src資料夾，就點擊Create New Folder 創建一個，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/021.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/022.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/023.png)

(4)最後將其Apply 就可在HelloWorld顯目中 看到src資料夾，如此就完成設定了，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/024.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/100.png)

# 讓Tomcat服務器簡單輸出Hello World
(1)在WebContent 底下新增一個jsp檔案，將其命名為Hello.jsp,並在其內容添加HelloWorld,如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/025.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/026.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/027.png)
(2)啟動Tomcat，在HelloWorld項目點擊右鍵 ，選擇Run on Server,接著選擇Tomcat 版本，並將要文件加入Server，如下圖所示。

![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/030.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/031.png)
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/032.png)
(3)最後在瀏覽器輸入http://localhost:8080/HelloWorld/Hello.jsp 變可看到HelloWorld 文字，如下圖所示。
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/033.png)
