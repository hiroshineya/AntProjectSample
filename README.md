Ant 実行環境サンプル
================

含まれているもの  
  build.xml       <= Ant実行定義設定  
  runAnt.bat      <= Ant実行バッチ  
  
  
JDKのインストールは済んでいるものとします。  
コマンドプロンプトで、javac のみで実行すると、何か実行される状態。  
  
Antのありか  
  http://ant.apache.org/bindownload.cgi  
    Windowsの場合、zip形式のファイルをDLする。  

この例では、JDKを C: 直下の C:\jdk1.6.0_05 にインストールしています。  
以下のようなDir構成となっているはずです。  
C:\jdk1.6.0_05              <= JAVA_HOME  
 ├bin  
 ├db  
 ├demo  
 ├include  
 ├jre  
 └lib  
  
・Ant インストール  
    AntのZipファイルを解凍し、JDKインストールディレクトリにコピーします。  
    すると、以下のDir構成となります。  
    C:\jdk1.6.0_05  
     ├bin  
     ├db  
     ├demo  
     ├include  
     ├jre  
     ├lib  
     └apache-ant-1.7.0     <= ANT_HOME  
        ├bin  
        ├docs  
        ├etc  
        └lib  
  
  
・Antプロジェクト(ここ一式)の設定  
    runAnt.bat の環境変数を設定します。  
    JAVA_HOME の設定  
        JDKのインストールディレクトリを設定  
        上記環境に沿うと、  
            C:\jdk1.6.0_05  
        となります。  
    ANT_HOME の設定  
        Antのインストールディレクトリを設定  
        上記環境に沿うと、  
            C:\jdk1.6.0_05\apache-ant-1.7.0  
        となります。  
  
  
・コンパイル環境の作成  
    コマンドプロンプトで、このDir(runAnt.batが存在するDir)をカレントディレクトリとします。  
    以下のコマンドを実行する。  
  
        runAnt CreateProject  
  
    classes、docs、lib、srcの４つのディレクトリが作成されます。  
    src ディレクトリに、パッケージ構成と同じディレクトリ構成のソースコードをコピーします。  
  

・コンパイル  
    コマンドプロンプトで、このDir(runAnt.batが存在するDir)をカレントディレクトリとします。  
    以下のコマンドを実行する。  
  
        runAnt  
  
    classes ディレクトリにクラスファイルが作成されます。  
  
・runAnt オプション  
    「コンパイル環境の作成」での実行のように、runAntは引数を受け付けます。  
    ・引数無し      ：通常のコンパイル。classesに、クラスファイルが作成される。  
    ・cleanCompile  ：クリーンコンパイル。以前作成したクラスファイルを削除してからコンパイル  
    ・jar           ：クリーンコンパイル＋jarファイル作成まで行う。  
    ・clean         ：以前作成したクラスファイルを削除  
    ・javadoc       ：JavaDoc作成。docsに出力。  
    ・CreateProject ：プロジェクトのディレクトリ構成を作成。  
  
  
以上  


