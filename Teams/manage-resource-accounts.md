---
title: Gérer les comptes de ressource dans Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: En savoir plus sur la gestion des comptes de ressource dans Microsoft Teams
ms.openlocfilehash: ad435a812191cc8f7b9061ac5fba2bbe626b908e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886060"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

Un compte de ressource est également appelée un objet utilisateur désactivé dans Azure Active Directory et peut être utilisé pour représenter les ressources en général. Dans Exchange, il peut être utilisé pour représenter des salles de conférence, par exemple et les autoriser à un numéro de téléphone. Un compte de ressource peut être hébergé dans Microsoft 365 ou sur site à l’aide de Skype pour Business server, et ces comptes sont créés à l’aide des commandes Powershell.

Dans Microsoft Teams ou Skype pour Business en ligne, chaque file d’attente des appels ou auto attendant est nécessaire pour ont un compte de ressource. Si un compte de ressource doit être un numéro de téléphone affecté dépendent de l’utilisation prévue de la file d’attente d’appel associé ou le standard automatique. Consultez les articles sur les files d’attente de l’appel et qui sont liées au bas de cet article avant d’affecter un numéro de téléphone à un compte de ressource de standards automatiques.

> [!NOTE]
> Cet article s’applique à Microsoft Teams et Skype pour Business Online.

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a>Conditions préalables pour affecter un numéro de téléphone à un compte de ressource

Mise en route il est important de garder à l’esprit quelques points :
  
- Vous devez attribuer une licence de système téléphonique à un compte de ressource qui sera associé à la file d’attente standard ou un appel automatique. Pour plus d’informations sur les licences, voir [Gestion des licences de module complémentaire équipes Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    

    > [!NOTE]
    > Pour rediriger les appels vers des personnes dans votre organisation en ligne, ils doivent disposer d’une licence de **Système téléphonique** et être activés pour Enterprise Voice ou Office 365 appelant Plans. Consultez les [licences d’affecter des équipes Microsoft](assign-teams-licenses.md). Pour les activer pour Enterprise Voice, vous pouvez utiliser Windows PowerShell. Par exemple, exécutez :  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Vous pouvez affecter un numéro hybride de routage Direct à votre compte de ressource.  Pour plus d’informations, voir [Planifier le routage Direct](direct-routing-plan.md) .
- Pour les plans d’appel Microsoft, vous ne pouvez affecter payants et les numéros de téléphone gratuit service que vous avez obtenu dans le **Centre d’administration de Microsoft équipes** ou transféré à partir d’un autre fournisseur de services vers un compte de ressource. Pour obtenir et utiliser des numéros gratuits service, vous devez configurer les crédits de Communications.

> [!NOTE]
> Numéros de téléphone de l’utilisateur (abonné) ne peut pas être affectés à un compte de ressource. Numéro payant service ou numéros de téléphone peuvent être utilisées.

Pour affecter un numéro de téléphone à un compte de ressource, vous devez obtenir ou transférer votre appel payant existant ou un service gratuit numéros. Une fois que vous obtenez les numéros de téléphone gratuit service payant, ils s’affichent dans le **Centre d’administration de Microsoft équipes** > **vocale** > **numéros de téléphone**et la volonté de **type numérique** présent figurer en tant que **Service - gratuit**. Pour obtenir vos numéros de service, voir les [numéros de téléphone de mise en service](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) , ou si vous souhaitez transférer un numéro de service existant, voir les [numéros de téléphone transfert vers Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Si vous êtes en dehors des États-Unis, vous ne pouvez pas utiliser le centre d’administration Microsoft Teams pour obtenir les numéros de service. Accédez à [Gérer les numéros de téléphone pour votre organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) à la place pour voir comment le faire à partir de l’extérieur des États-Unis.

## <a name="create-a-resource-account-in-powershell"></a>Créer un compte de ressource dans Powershell

 Vous souhaite créer un compte de ressource en exécutant l’applet de commande Powershell approprié selon vos besoins (pour un ou plusieurs comptes de ressources), nommez chacune d’elles et ainsi de suite. Il n’existe actuellement aucune option pour la création d’un compte de ressource dans le centre d’administration Microsoft Teams, mais vous pouvez modifier les numéros de téléphone et modifier les appels en file d’attente ou automatique attendant affectations d’un compte de ressource.

Selon que votre numéro de téléphone est situé en ligne ou sur site, vous devez vous connecter à l’invite de Powershell approprié avec des privilèges d’administrateur.

- Implémentations hybride (numéros de numéros hébergés sur routage Direct, OPCH et CCE) utilise [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) pour créer un compte de ressource qui est hébergé sur site.  
- En ligne uniquement implémentations utilise [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) pour avoir un compte de ressource qui est hébergé en ligne.

Voici un exemple d’environnement de ligne de la création d’un compte de ressource :

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

Pour plus d’informations sur cette commande, voir [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) .

> [!NOTE]
> Il est plus facile de définir le numéro de téléphone en ligne à l’aide du centre d’administration Microsoft Teams, comme décrit dans la section suivante. Vous pouvez également utiliser le `Set-CsOnlineVoiceApplicationInstance` commande pour attribuer un numéro de téléphone pour le compte de ressources après sa création initiale comme :

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

Pour plus d’informations sur cette commande, voir [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) .

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a>Gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams

Pour gérer les paramètres de compte de ressource dans le centre d’administration de Microsoft Teams, accédez à **paramètres à l’échelle de la société**  > **comptes de ressources**, sélectionnez le compte de ressources que vous souhaitez modifier les paramètres pour, puis cliquez sur le bouton **Modifier** . dans l’écran **Modifier le compte de la ressource** , vous ne pourrez pas modifier le :

- **Nom d’affichage** pour le compte
- File d’attente des appels ou qui utilise le compte de standard automatique
- Numéro de téléphone affectée au compte

Lorsque vous avez terminé, cliquez sur **Enregistrer**.

## <a name="related-information"></a>Informations connexes

Pour les implémentations qui sont hybride avec Skype pour Business Server :

[Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[Configurer des standards automatiques cloud](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

Pour les implémentations d’équipes ou Skype pour Business Online :

[Quels sont les standards automatiques du système téléphonique ?](what-are-phone-system-auto-attendants.md)

[Configurer les standards automatiques du système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[Exemple de petite entreprise : configurer un standard automatique](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[Créer une file d’attente d’appels de système téléphonique](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[Nouvelle CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[Nouvelle CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
