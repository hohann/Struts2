  # Struts 2 的工作環境

## 安裝Struts 2 之前，需要事先安裝JDK和Web服務器

1.JDK

首先安裝並配置JDK,至官網下載（本範例是採用JDK 8 +MAC ）：   
https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html
![Image](https://github.com/hohann/Struts2/blob/main/Struts%E5%85%A5%E9%96%80/Mac%20JDK.png)



2.Web 服務器

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

3.Struts 2 的下載與安裝

至官網下載：https://struts.apache.org/download.cgi （本範例採用 Struts 2.5.26版本），如下圖所示：

