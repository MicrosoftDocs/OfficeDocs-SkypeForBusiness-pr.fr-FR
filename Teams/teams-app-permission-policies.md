---
title: Gérer les stratégies d’autorisation d’application dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez les stratégies d’autorisation application dans Microsoft Teams et comment les utiliser pour contrôler les applications sont disponibles pour les utilisateurs de votre organisation.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: 49200d597811d87ce27d94d9bb19577def6355c1
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520223"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Gérer les stratégies d’autorisation d’application dans Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon.md)]

En tant qu’administrateur, vous pouvez utiliser des stratégies d’autorisation application pour contrôler les applications sont accessibles aux utilisateurs de Microsoft Teams dans votre organisation. Vous pouvez autoriser ou bloquer toutes les applications ou des applications spécifiques publiées par Microsoft, les fournisseurs tiers et votre organisation. Lorsque vous bloquez une application, les utilisateurs ne peuvent pas l’installer à partir de l’app store équipes.

Gérer les stratégies d’autorisation app dans le centre d’administration Microsoft Teams. Vous pouvez appliquer des paramètres à l’échelle de l’organisation, utilisez la stratégie globale (valeur par défaut à l’échelle de l’organisation) et créer et attribuer des stratégies personnalisées à des utilisateurs individuels ou des utilisateurs dans un groupe.  

![Capture d’écran de la stratégie d’autorisation application](media/app-permission-policies.png)

> [!NOTE]
> Les utilisateurs dans votre organisation reçoivent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Les paramètres d’application à l’échelle de l’organisation substituent la stratégie globale et toutes les stratégies personnalisées que vous créez et attribuer aux utilisateurs.

Par exemple, par exemple, que vous souhaitez bloquer toutes les applications tierces et autoriser des applications spécifiques de Microsoft pour l’équipe des ressources humaines dans votre organisation. Vous souhaiteriez créer une stratégie personnalisée appelée stratégie d’autorisation application RH, bloquer et autoriser les applications que vous souhaitez définir, puis attribuez-le aux utilisateurs de l’équipe des ressources humaines.

## <a name="manage-org-wide-app-settings"></a>Gérer les paramètres d’application à l’échelle de l’organisation

Utiliser les paramètres d’application à l’échelle de l’organisation pour contrôler les applications qui sont disponibles dans votre organisation. Les paramètres d’application à l’échelle de l’organisation déterminent le comportement pour tous les utilisateurs et remplacent les autres stratégies d’autorisation application attribuées aux utilisateurs. Les paramètres d’application à l’échelle de l’organisation prennent effet immédiatement et vous pouvez les utiliser pour contrôler les applications malveillantes ou problématiques.

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies d’autorisation**.
2. Sélectionnez les **paramètres de l’organisation**. Vous pouvez ensuite configurer les paramètres que vous souhaitez dans le panneau de configuration. 
![Capture d’écran des paramètres d’application à l’échelle de l’organisation](media/app-permission-policies-org-wide-settings.png)
3. Sous **applications de tiers**, désactiver ou activer sur ces paramètres pour contrôler l’accès aux applications de tiers :

    - **Autoriser les applications tierces dans les équipes**: cette option détermine si les utilisateurs peuvent utiliser les applications tierces.
    - **Autoriser les nouvelles applications de tiers publiées dans le magasin par défaut**: cette détermine si les nouvelles applications de tiers qui sont publiées sur l’application des équipes stockent sont automatiquement disponibles dans les équipes. Vous pouvez uniquement définir cette option si vous autorisez les applications tierces.

4. Sous **applications personnalisées**, activer ou désactiver sur **Autoriser l’interaction avec les applications personnalisées**. Ce paramètre contrôle si les utilisateurs peuvent interagir avec les applications personnalisées (sideloaded). N’oubliez pas que cela est différent de ce qui permet aux utilisateurs de *Télécharger* des applications personnalisées.
5. Sous **applications bloqué**, rechercher et ajouter les applications que vous souhaitez bloquer au sein de votre organisation. Vous pouvez choisir les applications à partir du catalogue d’applications client ou l’app store équipes.
6. Cliquez sur **Enregistrer** pour les paramètres d’application à l’échelle de l’organisation prennent effet.

## <a name="create-a-custom-app-permission-policy"></a>Créer une stratégie d’autorisation application personnalisée

Si vous souhaitez contrôler les applications qui sont disponibles pour différents groupes d’utilisateurs dans votre organisation, créer et affecter une ou plusieurs stratégies d’autorisation d’application personnalisée. Vous pouvez créer et affecter des stratégies personnalisées distinctes selon que les applications sont publiées par Microsoft, les fournisseurs tiers ou votre organisation. Il est important de savoir qu’après avoir créé une stratégie personnalisée, vous ne pouvez pas modifier si les applications tierces sont désactivées dans les paramètres de l’organisation. 

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies d’autorisation**.
2. Sélectionnez **nouvelle stratégie**.
    ![Capture d’écran de la nouvelle stratégie d’autorisation application](media/app-permission-policies-new-policy.png)
3. Entrez un nom descriptif pour la stratégie.
4. Sous **applications de Microsoft**, **les applications tierces**et les **applications de client**, sélectionnez une des options suivantes :

    - **Autoriser toutes les applications**
    - **Autoriser des applications spécifiques et de bloquer tous les autres**
    - **Bloquer des applications spécifiques et autoriser toutes les autres**
    - **Bloquer toutes les applications**

5. Si vous avez sélectionné **verte d’autres personnes et des applications spécifiques**, ajoutez les applications que vous souhaitez autoriser :

    1. Sélectionnez **Autoriser les applications**.
    1. Recherche pour les applications que vous souhaitez autoriser, puis cliquez sur **Ajouter**. Les résultats de recherche sont filtrés à l’éditeur de l’application (**applications Microsoft**, **les applications tierces**ou **applications client**).
    1. Lorsque vous avez choisi la liste des applications, cliquez sur **Autoriser**.

6. De même, si vous avez sélectionné **bloquer des applications spécifiques et autoriser toutes les autres**, rechercher et ajouter les applications que vous souhaitez bloquer.
7. Cliquez sur **Enregistrer**.

## <a name="edit-an-app-permission-policy"></a>Modifier une stratégie d’autorisation app

Vous pouvez utiliser le centre d’administration Microsoft Teams pour modifier une stratégie, notamment la stratégie globale de (valeur par défaut à l’échelle de l’organisation) et les stratégies personnalisées que vous créez. 

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies d’autorisation**.
2. Sélectionnez la stratégie que vous souhaitez modifier.
3. À partir de là, apportez les modifications souhaitées. Vous pouvez gérer les paramètres de l’éditeur de l’application et ajouter ou supprimer des applications basées sur le paramètre Autoriser/bloquer.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Affecter une stratégie d’autorisation des applications personnalisées aux utilisateurs

Vous pouvez utiliser le centre d’administration Microsoft Teams pour attribuer une stratégie personnalisée à des utilisateurs individuels ou le Skype pour le module PowerShell Business pour attribuer une stratégie personnalisée à plusieurs utilisateurs, tels que tous les utilisateurs dans un groupe de sécurité ou un groupe de distribution.

> [!IMPORTANT]
> Nous recommandons l’utilisation de PowerShell uniquement pour affecter des stratégies aux utilisateurs. Utiliser le centre d’administration Microsoft Teams pour créer, modifier et gérer des stratégies.

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a>Affecter une stratégie d’autorisation des applications personnalisées à des utilisateurs individuels

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies attribuées**, cliquez **sur Modifier**.
3. Sous **stratégie d’autorisation application**, sélectionnez la stratégie d’autorisation application que vous voulez attribuer, puis cliquez sur **Enregistrer**.

    ![policy.png du attribuer autorisation d’application du programme d’installation](media/app-permission-policies-assign-policy.png)

Vous pouvez également assigner une stratégie d’autorisation application comme suit pour un ou plusieurs utilisateurs :

1. Accédez au **Centre d’administration de Microsoft équipes** > **applications équipes** > **stratégies d’autorisation**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par un nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Affecter une stratégie d’autorisation des applications personnalisées aux utilisateurs d’un groupe

Vous souhaiterez peut-être attribuer une stratégie d’autorisation application personnalisée à plusieurs utilisateurs que vous avez déjà identifié. Par exemple, vous souhaiterez peut-être attribuer une stratégie à tous les utilisateurs dans un groupe de sécurité. Pour cela, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business. Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

Dans cet exemple, nous affecter une stratégie d’autorisation application personnalisée appelée stratégie d’autorisation application RH à tous les utilisateurs dans le groupe projet de Contoso Pharmaceuticals RH.  

> [!NOTE]
> Assurez-vous que votre première connexion à Azure Active Directory PowerShell pour le module graphique et Skype pour le module PowerShell Business en suivant les étapes de [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenir le GroupObjectId du groupe particulier.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtenir les membres du groupe spécifié.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Affecter tous les utilisateurs dans le groupe à une stratégie d’autorisation particulier d’application. Dans cet exemple, il est la stratégie d’autorisation application RH.
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.

## <a name="faq"></a>FAQ

### <a name="working-with-app-permission-policies"></a>Utilisation de stratégies d’autorisation des applications

#### <a name="can-i-control-line-of-business-lob-apps"></a>Puis-je contrôler ligne des applications métier (LOB) ?

Oui, vous pouvez utiliser des stratégies d’autorisation application pour contrôler le déploiement et la distribution des applications (LOB) personnalisées.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Comment les stratégies d’autorisation application par rapport aux applications épinglées et stratégies du programme d’installation des applications ?

Vous pouvez utiliser les stratégies du programme d’installation des applications avec des stratégies d’autorisation des applications. Applications préalable épinglées sont sélectionnées à partir de l’ensemble des applications activées pour un utilisateur. En outre, si l’utilisateur a une stratégie d’autorisation application bloque une application dans sa stratégie de configuration d’application, cette application n’apparaît pas dans les équipes.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a>Puis-je utiliser des stratégies d’autorisation application pour restreindre le téléchargement des applications personnalisées (également appelé chargement de version test) ?

Pour plus d’informations sur la façon de restreindre le téléchargement des applications personnalisées, voir [Gérer les stratégies d’application personnalisée et les paramètres dans les équipes](teams-custom-app-policies-and-settings.md).

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Combien de temps faut-il pour que les modifications de stratégie prennent effet ?

Une fois que vous modifiez la stratégie globale ou affectez une stratégie aux utilisateurs, il peut prendre jusqu'à 24 heures pour que les modifications prennent effet. Les paramètres d’application à l’échelle de l’organisation prennent effet immédiatement.

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Blocage d’une application applicable aux clients mobiles équipes ?

Oui, lorsque vous bloquez une application, cette application est bloquée pour tous les clients d’équipes.  

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Ce qui un utilisateur confronté lorsqu’une application est bloquée ?

Les utilisateurs ne peuvent pas interagir avec une application bloquée ou ses fonctionnalités, ces robots, des onglets et des extensions de messagerie. Dans un contexte partagé, telles que l’équipe ou un groupe de la conversation, robots peuvent encore envoyer des messages à tous les participants de ce contexte. Les équipes indique à l’utilisateur lorsqu’une application est bloquée. 

Par exemple, lorsqu’une application est bloquée, les utilisateurs ne peut pas effectuer une des options suivantes :

- Ajouter l’application personnellement ou à une conversation ou de l’équipe
- Envoyer des messages pour les robots de l’application
- Effectuer des actions de bouton Envoyer des informations sur l’application, tels que les messages exploitables  
- Afficher l’onglet de l’application
- Configurer les connecteurs pour recevoir des notifications
- Utilisez l’extension de messagerie de l’application

 ## <a name="related-topics"></a>Rubriques connexes
- [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
- [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
