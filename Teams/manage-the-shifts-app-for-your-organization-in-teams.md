---
title: Gérer l’application des équipes de votre organisation dans Microsoft Teams
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment configurer et gérer l’application des déplacements dans les équipes pour les travailleurs firstline dans votre organisation.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fdd9c47e54c9ce51e736363eb47227614824a4c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893356"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application des équipes de votre organisation dans Microsoft Teams

> [!IMPORTANT]
> Effet 2019, octobre 1, Microsoft StaffHub sera être retirée. Nous créons StaffHub fonctionnalités, notamment la gestion de tâches et calendrier dans Microsoft Teams. Des fonctionnalités supplémentaires pour les travailleurs firstline mettra en place pour les équipes au fil du temps. Pour plus d’informations, voir [Microsoft StaffHub à retirer](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).  

## <a name="overview-of-shifts"></a>Vue d’ensemble des équipes
L’application d’équipes dans Microsoft Teams conserve firstline employés connectés et synchronisés. Il est mobile d’abord généré pour la gestion du temps efficace et rapide et de communication pour les équipes. Déplacements permet aux travailleurs firstline et leurs responsables utilisent leurs appareils mobiles pour gérer les planifications et garder le contact. 

- Responsables de créer, mettre à jour et gérer les planifications de travail d’équipe pour les équipes. Ils peuvent envoyer des messages à une personne (« il existe un fractionnement sur le plancher ») ou l’ensemble de l’équipe (« les familles régionaux arrive dans 20 minutes »). Ils peuvent également envoyer des documents de stratégie, des bulletins d’informations et des vidéos. 
- Employés afficher leurs équipes à venir, peuvent voir qui d’autre est prévue pour le jour, demande d’échange ou de proposer une équipe et durée hors de la demande. 

Il est important de savoir qu’équipes actuellement ne prennent en charge les utilisateurs invités. Cela signifie que les invités d’une équipe ne peut pas être ajoutées à ou utilisent planifications MAJ lors de l’accès invité est activé dans les équipes. 

## <a name="availability-of-shifts"></a>Disponibilité des équipes

Déplacements est disponible dans tous les abonnements Office 365 qui incluent des équipes, avec quelques exceptions. Les exceptions sont nous gouvernement nuage communautaire (GCC) et les équipes libres. Équipes n’est pas disponible dans Office 365 américains ou équipes libre offres.

Pour en savoir plus sur la gestion des licences pour les équipes, voir [Gestion des licences Office 365 pour les équipes](Office-365-licensing.md).

## <a name="set-up-shifts"></a>Configurer des équipes

### <a name="enable-or-disable-shifts-in-your-organization"></a>Activer ou désactiver des équipes au sein de votre organisation.

Équipes est activée par défaut pour tous les utilisateurs d’équipes au sein de votre organisation. Vous pouvez désactiver ou activer l’application pour votre organisation dans le centre d’administration Microsoft 365.

1. Connectez-vous au centre d’administration Microsoft 365 avec votre compte d’administration d’Office 365.
2. Accédez à **paramètres** > **Services et compléments** > **Équipes Microsoft**. 
3. Sous **paramètres au niveau du client**, sélectionnez **applications**, puis sous **Applications par défaut**, désactivez ou sélectionnez la case à cocher **équipes** pour activer ou désactiver l’application. 

    ![Capture d’écran de la section applications par défaut] (media/firstline-worker-enable-disable-shifts.png "Capture d’écran de la section par défaut des applications dans le centre d’administration Microsoft 365, affichant la liste des applications, notamment les déplacements des applications")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Utiliser la stratégie du programme d’installation FirstLineWorker application aux équipes de code confidentiel pour les équipes

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

Stratégies d’application du programme d’installation vous permettent de personnaliser des équipes pour mettre en surbrillance les applications qui sont plus importantes pour les utilisateurs de votre organisation. La liste des applications dans une stratégie sont épinglées sur la barre d’application&mdash;la barre sur le côté du client de bureau équipes et en bas des clients mobiles équipes&mdash;où les utilisateurs peuvent rapidement et facilement y accéder. 
 
Équipes inclut une stratégie de configuration d’une application de FirstLineWorker intégrée que vous pouvez attribuer aux travailleurs firstline dans votre organisation. Par défaut, la stratégie inclut les applications de l’activité, équipes, la conversation et appeler. 

Pour afficher la stratégie FirstLineWorker, dans le volet de navigation gauche de Microsoft Teams & Skype entreprise centre d’administration, accédez à **l’application des équipes** > **stratégies du programme d’installation des applications**.

![Capture d’écran de la stratégie du programme d’installation d’application FirstLineWorker dans les équipes Microsoft & Skype entreprise centre d’administration] (media/firstline-worker-app-setup-policy.png "Capture d’écran de la stratégie du programme d’installation d’application FirstLineWorker dans les équipes Microsoft & Skype entreprise centre d’administration")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Affecter la stratégie FirstLineWorker à des utilisateurs individuels

1. Dans la navigation de gauche du Microsoft Teams & Skype entreprise centre d’administration, accédez à des **utilisateurs**, puis cliquez sur l’utilisateur.
2. En regard de **stratégies attribuées**, cliquez **sur Modifier**.
3. Sous **stratégie de l’installation des applications d’équipes**, sélectionnez **FirstLineWorker**, puis cliquez sur **Enregistrer**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>Attribuez-les FirstLineWorker application du programme d’installation pour les utilisateurs dans un groupe

Vous pouvez affecter la stratégie du programme d’installation d’application FirstLineWorker aux utilisateurs dans un groupe, par exemple un groupe de sécurité, en vous connectant à Azure Active Directory PowerShell pour le module graphique et le Skype pour le module PowerShell Business. Pour plus d’informations sur l’utilisation de PowerShell pour gérer les équipes, voir [Vue d’ensemble de PowerShell équipes](teams-powershell-overview.md).

Dans cet exemple, nous affectons la stratégie du programme d’installation d’application FirstLineWorker à tous les utilisateurs dans le groupe équipe Firstline de Contoso.

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
Affecter tous les utilisateurs dans le groupe à la stratégie du programme d’installation d’application FirstLineWorker.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
Selon le nombre de membres dans le groupe, cette commande peut prendre plusieurs minutes à exécuter.

## <a name="related-topics"></a>Rubriques connexes
- [Déplace l’aide pour les travailleurs firstline et responsables](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)