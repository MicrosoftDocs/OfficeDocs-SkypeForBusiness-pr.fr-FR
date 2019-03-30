---
title: Gérer l’application Shifts pour votre organisation dans Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application des déplacements dans les équipes pour les travailleurs Firstline dans votre organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b1ef7ee44b1d6318b85461b5d6b9d4173cc8552
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013208"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Shifts pour votre organisation dans Microsoft Teams

> [!IMPORTANT]
> Effet 2019, octobre 1, Microsoft StaffHub sera être retirée. Nous créons StaffHub fonctionnalités dans Microsoft Teams. Aujourd'hui, les équipes inclut l’application des équipes de gestion de la planification et des fonctionnalités supplémentaires seront intégrées au fil du temps. StaffHub cessera de fonctionner pour tous les utilisateurs sur le 1 octobre 2019. Toute personne qui essaie d’ouvrir StaffHub s’affichera un message pronom pour télécharger les équipes. Pour plus d’informations, voir [Microsoft StaffHub à retirer](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Vue d’ensemble des équipes
L’application d’équipes dans Microsoft Teams conserve Firstline employés connectés et synchronisés. Il est mobile d’abord généré pour la gestion du temps efficace et rapide et de communication pour les équipes. Déplacements permet aux travailleurs Firstline et leurs responsables utilisent leurs appareils mobiles pour gérer les planifications et garder le contact. 

- Responsables de créer, mettre à jour et gérer les planifications de travail d’équipe pour les équipes. Ils peuvent envoyer des messages à une personne (« il existe un fractionnement sur le plancher ») ou l’ensemble de l’équipe (« les familles régionaux arrive dans 20 minutes »). Ils peuvent également envoyer des documents de stratégie, des bulletins d’informations et des vidéos. 
- Employés afficher leurs équipes à venir, peuvent voir qui d’autre est prévue pour le jour, demande d’échange ou de proposer une équipe et durée hors de la demande. 

Il est important de savoir qu’équipes actuellement ne prennent en charge les utilisateurs invités. Cela signifie que les invités d’une équipe ne peut pas être ajoutées à ou utilisent planifications MAJ lors de l’accès invité est activé dans les équipes. 

## <a name="availability-of-shifts"></a>Disponibilité des équipes

Déplacements est disponible dans tous les abonnements Office 365 qui incluent des équipes, avec quelques exceptions. Les exceptions sont nous gouvernement nuage communautaire (GCC) et les équipes libres. Équipes n’est pas disponible dans Office 365 américains ou équipes libre offres.

Pour plus d’informations sur la gestion des licences pour les équipes, notamment la liste des abonnements Office 365 qui inclut des équipes, voir [Gestion des licences Office 365 pour les équipes](../../Office-365-licensing.md).

## <a name="location-of-shifts-data"></a>Emplacement des données d’équipes

Équipes données sont actuellement stockées dans Azure dans les centres de données en Amérique du Nord et Europe occidentale Asie-Pacifique. Pour plus d’informations sur le stockage des données, voir [où se trouvent mes données](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurer des équipes

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver des équipes au sein de votre organisation.

Équipes est activée par défaut pour tous les utilisateurs d’équipes au sein de votre organisation. Vous pouvez désactiver ou activer l’application pour votre organisation dans le centre d’administration Microsoft 365.

1. Connectez-vous au centre d’administration Microsoft 365 avec votre compte d’administration d’Office 365.
2. Accédez à **paramètres** > **compléments Services &** > **Équipes Microsoft**. 
3. Sous **paramètres au niveau du client**, sélectionnez **applications**, puis sous **Applications par défaut**, désactivez ou sélectionnez la case à cocher **équipes** pour activer ou désactiver l’application. 

    ![Capture d’écran de la section applications par défaut] (../../media/firstline-worker-enable-disable-shifts.png "Capture d’écran de la section par défaut des applications dans le centre d’administration Microsoft 365, affichant la liste des applications, notamment les déplacements des applications")

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a>Utilisent la stratégie du programme d’installation Firstline travailleur de l’application à des équipes de code confidentiel pour les équipes

> [!INCLUDE [Preview customer token](../../includes/preview-feature.md)]

Stratégies d’application du programme d’installation vous permettent de personnaliser des équipes pour mettre en surbrillance les applications qui sont plus importantes pour les utilisateurs de votre organisation. La liste des applications dans une stratégie sont épinglées sur la barre d’application&mdash;la barre sur le côté du client de bureau équipes et en bas des clients mobiles équipes&mdash;où les utilisateurs peuvent rapidement et facilement y accéder. 
 
Les équipes inclut une stratégie du programme d’installation d’une application de travail Firstline intégrée que vous pouvez attribuer aux travailleurs Firstline dans votre organisation. Par défaut, la stratégie inclut les applications de l’activité, équipes, la conversation et appeler. 

Pour afficher la stratégie de travail Firstline, dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.

![Capture d’écran de la stratégie du programme d’installation Firstline travailleur de l’application dans le centre d’administration Microsoft équipes] (../../media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie du programme d’installation Firstline travailleur de l’application dans le centre d’administration Microsoft équipes")

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a>Attribuer la stratégie de travail Firstline à des utilisateurs individuels

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies attribuées**, cliquez **sur Modifier**.
3. Sous **stratégie de l’installation des applications d’équipes**, sélectionnez **FirstlineWorker**, puis cliquez sur **Enregistrer**.

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a>Affecter le travailleur Firstline stratégie d’application du programme d’installation aux utilisateurs dans un groupe

Vous pouvez affecter le travailleur Firstline stratégie d’application du programme d’installation aux utilisateurs dans un groupe, par exemple un groupe de sécurité, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business. Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](../../teams-powershell-overview.md).

Dans cet exemple, nous affectons le processus de travail Firstline stratégie du programme d’installation d’application à tous les utilisateurs dans le groupe équipe Firstline de Contoso.

> [!NOTE]
> Assurez-vous que votre première connexion à Azure Active Directory PowerShell pour le module graphique et Skype pour le module PowerShell Business en suivant les étapes de [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenir le GroupObjectId du groupe particulier.
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Obtenir les membres du groupe spécifié.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Affecter tous les utilisateurs dans le groupe à la stratégie du programme d’installation d’application FirstlineWorker.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.

## <a name="related-topics"></a>Rubriques connexes
- [Déplace l’aide pour les travailleurs Firstline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
