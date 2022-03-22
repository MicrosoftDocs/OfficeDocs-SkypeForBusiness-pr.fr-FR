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
description: Découvrez comment configurer les paramètres utilisateur pour le forwarding et la délégation d’appels.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689078"
---
# <a name="configure-call-settings-for-your-users"></a>Configurer les paramètres d’appel pour vos utilisateurs

Cet article décrit comment vous, en tant qu’administrateur, pouvez modifier les paramètres de forwardage et de délégation d’appel pour vos utilisateurs. Vous pouvez modifier ces paramètres, par exemple, dans les cas ci-après :

- Un utilisateur est en congé maladie et vous devez vous assurer que les appels entrants à l’utilisateur sont transmis à un collègue.

- Vous devez inspecter les paramètres de forward d’appel pour tous les utilisateurs d’un service et éventuellement les corriger le cas échéant.

- Un nouvel assistant a été employé et vous devez l’ajouter en tant que délégué pour un groupe d’employés.

Vous pouvez utiliser le Teams d’administration ou Teams cmdlets PowerShell pour afficher et modifier les paramètres d’appel des utilisateurs.

Pour définir les paramètres d’appel d’un utilisateur, celui-ci doit avoir Téléphone Microsoft licence système.

## <a name="use-the-teams-admin-center"></a>Utiliser le Centre Teams’administration de l’équipe

Vous pouvez utiliser le centre Teams d’administration pour configurer le récupérer et la délégation d’appel de groupe pour vos utilisateurs. 

> [!NOTE]
> L’option de configuration des paramètres de forwardage n’est actuellement pas disponible dans le Teams d’administration.

Pour configurer le regroupement d’appels de groupe, vous pouvez :

1. Dans le Teams d’administration, sélectionnez un utilisateur dans **UsersManage** >  (**UtilisateursManage**).

2. Dans la page des détails de l’utilisateur, allez sur **l’onglet** Voix.

3. Sous **Regroupement d’appels de** groupe, **sélectionnez Ajouter des personnes**. 

4. Spécifiez les paramètres du **retard et de la commande d’appel**.

Pour configurer la délégation, sur la même page, allez à **Délégation** d’appel et **sélectionnez Ajouter des personnes**.

## <a name="use-powershell"></a>Utiliser PowerShell

Vous pouvez utiliser PowerShell pour configurer les paramètres de forward et de délégation d’appel pour vos utilisateurs.  Vous utiliserez les cmdlets suivantes, qui sont disponibles dans Teams module PowerShell version 4.0 ou ultérieure :

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - Affiche les paramètres de forwarding d’appel, les délégués et les informations de délégant pour un utilisateur.

- [Set-CsUserCallingSettings - définit](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) les paramètres de forwarding d’appel pour un utilisateur.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) : ajoute un nouveau délégué avec les autorisations d’un utilisateur.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - modifie les autorisations d’un délégué existant.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - supprime un délégué d’un utilisateur.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Afficher les paramètres de forward et de délégation d’appel pour un utilisateur

Pour afficher les paramètres actuels de forward et de délégation d’un utilisateur, utilisez l'Get-CsUserCallingSettings de contrôle, comme illustré dans l’exemple suivant :

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
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

La sortie indique que l’utilisateur1 a configuré une sonnerie simultanée pour les délégués. Les appels sans réponse sont envoyés vers la messagerie vocale au bout de 20 secondes. User2 est défini comme délégué avec toutes les autorisations de délégué.


### <a name="set-call-forward-settings-for-a-user"></a>Définir les paramètres de forward d’appel pour un utilisateur

Pour faire suivre tous les appels de l’utilisateur 1 à l’utilisateur2, utilisez la cmdlet Set-CsUserCallingSettings, comme illustré dans l’exemple suivant : 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Pour faire sonner simultanément tous les délégués pour l’utilisateur 3, utilisez la cmdlet Set-CsUserCallingSettings, comme montré dans l’exemple suivant : 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

L’exemple suivant utilise l'Set-CsUserCallingSettings de la cmdlet pour configurer un groupe d’appels pour user4 avec user5 et user6 en tant que membres. Tous les appels à des membres du groupe sont transmis dans l’ordre défini : 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Pour plus d’exemples, [voir Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Ajouter un délégué d’appel pour un utilisateur

Pour ajouter user2 en tant que délégué pour user1 avec toutes les autorisations autorisées, utilisez l'New-CsUserCallingDelegate, comme montré dans l’exemple suivant : 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Modifier les autorisations de délégué d’appel

Pour modifier les autorisations accordées aux délégués (par exemple, pour ne pas autoriser l’utilisateur2 à effectuer des appels pour l’utilisateur 1), utilisez l'Set-CsUserCallingDelegate cmdlet, comme montré dans l’exemple suivant : 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Supprimer un délégué d’appel pour un utilisateur

Pour supprimer user2 en tant que délégué pour user1, utilisez l'Remove-CsUserCallingDelegate, comme illustré dans l’exemple suivant : 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>Rubriques connexes

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
