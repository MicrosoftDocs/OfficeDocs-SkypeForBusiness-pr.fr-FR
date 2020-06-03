---
title: Gérer les stratégies d’appel d’urgence dans Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser et gérer des politiques d’appel d’urgence dans Microsoft teams pour définir ce qui se passe quand un utilisateur de teams dans votre organisation effectue un appel d’urgence.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98d6fb5eba98701cddccb808e5670fb34a00efbf
ms.sourcegitcommit: d8e05e66311725f8ff6d28011355129baeb305b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44539481"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>Gérer les stratégies d’appel d’urgence dans Microsoft teams

Si votre organisation utilise des [plans d’appels](set-up-calling-plans.md) ou un [routage direct du système téléphonique](direct-routing-landing-page.md), vous pouvez utiliser les politiques d’appel d’urgence de Microsoft teams pour définir ce qui se produit quand un utilisateur de teams de votre organisation effectue un appel d’urgence. Vous pouvez définir la personne à notifier et la manière dont elle est avertie lorsqu’un utilisateur auquel cette stratégie appelle des services d’urgence. Par exemple, vous pouvez configurer des paramètres de stratégie pour avertir automatiquement le support technique de votre organisation et les informer dans les appels d’urgence.  

Vous pouvez gérer les stratégies d’appel d' **Voice**urgence en accédant à  >  **stratégies d’urgence** vocale dans le centre d’administration Microsoft teams ou à l’aide de Windows PowerShell. Elles peuvent être attribuées à des utilisateurs et des [sites réseau](cloud-voice-network-settings.md).

Pour les utilisateurs, vous pouvez utiliser la stratégie globale par défaut de l’organisation ou créer et attribuer des stratégies personnalisées. Les utilisateurs bénéficieront automatiquement de la stratégie globale, sauf si vous créez et attribuez une stratégie personnalisée. Gardez à l’esprit que vous pouvez modifier les paramètres de la stratégie globale, mais que vous ne pouvez pas les renommer ou les supprimer. Pour les sites réseau, vous créez et attribuez des stratégies personnalisées.

Si vous avez affecté une stratégie d’appel d’urgence à un site réseau et à un utilisateur et que ce dernier se trouve sur ce site réseau, la stratégie attribuée au site réseau remplace celle qui est affectée à l’utilisateur.

## <a name="create-a-custom-emergency-calling-policy"></a>Créer une stratégie d’appel d’urgence personnalisée

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description.
4. Définissez la manière dont vous souhaitez informer les membres de votre organisation, en général le centre de sécurité, lors de l’appel d’urgence. Pour ce faire, sous **mode de notification**, sélectionnez l’une des options suivantes :
    - **Envoyer la notification uniquement**: un message de discussion teams est envoyé aux utilisateurs et aux groupes que vous spécifiez.
    - **Conférences lancées, mais qui ne sont**pas activées : un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez et ils peuvent écouter (mais ne pas participer) à la conversation entre l’appelant et l’opérateur PSAPI.
    - **Conférences dans et** activées **(bientôt disponible)**: un message de discussion d’équipes est envoyé aux utilisateurs et aux groupes que vous spécifiez, et ils peuvent basculer entre l’appelant et l’opérateur PSAPI.
5.  Si vous avez sélectionné la Conférence rendez-vous, mais que vous êtes en mode **muet** , dans la zone **numéros à composer pour les notifications d’appels d’urgence** , vous pouvez entrer un numéro de téléphone PSTN d’un utilisateur ou d’un groupe pour appeler et rejoindre l’appel d’urgence. Par exemple, entrez le numéro du centre de sécurité de votre organisation, qui recevra un appel en cas d’appel d’urgence et peut alors écouter l’appel.
6. Recherchez et sélectionnez un ou plusieurs utilisateurs ou groupes, comme le centre de sécurité de votre organisation, pour avertir en cas d’appel d’urgence.  La notification peut être envoyée aux adresses de courrier des utilisateurs, des groupes de distribution et des groupes de sécurité. Un maximum de 50 utilisateurs peut être notifié.
7. Cliquez sur **Appliquer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).

## <a name="edit-an-emergency-calling-policy"></a>Modifier une politique d’appel d’urgence

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Vous pouvez modifier la stratégie globale ou toutes les stratégies personnalisées que vous créez.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .
2. Sélectionnez la stratégie en cliquant à gauche du nom de la stratégie, puis cliquez sur **modifier**.
3. Apportez les modifications souhaitées, puis cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

Voir [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs

### <a name="using-the-microsoft-teams-admin-center"></a>Utilisation du centre d’administration Microsoft Teams

Pour attribuer une stratégie à un utilisateur :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, et accédez aux **Utilisateurs**, puis cliquez sur l’utilisateur.
2. Cliquez sur **stratégies**, puis en regard de **stratégies affectées**, cliquez sur **modifier**.
3. Sous **stratégie d’appel d’urgence**, sélectionnez la stratégie que vous voulez attribuer, puis cliquez sur **Enregistrer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.  

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft **Voice**Teams, accédez à  >  **stratégies d’urgence**vocale, puis cliquez sur l’onglet politiques d' **appel** .
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci.
3. Sélectionnez **Gérer les utilisateurs**.
4. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis sélectionnez **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

### <a name="using-powershell"></a>Utiliser PowerShell

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a>Affecter une stratégie d’appel d’urgence personnalisée à un utilisateur

Voir [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a>Affecter une stratégie d’appel d’urgence personnalisée aux utilisateurs d’un groupe

Il est possible que vous souhaitiez affecter une stratégie d’appel d’urgence personnalisée à plusieurs utilisateurs déjà identifiés. Par exemple, vous souhaiterez probablement affecter une stratégie à l’ensemble des utilisateurs d’un groupe de sécurité. Pour cela, vous devez vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise.

Dans cet exemple, nous affectons une stratégie appelée stratégie d’appel d’urgence d’opérations à tous les utilisateurs du groupe opérations de contoso.  

> [!NOTE]
> Assurez-vous d’abord de vous connecter au module Azure Active Directory PowerShell pour Graph et au module PowerShell Skype entreprise en suivant les étapes décrites dans l’article [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenez la GroupObjectId du groupe en particulier.
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
Obtenez les membres du groupe spécifié.
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Attribuez à tous les utilisateurs du groupe une stratégie d’équipe particulière. Dans cet exemple, il s’agit de la stratégie d’acheminement des appels d’urgence.
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
En fonction du nombre de membres du groupe, cette commande risque de prendre quelques minutes.

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>Affecter une stratégie d’appel d’urgence personnalisée à un site réseau

Utilisez l’applet de connexion [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) pour attribuer une stratégie d’appel d’urgence à un site réseau.

L’exemple suivant montre comment affecter une stratégie appelée stratégie d’appel d’urgence contoso 1 au site site1.

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>Voir aussi

- [Gérer les stratégies de routage des appels d’urgence dans teams](manage-emergency-call-routing-policies.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs dans teams](assign-policies.md)
