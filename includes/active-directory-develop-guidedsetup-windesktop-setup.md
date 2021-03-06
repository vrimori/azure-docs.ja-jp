---
title: インクルード ファイル
description: インクルード ファイル
services: active-directory
documentationcenter: dev-center-name
author: andretms
manager: mtillman
editor: ''
ms.assetid: 820acdb7-d316-4c3b-8de9-79df48ba3b06
ms.service: active-directory
ms.devlang: na
ms.topic: include
ms.tgt_pltfrm: na
ms.workload: identity
ms.date: 04/19/2018
ms.author: andret
ms.custom: include file
ms.openlocfilehash: 5e933406b266b8371019abf0f62365184d8900b3
ms.sourcegitcommit: c851842d113a7078c378d78d94fea8ff5948c337
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2018
ms.locfileid: "36205246"
---
## <a name="set-up-your-project"></a>プロジェクトの設定

このセクションでは、Windows デスクトップ .NET アプリケーション (XAML) に *"Microsoft でサインイン"* を統合して、トークンを必要とする Web API でクエリを実行できるようにする方法を示すために、新しいプロジェクトを作成します。

このガイドで作成したアプリケーションには、グラフを呼び出すボタン、結果を画面に表示する領域、およびサインアウト ボタンが表示されます。

> [!NOTE]
> 代わりにこのサンプルの Visual Studio プロジェクトをダウンロードすることもできます。 [プロジェクトをダウンロード](https://github.com/Azure-Samples/active-directory-dotnet-desktop-msgraph-v2/archive/master.zip)したら、[構成手順](#register-your-application)に進んでサンプル コードを構成してから実行してください。
>

アプリケーションを作成するには、次の手順を実行します。
1. Visual Studio で、**[ファイル]** > **[新規]** > **[プロジェクト]** の順に選択します。
2. **[テンプレート]** で **[Visual C#]** を選択します。
3. 使用している Visual Studio のバージョンに応じて、**[WPF アプリ]** または **[WPF アプリケーション]** を選択します。

## <a name="add-msal-to-your-project"></a>プロジェクトに MSAL を追加する
1. Visual Studio で、**[ツール]** > **[NuGet パッケージ マネージャー]**> **[パッケージ マネージャー コンソール]** の順に選択します。
2. [パッケージ マネージャー コンソール] ウィンドウで、次の Azure PowerShell コマンドを貼り付けます。

    ```powershell
    Install-Package Microsoft.Identity.Client -Pre
    ```

    > [!NOTE] 
    > このコマンドを実行すると、Microsoft Authentication Library がインストールされます。 MSAL は、Azure Active Directory v2 で保護される API へのアクセスで使用するユーザー トークンの取得、キャッシュ、更新を処理します。
    >

## <a name="add-the-code-to-initialize-msal"></a>MSAL を初期化するコードの追加
この手順では、トークンの処理など MSAL ライブラリとのやり取りを処理するクラスを作成します。

1. *App.xaml.cs* ファイルを開き、クラスに MSAL の参照を追加します。

    ```csharp
    using Microsoft.Identity.Client;
    ```
<!-- Workaround for Docs conversion bug -->

2. App クラスを以下のように更新します。

    ```csharp
    public partial class App : Application
    {
        //Below is the clientId of your app registration. 
        //You have to replace the below with the Application Id for your app registration
        private static string ClientId = "your_client_id_here";

        public static PublicClientApplication PublicClientApp = new PublicClientApplication(ClientId);

    }
    ```

## <a name="create-the-application-ui"></a>アプリケーション UI を作成する

このセクションでは、アプリケーションで、Microsoft Graph のような保護されたバックエンド サーバーに対してクエリを実行する方法を示します。 

*MainWindow.xaml* ファイルは、プロジェクト テンプレートの一部として自動的に作成されます。 このファイルを開き、アプリケーションの *\<Grid>* ノードを次のコードに置き換えます。

```xml
<Grid>
    <StackPanel Background="Azure">
        <StackPanel Orientation="Horizontal" HorizontalAlignment="Right">
            <Button x:Name="CallGraphButton" Content="Call Microsoft Graph API" HorizontalAlignment="Right" Padding="5" Click="CallGraphButton_Click" Margin="5" FontFamily="Segoe Ui"/>
            <Button x:Name="SignOutButton" Content="Sign-Out" HorizontalAlignment="Right" Padding="5" Click="SignOutButton_Click" Margin="5" Visibility="Collapsed" FontFamily="Segoe Ui"/>
        </StackPanel>
        <Label Content="API Call Results" Margin="0,0,0,-5" FontFamily="Segoe Ui" />
        <TextBox x:Name="ResultText" TextWrapping="Wrap" MinHeight="120" Margin="5" FontFamily="Segoe Ui"/>
        <Label Content="Token Info" Margin="0,0,0,-5" FontFamily="Segoe Ui" />
        <TextBox x:Name="TokenInfoText" TextWrapping="Wrap" MinHeight="70" Margin="5" FontFamily="Segoe Ui"/>
    </StackPanel>
</Grid>
```

