---
title: Gérer les stratégies d’autorisation d’application dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez-en davantage sur les stratégies d’autorisation d’applications dans Microsoft teams et la manière de les utiliser pour contrôler les applications disponibles pour les utilisateurs de votre organisation.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ed568fe0354f009656e3837d36701a94f0765340
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837404"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gérer les stratégies d’autorisation d’application dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler les applications disponibles pour les utilisateurs de Microsoft teams au sein de votre organisation. Vous pouvez autoriser ou bloquer toutes les applications ou applications spécifiques publiées par Microsoft, des tiers et votre organisation. Lorsque vous bloquez une application, les utilisateurs ne peuvent pas l’installer à partir de l’App Store Teams.

Vous gérez les stratégies d’autorisation d’application dans le centre d’administration Microsoft Teams. Vous pouvez appliquer les paramètres à l’échelle de l’organisation, utiliser la stratégie globale par défaut de l’organisation, puis créer et attribuer des stratégies personnalisées à des utilisateurs individuels ou à des utilisateurs au sein d’un groupe.  

![Capture d’écran de la stratégie d’autorisation d’application](media/app-permission-policies.png)

> [!NOTE]
> Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée. Les paramètres d’application à l’échelle de l’organisation remplacent la stratégie globale et les stratégies personnalisées que vous créez et attribuez aux utilisateurs.

Si votre organisation est déjà en équipe, les paramètres d’application que vous avez configurés dans les paramètres à l' **échelle du client** du centre d’administration 365 Microsoft sont reflétés dans les paramètres de l’application à l’échelle de l’organisation. S’il s’agit de nouvelles équipes et de la mise en route, par défaut, toutes les applications sont autorisées dans la stratégie globale. Cela inclut les applications publiées par Microsoft, par des tiers et par votre organisation.

Par exemple, supposons que vous souhaitiez bloquer toutes les applications tierces et autoriser des applications spécifiques de Microsoft à l’équipe RH de votre organisation. Vous pouvez créer une stratégie personnalisée nommée Stratégie d’autorisations de l’application DRH, définir le blocage et autoriser les applications souhaitées, puis les affecter aux utilisateurs de l’équipe RH.

> [!NOTE]
> Si vous avez déployé des équipes dans un environnement Microsoft 365 Government-GCC, voir [stratégies d’autorisation d’application pour GCC](#app-permission-policies-for-gcc) pour en savoir plus sur les paramètres d’application tiers propres à gcc.

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’Organisation

Utilisez les paramètres de l’application à l’échelle de l’Organisation pour contrôler les applications disponibles dans l’ensemble de votre organisation. Les paramètres de l’application à l’échelle de l’organisation régissent le comportement de tous les utilisateurs et remplacent toutes les autres stratégies d’autorisation d’application attribuées aux utilisateurs. Vous pouvez les utiliser pour contrôler les applications malveillantes ou problématiques.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Sélectionnez **paramètres à l’échelle de l’organisation**. Vous pouvez alors configurer les paramètres de votre choix dans le panneau. 
    ![Capture d’écran des paramètres d’application à l’échelle de l’Organisation](media/app-permission-policies-org-wide-settings.png)
3. Sous **applications tierces**, désactivez ou activez ces paramètres pour contrôler l’accès aux applications tierces :

    - **Autoriser une tierce partie dans teams**: ce contrôle si les utilisateurs peuvent utiliser des applications tierces.
    - **Autorisez toutes les nouvelles applications tierces publiées dans le Windows Store par défaut**: ce contrôle si les nouvelles applications tierces publiées dans le Windows Store sont automatiquement disponibles dans Teams. Vous ne pouvez définir cette option que si vous autorisez des applications tierces.

4. Sous **applications personnalisées**, désactivez ou activez l’option **autoriser les interactions avec les applications personnalisées**. Ce paramètre détermine si les utilisateurs peuvent interagir avec les applications personnalisées (chargée). Gardez à l’esprit qu’il est différent de l’autorisation des utilisateurs à *Télécharger* des applications personnalisées.
5. Sous **applications bloquées**, recherchez et ajoutez les applications que vous souhaitez bloquer au sein de votre organisation. Vous pouvez sélectionner des applications à partir du catalogue d’applications du client ou du magasin d’applications Teams.
6. Cliquez sur **Enregistrer** pour appliquer les paramètres de l’application à l’échelle de l’organisation.

## <a name="create-a-custom-app-permission-policy"></a>Créer une stratégie d’autorisations d’application personnalisée

Si vous voulez contrôler les applications qui sont disponibles pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies d’autorisation d’application personnalisées. Vous pouvez créer et attribuer des stratégies personnalisées distinctes selon que les applications sont publiées par Microsoft, par des tiers ou par votre organisation. Il est important de savoir qu’une fois que vous avez créé une stratégie personnalisée, vous ne pouvez pas la modifier si des applications tierces sont désactivées dans les paramètres à l’échelle de l’organisation. 

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Cliquez sur **Ajouter**.
    ![Capture d’écran de la nouvelle stratégie d’autorisation d’application](media/app-permission-policies-new-policy.png)
3. Entrez le nom et la description de la stratégie.
4. Sous **applications Microsoft**, **applications**tierces et **applications clientes**, sélectionnez l’une des options suivantes :

    - **Autoriser toutes les applications**
    - **Autoriser des applications spécifiques et bloquer toutes les autres**
    - **Bloquer des applications spécifiques et autoriser tous les autres**
    - **Bloquer toutes les applications**

5. Si vous avez sélectionné **autoriser des applications spécifiques et bloquer d’autres personnes**, ajoutez les applications que vous souhaitez autoriser :

    1. Sélectionnez **autoriser les applications**.
    1. Recherchez les applications que vous souhaitez autoriser, puis cliquez sur **Ajouter**. Les résultats de la recherche sont filtrés sur l’éditeur de l’application (**applications Microsoft**, **applications tierces**ou **applications clientes**).
    1. Lorsque vous avez choisi la liste des applications, cliquez sur **autoriser**.

6. De même, si vous avez sélectionné **bloquer des applications spécifiques et autorisez tous les autres**, recherchez et ajoutez les applications que vous souhaitez bloquer.
7. Cliquez sur **Enregistrer**.

## <a name="edit-an-app-permission-policy"></a>Modifier une stratégie d’autorisation d’application

Vous pouvez utiliser le centre d’administration de Microsoft teams pour modifier une stratégie, y compris la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. À partir de cet emplacement, apportez les modifications souhaitées. Vous pouvez gérer les paramètres en fonction de l’éditeur de l’application et ajouter et supprimer des applications en fonction du paramètre autoriser/bloquer.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Attribuer une stratégie d’autorisation d’application personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à un ou plusieurs utilisateurs ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, par exemple tous les utilisateurs d’un groupe de sécurité ou d’un groupe de distribution.

### <a name="assign-a-custom-app-permission-policy-to-a-user"></a>Attribuer une stratégie d’autorisation d’application personnalisée à un utilisateur

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de l’utilisateur, puis sur **modifier les paramètres**.
3. Sous **stratégie d’autorisation d’application**, sélectionnez la stratégie d’autorisation d’application que vous voulez attribuer, puis cliquez sur **appliquer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Assigner une stratégie d’autorisation d’application personnalisée aux utilisateurs d’un groupe

Il est possible que vous souhaitiez affecter une stratégie d’autorisation d’application personnalisée à plusieurs utilisateurs déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité. Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).

Dans cet exemple, nous affectons une stratégie d’autorisations d’application personnalisée appelée stratégie d’autorisation d’application pour tous les utilisateurs du groupe de projets RH de contoso Pharmaceuticals.  

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtenez les membres du groupe spécifié.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie d’autorisation d’application particulière. Dans cet exemple, il s’agit de la stratégie d’autorisation d’application HR.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="app-permission-policies-for-gcc"></a>Stratégies d’autorisation d’application pour GCC

Dans Microsoft 365 Government-déploiement de Microsoft Teams, il est important de connaître les paramètres d’application tiers, qui sont propres à la configuration de Skype.

Dans GCC, toutes les applications tierces sont bloquées par défaut. Par ailleurs, vous verrez la note suivante concernant la gestion des applications tierces sur la page stratégies d’autorisation d’application dans le centre d’administration Microsoft Teams.

![Capture d’écran de la stratégie d’autorisation d’application dans GCC](media/app-permission-policies-gcc.png)

Pour autoriser une application tierce à un utilisateur ou à un groupe d’utilisateurs de votre organisation, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à > **stratégies d’autorisations**des **applications teams**.
2. Vérifiez que l’application tierce que vous souhaitez autoriser pour un ensemble d’utilisateurs est bloquée au niveau de l’organisation. Pour cela, cliquez sur **paramètres à l’échelle**de l’organisation, puis sous **applications bloquées**, vérifiez que l’application est répertoriée.
3. Modifiez la stratégie globale pour bloquer l’application tierce. Pour ce faire :
    1. Dans la page stratégies d’autorisation d’application, cliquez sur **global (par défaut de l’organisation)**, puis cliquez sur **modifier**.
    2. Sous **applications tierces**, sélectionnez **bloquer des applications spécifiques**, ajoutez l’application, puis cliquez sur **Enregistrer**.

    > [!NOTE]
    > Il est important de procéder de la sorte avant de passer à l’étape suivante pour autoriser l’application au niveau de l’organisation. En effet, si l’application tierce n’est pas bloquée dans la stratégie globale, tous les utilisateurs auxquels la stratégie globale s’appliquent pourront accéder à l’application tierce lorsque vous l’autoriserez au niveau de l’organisation.

4. Autorisez l’application tierce au niveau de l’organisation. Pour cela, cliquez sur **paramètres à l’échelle**de l’organisation, sous **applications bloquées**, supprimez l’application dans la liste, puis cliquez sur **Enregistrer**.
5. [Créez une stratégie d’autorisations d’application personnalisée](#create-a-custom-app-permission-policy) pour autoriser l’application, puis [affectez la stratégie](#assign-a-custom-app-permission-policy-to-users) aux utilisateurs de votre choix.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>Utilisation des stratégies d’autorisation d’application

#### <a name="can-i-control-line-of-business-lob-apps"></a>Puis-je contrôler les applications métier ?
Oui, vous pouvez utiliser des stratégies d’autorisation d’application pour contrôler le lancement et la distribution d’applications personnalisées (LOB). Vous pouvez créer une stratégie personnalisée ou modifier la stratégie globale pour autoriser ou bloquer des applications personnalisées en fonction des besoins de votre organisation.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Quelle est la relation entre les stratégies d’autorisation d’application et les stratégies d’application et de configuration d’applications ?

Vous pouvez utiliser les stratégies de configuration d’application conjointement avec des stratégies d’autorisation d’application. Les applications pré-épinglées sont sélectionnées à partir de l’ensemble des applications activées pour un utilisateur. De plus, si un utilisateur dispose d’une stratégie d’autorisations d’application qui bloque une application dans sa stratégie de configuration de l’application, celle-ci n’apparaîtra pas dans Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>Est-il possible d’utiliser des stratégies d’autorisation d’application pour limiter le téléchargement d’applications personnalisées (également appelées chargement indépendant) ?

Utilisez les paramètres à l’échelle de l’organisation dans les stratégies d’autorisation d’application pour limiter le téléchargement d’applications personnalisées pour votre organisation.  

Pour empêcher des utilisateurs spécifiques de télécharger des applications personnalisées, utilisez des stratégies d’application personnalisées. Pour plus d’informations, consultez [gérer les stratégies et les paramètres d’application personnalisés dans teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Le blocage d’une application s’applique-t-elle aux clients mobiles teams ?

Oui, lorsque vous bloquez une application, celle-ci est bloquée sur tous les clients Teams.  

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Que se passe-t-il lorsqu’une application est bloquée ?

Les utilisateurs ne peuvent pas interagir avec une application bloquée ou ses fonctionnalités, telles que les robots, les onglets et les extensions de messagerie. Dans un contexte partagé, tel qu’une discussion d’équipe ou de groupe, les robots peuvent tout de même envoyer des messages à tous les participants de ce contexte. Teams indique à l’utilisateur quand une application est bloquée.

Par exemple, quand une application est bloquée, les utilisateurs ne peuvent pas effectuer les opérations suivantes :

- Ajouter l’application personnellement ou à une conversation ou une équipe
- Envoyer des messages au bot de l’application
- Effectuer des actions de bouton qui renvoient des informations à l’application, telles que des messages actionnables  
- Afficher l’onglet de l’application
- Configurer des connecteurs pour recevoir des notifications
- Utiliser l’extension de messagerie de l’application

Le portail hérité autorisait le contrôle des applications au niveau de l’organisation, ce qui signifie qu’une application est bloquée pour tous les utilisateurs au sein de l’organisation. Le paramètre de l’application à l’échelle de l’organisation dans les stratégies d’autorisation des applications fonctionne exactement de la même manière.

Pour les stratégies d’autorisation d’application attribuées à des utilisateurs spécifiques, si une application dotée d’une fonctionnalité de robot ou de connecteur a été autorisée et bloquée et si l’application est alors autorisée uniquement pour certains utilisateurs dans un contexte partagé, les membres d’une conversation de groupe ou d’un canal ne disposant pas de l’autorisation sur cette application  peut afficher l’historique des messages et les messages publiés par le robot ou le connecteur, mais ne peut pas interagir avec celui-ci.

 ## <a name="related-topics"></a>Rubriques connexes
- [Paramètres d’administration pour les applications dans Microsoft Teams](admin-settings.md)
