---
title: Gérer les stratégies de mise en application dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez-en davantage sur les stratégies de configuration des applications dans Microsoft teams et la manière de les utiliser pour épingler des applications afin de personnaliser les équipes pour les utilisateurs de votre organisation.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 21e56f9b2910180295e996f12c899e153551a8a3
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198627"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gérer les stratégies de mise en application dans Microsoft Teams

> [!NOTE]
> Si vous avez activé le paramètre de stratégie d’autorisation d’application à l’échelle de l’organisation, autorisez les **interactions avec les applications personnalisées**, il est possible que les stratégies de configuration des applications n’apparaissent pas dans le centre d’administration Microsoft Teams. Ce service est actuellement déployé et sera disponible prochainement dans votre organisation.

En tant qu’administrateur, vous pouvez utiliser des stratégies de configuration d’application pour personnaliser Microsoft teams afin de mettre en évidence les applications les plus importantes pour vos utilisateurs. Vous choisissez les applications à épingler et définir leur ordre d’apparition. Les stratégies de configuration des applications vous permettent de faire la promotion des applications requises par les utilisateurs de votre organisation, notamment celles créées par des tiers ou des développeurs de votre organisation. Vous pouvez également utiliser des stratégies de configuration d’application pour gérer l’affichage des fonctionnalités intégrées.

Applications épinglées à la barre de l’application. Il s’agit de la barre située sur le côté du client de bureau teams et au bas des clients mobiles Teams (iOS et Android). 

|Client de bureau teams  |Client mobile teams |
|---------|---------|
|![Capture d’écran illustrant le client de bureau teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Capture d’écran illustrant le client Microsoft teams mobile](media/app-setup-policies-mobile-app-bar.png)      |

Vous gérez les stratégies de configuration des applications dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer des stratégies personnalisées et les affecter à des utilisateurs. Les utilisateurs de votre organisation obtiennent automatiquement la stratégie globale sauf si vous créez et attribuez une stratégie personnalisée.

Vous pouvez modifier les paramètres de la stratégie globale de manière à inclure les applications souhaitées. Si vous voulez personnaliser teams pour différents groupes d’utilisateurs de votre organisation, créez et attribuez une ou plusieurs stratégies personnalisées. Si un utilisateur dispose d’une stratégie personnalisée, cette politique s’applique à l’utilisateur. Si un utilisateur ne reçoit pas de stratégie personnalisée, la politique globale s’applique à l’utilisateur.

![Capture d’écran montrant la page stratégies de configuration des applications](media/app-setup-policies.png)

[!INCLUDE [external-apps-m365-admin-center](includes/external-apps-m365-admin-center.md)]

> [!NOTE]
> Si vous disposez d’équipes pour l’éducation, il est important de savoir que l’application devoirs est épinglée par défaut dans la stratégie globale, même si elle n’est pas répertoriée dans la stratégie globale. Il s’agira de la quatrième application de la liste des applications épinglées sur les clients Teams.

## <a name="create-a-custom-app-setup-policy"></a>Créer une stratégie de configuration d’application personnalisée

Vous pouvez utiliser le centre d’administration de Microsoft teams pour créer une stratégie personnalisée.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies de configuration**des **applications** > teams.
2. Sélectionnez **nouvelle stratégie**.
3. Entrez un nom descriptif pour la stratégie, puis cliquez sur **Ajouter des applications**.
4. Activez ou désactivez l’option autoriser le téléchargement d' **applications personnalisées**, selon que vous voulez permettre aux utilisateurs de télécharger des applications personnalisées dans Teams.
5. Dans le volet **Ajouter des applications épinglées** , recherchez les applications que vous voulez ajouter, puis cliquez sur **Ajouter**. Vous pouvez également filtrer les applications par stratégie d’autorisation d’applications. Lorsque vous avez choisi votre liste d’applications, cliquez sur **Ajouter**.

     ![Capture d’écran montrant le volet ajouter des applications épinglées](media/app-setup-policies-add-apps.png)

6. Organisez les applications dans l’ordre dans lequel vous voulez qu’elles apparaissent dans Teams, puis cliquez sur **Enregistrer**.

    ![Capture d’écran montrant la section applications épinglées](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modifier une stratégie de configuration de l’application

Vous pouvez utiliser le centre d’administration de Microsoft teams pour modifier une stratégie, dont la stratégie globale par défaut de l’organisation et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à**stratégies de configuration**des **applications** > teams.
2. Sélectionnez la stratégie que vous voulez modifier. 
3. À partir de cet emplacement, apportez les modifications souhaitées. Vous pouvez ajouter, supprimer et modifier l’ordre des applications.
4. Cliquez sur **Enregistrer**.

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Assigner une stratégie de configuration d’application personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration de Microsoft teams pour attribuer une stratégie personnalisée à des utilisateurs individuels ou au module PowerShell Skype entreprise pour attribuer une stratégie personnalisée à des groupes d’utilisateurs, tels qu’un groupe de sécurité ou un groupe de distribution.

> [!IMPORTANT]
> Nous vous recommandons d’utiliser PowerShell uniquement pour attribuer des stratégies aux utilisateurs. Utilisez le centre d’administration de Microsoft teams pour créer, modifier et gérer des stratégies.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Assigner une stratégie de configuration d’application personnalisée à des utilisateurs individuels

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies affectées**, choisissez **modifier**.
3. Sous **stratégie de configuration des applications teams**, sélectionnez la stratégie de configuration de l’application que vous voulez attribuer, puis cliquez sur **Enregistrer**.

    ![Capture d’écran montrant le volet modifier les stratégies d’utilisateur](media/app-setup-policies-assign-policy.png)

Vous pouvez également affecter une stratégie de configuration d’application à un ou plusieurs utilisateurs comme suit:

1. Accédez à**stratégies de configuration**des**applications** > du centre > d' **administration Microsoft teams**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Assigner une stratégie de configuration d’application personnalisée aux utilisateurs d’un groupe

Il est possible que vous souhaitiez affecter une stratégie de configuration d’application personnalisée à plusieurs utilisateurs déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité. Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise. Pour plus d’informations sur l’utilisation de PowerShell pour gérer Teams, voir [vue d’ensemble de teams PowerShell](teams-powershell-overview.md).

Dans cet exemple, nous affectons une stratégie d’installation d’application personnalisée appelée stratégie de configuration des applications humaines à tous les utilisateurs du groupe de projets RH de contoso Pharmaceuticals.  

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Obtenez les membres du groupe spécifié.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie de configuration d’application particulière. Dans cet exemple, il s’agit de la stratégie de configuration des applications humaines.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>Utilisation des stratégies de configuration des applications

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Quelles stratégies de configuration des applications intégrées sont incluses dans le centre d’administration de Microsoft teams?

- **Global (par défaut de l’organisation)**: cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation sauf si vous affectez une autre stratégie. Modifiez la stratégie globale pour épingler les applications les plus importantes à vos utilisateurs.
- **FirstLineWorker**: cette stratégie concerne les travailleurs terrain. Vous pouvez l’affecter à des travailleurs terrain au sein de votre organisation. Il est important de savoir que, comme les stratégies personnalisées que vous créez, vous devez affecter la stratégie aux utilisateurs pour que les paramètres soient actifs. Pour plus d’informations, accédez à la section assigner [une stratégie de configuration d’application personnalisée aux utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas retrouver une application dans le volet ajouter des applications épinglées?

Toutes les applications ne peuvent pas être épinglées à teams via une stratégie de configuration d’application. Certaines applications ne prennent pas en charge cette fonctionnalité. Pour rechercher des applications qui peuvent être épinglées, recherchez l’application dans le volet **Ajouter des applications épinglées** . Les onglets qui comportent des onglets statiques et des robots peuvent être épinglés au client de bureau teams et ces applications sont disponibles dans le volet **Ajouter des applications épinglées** .

Gardez à l’esprit que le Windows teams Store répertorie toutes les applications teams alors que le volet **Ajouter des applications épinglées** inclut uniquement les applications qui peuvent être épinglées aux équipes via une stratégie. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Je suis un administrateur d’équipe pour l’éducation. De quoi ai-je besoin en savoir plus sur les stratégies de configuration des applications dans teams pour l’éducation?

L’application appelante n’est pas disponible dans teams pour l’éducation. Lorsque vous créez une stratégie personnalisée de configuration de l’application, l’application d’appel s’affiche dans la liste des applications. Toutefois, l’application n’est pas épinglée aux clients teams et aux équipes destinées aux utilisateurs éducation ne verra pas l’application appels dans Teams.

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>Combien d’applications peuvent être ajoutées à une stratégie?

Au moins deux applications doivent être épinglées aux clients mobiles Teams (iOS et Android). Si une stratégie comporte moins de deux applications, les clients mobiles ne reflètent pas les paramètres de stratégie et continuent à utiliser la configuration existante.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Combien de temps faut-il pour que les modifications soient prises en compte?

Lorsque vous modifiez la stratégie globale ou que vous attribuez une stratégie, un délai de 24 heures peut être nécessaire pour que les modifications soient prises en compte.

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Comment les utilisateurs peuvent-ils voir toutes leurs applications épinglées dans teams?

Pour afficher toutes les applications épinglées pour un utilisateur, les utilisateurs peuvent être amenés à effectuer les opérations suivantes, en fonction du nombre d’applications installées et de la taille de la fenêtre client d’équipes.

|Client de bureau teams |Client mobile teams |
|---------|---------|
|Dans la barre d’application sur le côté d’équipes, cliquez sur **... Autres applications**.| Dans la barre de l’application en bas de teams, balayez vers le haut.|
|![Capture d’écran montrant plus d’applications dans le client de bureau teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Capture d’écran illustrant davantage d’applications dans le client mobile teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Que dois-je savoir sur l’interface mobile de teams?

Les clients mobiles Teams (iOS et Android) ne prennent actuellement pas en charge les applications personnelles à l’aide d’onglets statiques. En fonction des applications définies dans la stratégie, les applications épinglées au client de bureau teams peuvent ne pas apparaître dans les clients mobiles Teams. Les robots personnels apparaîtront toujours dans la conversation sur les clients mobiles.

Les clients mobiles teams pourront voir les applications principales de teams, telles que les activités, les discussions et les équipes, et vous pouvez épingler certaines applications tierces de Microsoft, telles que les Shifts. 

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Les utilisateurs peuvent-ils changer l’ordre des applications épinglées par le biais d’une stratégie?

Pour l’instant, les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur des clients mobiles Teams, mais pas sur le bureau teams ou les clients Web. 

### <a name="custom-teams-apps"></a>Applications personnalisées d’équipes

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mon organisation a créé une application teams personnalisée et l’a publiée, soit dans AppSource, soit dans le catalogue d’applications du client, mais l’icône d’application ne s’affiche pas comme prévu lorsque l’application est épinglée à la barre de l’application dans Teams. Comment résoudre ce problème? 

Veillez à suivre les recommandations relatives au logo avant de procéder à la soumission de l’application. Pour en savoir plus, voir [liste de contrôle pour la soumission du tableau de bord du vendeur](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist). 

 ## <a name="related-topics"></a>Voir aussi
- [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md)
- [Publier une application dans le catalogue d’applications client à partir du client teams](tenant-apps-catalog-teams.md)
