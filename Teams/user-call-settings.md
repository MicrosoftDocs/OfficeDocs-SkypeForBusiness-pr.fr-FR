---
title: Configurer les paramètres d’appel pour les utilisateurs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Découvrez comment configurer les paramètres utilisateur pour le transfert et la délégation des appels.
ms.openlocfilehash: 41d954f468166fd8600601f98ea98d5be129eccd
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681995"
---
# <a name="configure-call-settings-for-your-users"></a>Configurer les paramètres d’appel pour vos utilisateurs

Cet article décrit comment vous, l’administrateur, pouvez modifier les paramètres de transfert d’appel et de délégation pour vos utilisateurs. Vous souhaiterez peut-être modifier ces paramètres, par exemple, si :

- Un utilisateur est en congé de maladie et vous devez vous assurer que les appels entrants à l’utilisateur sont transférés à un collègue.
- Vous devez inspecter les paramètres de transfert d’appel pour tous les utilisateurs d’un service et les corriger éventuellement en fonction des besoins.
- Un nouvel assistant a été employé et vous devez l’ajouter en tant que délégué pour un groupe d’employés.

Vous pouvez utiliser le centre d’administration Teams ou Teams applets de commande PowerShell pour afficher et modifier les paramètres d’appel des utilisateurs.

Pour définir les paramètres d’appel d’un utilisateur, l’utilisateur doit disposer d’une licence système Téléphone Microsoft attribuée.

## <a name="use-the-teams-admin-center"></a>Utiliser le centre d’administration Teams

Vous pouvez utiliser le centre d’administration Teams pour configurer les paramètres de transfert d’appel et sans réponse, la prise en charge des appels de groupe et la délégation d’appel pour vos utilisateurs.

Pour configurer les paramètres de transfert d’appel immédiat :

1. Dans le centre d’administration Teams, accédez à **Users** > **Manage users** et sélectionnez un utilisateur.

2. Dans la page des détails de l’utilisateur, accédez à l’onglet **Voix** .

3. Sous **Règles de réponse aux appels**, sélectionnez **Être immédiatement transféré**, puis sélectionnez le type et la destination de transfert d’appel appropriés.

Pour configurer la sonnerie simultanée, dans la même page, sélectionnez **Sonner les appareils de l’utilisateur**. Dans la liste déroulante **Autoriser également** , sélectionnez le paramètre de sonnerie simultané approprié.

Pour configurer les paramètres sans réponse, dans la même page, sélectionnez le paramètre approprié dans la liste **déroulante Si sans réponse** . Dans **l’Anneau pendant ces nombreuses secondes avant de rediriger** la liste déroulante, spécifiez le nombre de secondes d’attente.

La configuration de la délégation d’appel et de la prise d’appel de groupe est intégrée aux paramètres de transfert d’appel et sans réponse en sélectionnant le type approprié. Par exemple, pour configurer que les appels doivent également sonner les délégués de l’utilisateur, dans la même page, sélectionnez **Délégation d’appel** sous **Autoriser également**. Ajoutez ensuite les délégués appropriés en sélectionnant **Ajouter des personnes** et en cliquant sur **Enregistrer**.

## <a name="use-powershell"></a>Utiliser PowerShell

Vous pouvez utiliser PowerShell pour configurer les paramètres de transfert d’appel et de délégation pour vos utilisateurs.  Vous allez utiliser les applets de commande suivantes, qui sont disponibles dans Teams module PowerShell version 4.0 ou ultérieure :

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) : affiche les paramètres de transfert d’appel, les délégués et les informations de suppression pour un utilisateur.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) : définit les paramètres de transfert d’appel pour un utilisateur.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) : ajoute un nouveau délégué avec des autorisations pour un utilisateur.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) : modifie les autorisations pour un délégué existant.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) : supprime un délégué d’un utilisateur.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Afficher les paramètres de transfert d’appel et de délégation pour un utilisateur

Pour afficher les paramètres actuels de transfert d’appel et de délégation pour un utilisateur, utilisez l’applet de commande Get-CsUserCallingSettings, comme illustré dans l’exemple suivant :

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

La sortie montre que la sonnerie simultanée de l’utilisateur1 aux délégués est configurée. Les appels sans réponse sont envoyés à la messagerie vocale après 20 secondes. User2 est défini comme délégué avec toutes les autorisations déléguées.

### <a name="set-call-forward-settings-for-a-user"></a>Définir les paramètres de transfert d’appel pour un utilisateur

Pour transférer tous les appels de user1 à user2, utilisez l’applet de commande Set-CsUserCallingSettings, comme indiqué dans l’exemple suivant :

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Pour faire sonner simultanément tous les délégués pour user3, utilisez l’applet de commande Set-CsUserCallingSettings, comme illustré dans l’exemple suivant :

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

L’exemple suivant utilise l’applet de commande Set-CsUserCallingSettings pour configurer un groupe d’appels pour user4 avec user5 et user6 comme membres. Tous les appels aux membres du groupe sont transférés dans l’ordre dans lequel ils sont définis :

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Pour plus d’exemples, consultez [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Ajouter un délégué appelant pour un utilisateur

Pour ajouter user2 en tant que délégué pour user1 avec toutes les autorisations autorisées, utilisez l’applet de commande New-CsUserCallingDelegate, comme illustré dans l’exemple suivant :

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Modifier les autorisations des délégués appelants

Pour modifier les autorisations de délégué, par exemple pour ne pas autoriser user2 à effectuer des appels pour user1, utilisez l’applet de commande Set-CsUserCallingDelegate, comme indiqué dans l’exemple suivant :

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Supprimer un délégué appelant pour un utilisateur

Pour supprimer user2 en tant que délégué pour user1, utilisez l’applet de commande Remove-CsUserCallingDelegate, comme illustré dans l’exemple suivant :

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>Sujets associés

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
