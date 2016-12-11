# escape=`
FROM microsoft/windowsservercore

RUN powershell -Command `
    (New-Object System.Net.WebClient).DownloadFile('http://javadl.oracle.com/webapps/download/AutoDL?BundleId=210185', 'C:\jreinstaller.exe') ; `
    Start-Process -filepath C:\jreinstaller.exe -passthru -wait -argumentlist "/s,INSTALLDIR=c:\Java\jre" ; `
    del C:\jreinstaller.exe

ENV JAVA_HOME c:\\Java\\jre

RUN setx PATH %PATH%;%JAVA_HOME%\bin

CMD [ "java.exe" ]