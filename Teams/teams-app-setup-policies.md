---
title: Gérer les stratégies de mise en application dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 2/11/2019
ms.reviewer: larryjin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez les stratégies d’installation des applications dans Microsoft Teams et comment les utiliser pour les applications de code confidentiel pour personnaliser les équipes pour les utilisateurs de votre organisation.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e6ad41dac9021079bffa80284809733c39f3cc9
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205762"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a>Gérer les stratégies de mise en application dans Microsoft Teams

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

En tant qu’administrateur, vous pouvez utiliser des stratégies d’application du programme d’installation pour personnaliser Microsoft Teams pour mettre en surbrillance les applications qui sont importantes pour vos utilisateurs. Vous choisissez applications pour épingler et définir l’ordre dans lequel ils apparaissent. Stratégies d’application du programme d’installation vous permettent de présenter les applications nécessitant des utilisateurs de votre organisation, y compris celles créées par des tiers ou par les développeurs dans votre organisation. Vous pouvez également utiliser des stratégies de paramétrage d’application pour gérer les fonctionnalités intégrées comment s’affichent.

Les applications sont épinglées sur la barre de l’application. Il s’agit de la barre sur le côté du client de bureau équipes et en bas des clients mobiles équipes (iOS et Android). 

|Client de bureau d’équipes  |Client mobile d’équipes |
|---------|---------|
|![App-Setup-Policies-Desktop-App-bar.png](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-mobile-App-bar.png](media/app-setup-policies-mobile-app-bar.png)      |

Gérer les stratégies d’installation des applications dans le centre d’administration Microsoft Teams. Vous pouvez utiliser la stratégie globale (valeur par défaut à l’échelle de l’organisation) ou créer des stratégies personnalisées et les attribuer aux utilisateurs. Les utilisateurs dans votre organisation reçoivent automatiquement la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée.

Vous pouvez modifier les paramètres de la stratégie globale pour inclure les applications que vous souhaitez. Si vous souhaitez personnaliser les équipes pour différents groupes d’utilisateurs de votre organisation, créer et affecter une ou plusieurs stratégies personnalisées.

![le programme d’installation-application-policies.png](media/app-setup-policies.png)

> [!NOTE]
> Si un utilisateur est affecté à une stratégie personnalisée, cette stratégie s’applique à l’utilisateur. Si un utilisateur n’est pas attribué une stratégie personnalisée, la stratégie globale s’applique à l’utilisateur.

## <a name="create-a-custom-app-setup-policy"></a>Créer une stratégie du programme d’installation d’application personnalisée

Vous pouvez utiliser le centre d’administration de Microsoft Teams ou de Windows PowerShell pour créer une stratégie personnalisée.

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.
2. Sélectionnez **nouvelle stratégie**.
3. Entrez un nom descriptif pour la stratégie, puis cliquez sur **Ajouter les applications**.
4. Dans le volet **Ajouter épinglés des applications** , recherchez les applications que vous souhaitez ajouter, puis cliquez sur **Ajouter**.  Pour afficher une liste de toutes les applications, sélectionnez **application équipes de banque**. Lorsque vous avez choisi votre liste des applications, cliquez sur **Ajouter**.

     ![application-le programme d’installation-stratégies-ajouter-apps.png](media/app-setup-policies-add-apps.png)

5. Organiser les applications dans l’ordre que vous souhaitez qu’il apparaît dans les équipes, puis cliquez sur **Enregistrer**.

    ![App-Setup-Policies-New-Policy-Setup.png](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a>Modifier une stratégie de paramètres d’application

Vous pouvez utiliser le centre d’administration de Microsoft Teams ou de Windows PowerShell pour modifier une stratégie, notamment la stratégie globale de (valeur par défaut à l’échelle de l’organisation) et les stratégies personnalisées que vous créez. 

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.
2. Sélectionnez la stratégie que vous souhaitez modifier. 
3. À partir de là, apportez les modifications souhaitées. Vous pouvez ajouter, supprimer et modifier l’ordre des applications.
4. Cliquez sur **Enregistrer**. 

## <a name="assign-a-custom-app-setup-policy-to-users"></a>Affecter une stratégie du programme d’installation d’application personnalisée aux utilisateurs

Vous pouvez utiliser le centre d’administration Microsoft Teams pour affecter une stratégie personnalisée à des utilisateurs individuels ou de Windows PowerShell pour attribuer une stratégie personnalisée pour les groupes d’utilisateurs, par exemple un groupe de sécurité ou un groupe de distribution.

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a>Affecter une stratégie du programme d’installation d’application personnalisée à des utilisateurs individuels

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies attribuées**, cliquez **sur Modifier**.
3. Sous **stratégie de l’installation des applications d’équipes**, sélectionnez la stratégie d’application le programme d’installation que vous voulez attribuer, puis cliquez sur **Enregistrer**.

    ![policy.png du attribuer stratégies d’application du programme d’installation](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a>Affecter une stratégie du programme d’installation d’application personnalisée à utilisateurs d’un groupe

Vous souhaiterez peut-être attribuer une stratégie du programme d’installation d’application personnalisée à plusieurs utilisateurs que vous avez déjà identifié. Par exemple, vous souhaiterez peut-être attribuer une stratégie à tous les utilisateurs dans un groupe de sécurité. Pour cela, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business. Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

Dans cet exemple, nous affectons une stratégie du programme d’installation d’application personnalisée appelée stratégie de ressources humaines App du programme d’installation pour tous les utilisateurs dans le groupe projet de Contoso Pharmaceuticals RH.  

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
Affecter tous les utilisateurs dans le groupe à une stratégie du programme d’installation d’application particulière. Dans cet exemple, il est stratégie de ressources humaines App du programme d’installation.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.

## <a name="faq"></a>FAQ

### <a name="working-with-app-setup-policies"></a>Utilisation de stratégies d’installation des applications

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a>Les stratégies de paramètres d’application intégrée sont inclus dans le centre d’administration Microsoft Teams ?

- **Global (à l’échelle de l’organisation par défaut)**: cette stratégie par défaut s’applique à tous les utilisateurs de votre organisation, sauf si vous attribuez une autre stratégie. Modifier la stratégie globale pour les applications de code confidentiel qui sont importantes pour vos utilisateurs.
- **FirstLineWorker**: cette stratégie est destinée aux travailleurs firstline. Vous pouvez l’affecter à des travailleurs firstline dans votre organisation. Il est important de savoir que telles que des stratégies personnalisées que vous créez, vous devez attribuer la stratégie aux utilisateurs pour les paramètres actif. Pour plus d’informations, consultez la section [affecter une stratégie du programme d’installation d’application personnalisée aux utilisateurs](#assign-a-custom-app-setup-policy-to-users) de cet article.

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a>Pourquoi ne puis-je pas trouver une application dans le volet d’applications épinglé ajouter ?

Pas toutes les applications peuvent être épinglées aux équipes via une stratégie d’application du programme d’installation. Certaines applications ne peuvent pas en charge cette fonctionnalité. Pour rechercher les applications qui peuvent être mis en attente, de recherche pour l’application dans le volet **Ajouter épinglés apps** . Vous pouvez ajouter des onglets ayant une portée personnelle (onglets statiques) et des robots pour le client de bureau équipes et ces applications sont disponibles dans le volet **Ajouter épinglés applications** .

N’oubliez pas que l’app store équipes répertorie toutes les applications d’équipes, tandis que le volet **Ajouter épinglé applications** inclut uniquement les applications qui peuvent être épinglées aux équipes via une stratégie. 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a>Je suis un équipes pour administrateur de formation. Que dois-je savoir à propos des stratégies de configuration des applications dans les équipes pour l’éducation ?

L’application d’appel n’est pas disponible dans les équipes pour l’éducation. Lorsque vous créez une nouvelle stratégie du programme d’installation d’application personnalisée, l’application d’appel s’affiche dans la liste des applications. Toutefois, l’application n’est pas épinglée aux clients d’équipes et équipes pour les utilisateurs de formation ne verrez pas l’application des appels dans les équipes. 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a>Combien d’applications peuvent être ajoutées à une stratégie ?

Un minimum de deux applications doit être épinglé sur les clients mobiles équipes (iOS et Android). Si une stratégie a moins de deux applications, les clients mobiles ne reflèteront pas les paramètres de stratégie et au lieu de cela va continuer à utiliser la configuration existante.

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a>Combien de temps faut-il pour que les modifications de stratégie prennent effet ?

Une fois que vous modifiez la stratégie globale ou affectez une stratégie, elle peut prendre jusqu'à 24 heures pour que les modifications prennent effet.

### <a name="user-experience"></a>Expérience utilisateur

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a>Comment les utilisateurs peuvent voir tous leurs applications affichées dans les équipes ?

Pour afficher toutes les applications qui sont mis en attente pour un utilisateur, les utilisateurs devront peut-être effectuer les opérations suivantes selon le nombre d’applications installées et la taille de la fenêtre du client leurs équipes.

|Client de bureau d’équipes |Client mobile d’équipes |
|---------|---------|
|Dans la barre d’application sur le côté d’équipes, cliquez sur **... Plus d’applications**.| Dans la barre d’application au bas des équipes, faites glisser vers le haut.|
|![App-Setup-Policies-Desktop-More-Apps.png](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-mobile-More-Apps.png](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a>Que dois-je savoir à propos de l’expérience mobile équipes ?

Les clients mobiles équipes (iOS et Android) actuellement ne reconnaissent pas les applications personnelles avec onglets statiques. Selon les applications de la stratégie, les applications épinglées sur le client de bureau équipes n’apparaîtront dans les clients mobiles équipes. Robots personnels il continuera d’apparaître dans la conversation sur les clients mobiles.

Avec les clients mobiles équipes, les utilisateurs verront principaux équipes applications telles que les activités, la conversation et les équipes, et vous pouvez ajouter des applications internes de Microsoft, tels que des équipes.

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a>Pouvant utilisateurs modifier l’ordre des applications épinglés via une stratégie ?

Actuellement, les utilisateurs peuvent modifier l’ordre de leurs applications épinglées sur les clients mobiles équipes mais pas sur les clients de bureau ou web équipes. 

### <a name="custom-teams-apps"></a>Applications personnalisées d’équipes

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-through-appsource-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a>Mon organisation créé une application équipes personnalisée et publié par le biais de AppSource, mais l’icône d’application n’est pas affichée comme prévu lors de l’application est épinglée à la barre d’application dans les équipes. Comment dois-je faire ? 

Assurez-vous que vous suivez les instructions du logo avant de soumettre l’application. Pour plus d’informations, voir [liste de vérification pour l’envoi du tableau de bord vendeur](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist). 

 ## <a name="related-topics"></a>Rubriques connexes
- [Publier une application dans le catalogue d’applications client à partir du client d’équipes](tenant-apps-catalog-teams.md)
