# Windows_VisualStudio-LuaBuild
WindowsのVisualStudioでluaのビルド可能なプロジェクト

## ビルド設定テンプレートメモ
#出力ディレクトリ
Build\_$(PlatformShortName)\$(Configuration)\
#中間ディレクトリ
Temp\_$(PlatformShortName)\$(Configuration)\
#出力ファイル名
$(ProjectName)5.3.3_$(PlatformShortName)

//ライブラリ(LIB,DLL)の場合のみ
lua5.3.3_$(PlatformShortName)

libビルド後イベント
mkdir ..\output\
copy Build\_$(PlatformShortName)\$(Configuration)\lua5.3.3_$(PlatformShortName).dll ..\output\

dllビルド後イベント
mkdir ..\output\
copy Build\_$(PlatformShortName)\$(Configuration)\lua5.3.3_$(PlatformShortName).lib ..\output\

exeビルド後イベント
mkdir ..\output\
copy Build\_$(PlatformShortName)\$(Configuration)\$(ProjectName)5.3.3_$(PlatformShortName).exe ..\output\
