---
title: 'チュートリアル: Azure Active Directory と Lessonly.com の統合 | Microsoft Docs'
description: Azure Active Directory と Lessonly.com の間でシングル サインオンを構成する方法について説明します。
services: active-directory
documentationCenter: na
author: jeevansd
manager: mtillman
ms.assetid: 8c9dc6e6-5d85-4553-8a35-c7137064b928
ms.service: active-directory
ms.component: saas-app-tutorial
ms.workload: identity
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 06/23/2017
ms.author: jeedes
ms.openlocfilehash: 050e8efed38c40d8c7da292c0d6865869a07c9f9
ms.sourcegitcommit: 2ad510772e28f5eddd15ba265746c368356244ae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43121711"
---
# <a name="tutorial-azure-active-directory-integration-with-lessonlycom"></a>チュートリアル: Azure Active Directory と Lessonly.com の統合

このチュートリアルでは、Lessonly.com と Azure Active Directory (Azure AD) を統合する方法について説明します。

Lessonly.com と Azure AD の統合には、次の利点があります。

- Lessonly.com にアクセスする Azure AD ユーザーを制御できます。
- ユーザーが自分の Azure AD アカウントで自動的に Lessonly.com にサインオン (シングル サインオン) できるようにすることが可能です。
- 1 つの中央サイト (Azure Portal) でアカウントを管理できます

SaaS アプリと Azure AD の統合の詳細については、「[Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)」をご覧ください。

## <a name="prerequisites"></a>前提条件

Lessonly.com と Azure AD の統合を構成するには、次のものが必要です。

- Azure AD サブスクリプション
- Lessonly.com のシングル サインオンが有効なサブスクリプション

> [!NOTE]
> このチュートリアルの手順をテストする場合、運用環境を使用しないことをお勧めします。

このチュートリアルの手順をテストするには、次の推奨事項に従ってください。

- 必要な場合を除き、運用環境は使用しないでください。
- Azure AD の評価環境がない場合は、 [こちら](https://azure.microsoft.com/pricing/free-trial/)から 1 か月の評価版を入手できます。

## <a name="scenario-description"></a>シナリオの説明
このチュートリアルでは、テスト環境で Azure AD のシングル サインオンをテストします。 このチュートリアルで説明するシナリオは、主に次の 2 つの要素で構成されています。

1. ギャラリーからの Lessonly.com の追加
1. Azure AD シングル サインオンの構成とテスト

## <a name="adding-lessonlycom-from-the-gallery"></a>ギャラリーからの Lessonly.com の追加
Azure AD への Lessonly.com の統合を構成するには、ギャラリーから管理対象 SaaS アプリの一覧に Lessonly.com を追加する必要があります。

**ギャラリーから Lessonly.com を追加するには、次の手順に従います。**

1. **[Azure Portal](https://portal.azure.com)** の左側のナビゲーション ウィンドウで、**[Azure Active Directory]** アイコンをクリックします。 

    ![Active Directory][1]

1. **[エンタープライズ アプリケーション]** に移動します。 次に、**[すべてのアプリケーション]** に移動します。

    ![[アプリケーション]][2]
    
1. 新しいアプリケーションを追加するには、ダイアログの上部にある **[新しいアプリケーション]** をクリックします。

    ![[アプリケーション]][3]

1. 検索ボックスに、「**Lessonly.com**」と入力します。

    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/tutorial_lessonly.com_search.png)

1. 結果ウィンドウで **[Lessonly.com]** を選択し、**[追加]** をクリックして、アプリケーションを追加します。

    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/tutorial_lessonly.com_addfromgallery.png)

##  <a name="configuring-and-testing-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成とテスト
このセクションでは、"Britta Simon" というテスト ユーザーに基づいて、Lessonly.com で Azure AD のシングル サインオンを構成し、テストします。

シングル サインオンを機能させるには、Azure AD ユーザーに対応する Lessonly.com ユーザーが Azure AD で認識されている必要があります。 言い換えると、Azure AD ユーザーと Lessonly.com の関連ユーザーの間で、リンク関係が確立されている必要があります。

Lessonly.com で、Azure AD の **[ユーザー名]** の値を **[Username]** の値として割り当ててリンク関係を確立します。

Lessonly.com で Azure AD のシングル サインオンを構成してテストするには、次の構成要素を完了する必要があります。

1. **[Configuring Azure AD Single Sign-On](#configuring-azure-ad-single-sign-on)** - ユーザーがこの機能を使用できるようにします。
1. **[Azure AD のテスト ユーザーの作成](#creating-an-azure-ad-test-user)** - Britta Simon で Azure AD のシングル サインオンをテストします。
1. **[Lessonly.com テスト ユーザーの作成](#creating-a-lessonly-test-user)** - Lessonly.com で Britta Simon に対応するユーザーを作成し、Azure AD の Britta Simon にリンクさせます。
1. **[Azure AD テスト ユーザーの割り当て](#assigning-the-azure-ad-test-user)** - Britta Simon が Azure AD のシングル サインオンを使用できるようにします。
1. **[シングル サインオンのテスト](#testing-single-sign-on)** - 構成が機能するかどうかを確認します。

### <a name="configuring-azure-ad-single-sign-on"></a>Azure AD シングル サインオンの構成

このセクションでは、Azure Portal で Azure AD のシングル サインオンを有効にして、Lessonly.com アプリケーションでシングル サインオンを構成します。

**Lessonly.com で Azure AD シングル サインオンを構成するには、次の手順に従います。**

1. Azure Portal の **Lessonly.com** アプリケーション統合ページで、**[シングル サインオン]** をクリックします。

    ![Configure single sign-on][4]

1. **[シングル サインオン]** ダイアログで、**[モード]** として **[SAML ベースのサインオン]** を選択し、シングル サインオンを有効にします。
 
    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly.com_samlbase.png)

1. **[Lessonly.com Domain and URLs]\(Lessonly.com のドメインと URL\)** セクションで、次の手順に従います。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly.com_url.png)

    a. **[サインオン URL]** ボックスに、次の形式で URL を入力します。
    | |
    |--|
    | `https://<companyname>.lessonly.com/signin`|

    >[!NOTE]
    >一般名を参照するときは、この **companyname** を実際の名前に置き換える必要があります。
    
    b. **[識別子]** ボックスに、次の形式で URL を入力します。
    | |
    |--|
    | `https://<companyname>.lessonly.com/auth/saml/metadata`|

    > [!NOTE] 
    > これらは実際の値ではありません。 実際のサインオン URL と識別子でこれらの値を更新してください。 これらの値を取得するには、[Lessonly.com クライアント サポート チーム](mailto:dev@lessonly.com)に問い合わせてください。 

1. **[SAML 署名証明書]** セクションで、**[証明書 (Base64)]** をクリックし、コンピューターに証明書ファイルを保存します。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly.com_certificate.png)

1. Lessonly.com アプリケーションでは、特定の形式の SAML アサーションを使用するため、カスタム属性マッピングを **SAML トークン属性**の構成に追加する必要があります。次のスクリーンショットにその例を示します。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly_06.png)
           
1. **[Single sign-on]\(シングル サインオン\)** ダイアログの **[User Attributes]\(ユーザー属性\)** セクションで、上記の図に示すように SAML トークン属性を構成し、次の手順を実行します。

    | 属性名   | 属性値 |
    | ---------------  | ----------------|
    | urn:oid:2.5.4.42 |User.givenname |
    | urn:oid:2.5.4.4  |User.surname |
    | urn:oid:0.9.2342.19200300.100.1.3 |User.mail |
    | urn:oid:1.3.6.1.4.1.5923.1.1.1.10 |user.objectid |

    a. **[属性の追加]** をクリックして **[属性の追加]** ダイアログを開きます。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_attribute_04.png)

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_attribute_05.png)

    b. **[名前]** ボックスに、その行に対して表示される属性名を入力します。

    c. **[値]** 一覧から、その行に対して表示される値を入力します。
    
    d. **[OK]** をクリックします。     

1. **[保存]** ボタンをクリックします。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_general_400.png)

1. **[Lessonly.com Configuration]\(Lessonly.com 構成\)** セクションで、**[Configure Lessonly.com]\(Lessonly.com を構成する\)** をクリックして、**[サインオンの構成]** ウィンドウを開きます。 **[クイック リファレンス]** セクションから、**サインアウト URL、SAML エンティティ ID、SAML シングル サインオン サービス URL** をコピーします。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly.com_configure.png)

1. **Lessonly.com** 側にシングル サインオンを構成するには、ダウンロードされた**証明書 (Base64)**、**サインアウト URL、SAML エンティティ ID、SAML シングル サインオン サービス URL** を [Lessonly.com サポート チーム](mailto:dev@lessonly.com)に送信する必要があります。

> [!TIP]
> アプリのセットアップ中、[Azure Portal](https://portal.azure.com) 内で上記の手順の簡易版を確認できるようになりました。  **[Active Directory] の [エンタープライズ アプリケーション]** セクションからこのアプリを追加した後、**[シングル サインオン]** タブをクリックし、一番下の **[構成]** セクションから組み込みドキュメントにアクセスするだけです。 組み込みドキュメント機能の詳細については、[Azure AD の組み込みドキュメント]( https://go.microsoft.com/fwlink/?linkid=845985)に関するページを参照してください。

### <a name="creating-an-azure-ad-test-user"></a>Azure AD のテスト ユーザーの作成
このセクションの目的は、Azure Portal で Britta Simon というテスト ユーザーを作成することです。

![Azure AD ユーザーの作成][100]

**Azure AD でテスト ユーザーを作成するには、次の手順に従います。**

1. **Azure Portal** の左側のナビゲーション ウィンドウで、**[Azure Active Directory]** アイコンをクリックします。

    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/create_aaduser_01.png) 

1. **[ユーザーとグループ]** に移動し、**[すべてのユーザー]** をクリックして、ユーザーの一覧を表示します。
    
    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/create_aaduser_02.png) 

1. ダイアログの上部にある **[追加]** をクリックして、**[ユーザー]** ダイアログを開きます。
 
    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/create_aaduser_03.png) 

1. **[ユーザー]** ダイアログ ページで、次の手順を実行します。
 
    ![Azure AD のテスト ユーザーの作成](./media/lessonly-tutorial/create_aaduser_04.png) 

    a. **[名前]** ボックスに「**BrittaSimon**」と入力します。

    b. **[ユーザー名]** ボックスに BrittaSimon の**電子メール アドレス**を入力します。

    c. **[パスワードを表示]** を選択し、**[パスワード]** の値をメモします。

    d. **Create** をクリックしてください。
 
### <a name="creating-a-lessonlycom-test-user"></a>Lessonly.com テスト ユーザーの作成

このセクションの目的は、Lessonly.com で Britta Simon というユーザーを作成することです。 Lessonly.com では、Just-In-Time プロビジョニングがサポートされています。この設定は、既定で有効になっています。

このセクションでは、ユーザー側で必要な操作はありません。 存在しない Lessonly.com ユーザーにアクセスしようとすると、新しいユーザーが自動的に作成されます。

> [!NOTE]
> ユーザーを手動で作成する必要がある場合は、[Lessonly.com のサポート チーム](mailto:dev@lessonly.com)にお問い合わせください。

### <a name="assigning-the-azure-ad-test-user"></a>Azure AD テスト ユーザーの割り当て

このセクションでは、Britta Simon に Lessonly.com へのアクセスを許可することで、このユーザーが Azure シングル サインオンを使用できるようにします。

![ユーザーの割り当て][200] 

**Lessonly.com に Britta Simon を割り当てるには、次の手順を実行します。**

1. Azure Portal でアプリケーション ビューを開き、ディレクトリ ビューに移動します。次に、**[エンタープライズ アプリケーション]** に移動し、**[すべてのアプリケーション]** をクリックします。

    ![ユーザーの割り当て][201] 

1. アプリケーションの一覧で **[Lessonly.com]** を選択します。

    ![Configure single sign-on](./media/lessonly-tutorial/tutorial_lessonly.com_app.png)

1. 左側のメニューで **[ユーザーとグループ]** をクリックします。

    ![ユーザーの割り当て][202] 

1. **[追加]** ボタンをクリックします。 次に、**[割り当ての追加]** ダイアログで **[ユーザーとグループ]** を選択します。

    ![ユーザーの割り当て][203]

1. **[ユーザーとグループ]** ダイアログで、ユーザーの一覧から **[Britta Simon]** を選択します。

1. **[ユーザーとグループ]** ダイアログで **[選択]** をクリックします。

1. **[割り当ての追加]** ダイアログで **[割り当て]** ボタンをクリックします。
    
### <a name="testing-single-sign-on"></a>シングル サインオンのテスト

このセクションの目的は、アクセス パネルを使用して Azure AD のシングル サインオン構成をテストすることです。

アクセス パネルで [Lessonly.com] タイルをクリックすると、自動的に Lessonly.com アプリケーションにサインオンします。

## <a name="additional-resources"></a>その他のリソース

* [SaaS アプリと Azure Active Directory を統合する方法に関するチュートリアルの一覧](tutorial-list.md)
* [Azure Active Directory のアプリケーション アクセスとシングル サインオンとは](../manage-apps/what-is-single-sign-on.md)

<!--Image references-->

[1]: ./media/lessonly-tutorial/tutorial_general_01.png
[2]: ./media/lessonly-tutorial/tutorial_general_02.png
[3]: ./media/lessonly-tutorial/tutorial_general_03.png
[4]: ./media/lessonly-tutorial/tutorial_general_04.png

[100]: ./media/lessonly-tutorial/tutorial_general_100.png

[200]: ./media/lessonly-tutorial/tutorial_general_200.png
[201]: ./media/lessonly-tutorial/tutorial_general_201.png
[202]: ./media/lessonly-tutorial/tutorial_general_202.png
[203]: ./media/lessonly-tutorial/tutorial_general_203.png

