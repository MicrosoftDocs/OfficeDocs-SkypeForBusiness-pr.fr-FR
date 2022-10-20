---
title: Mode partage de lignes dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Découvrez la fonctionnalité d’apparence de ligne De partage dans Microsoft Teams.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614096"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Mode partage de lignes dans Microsoft Teams

L’apparence de ligne partagée permet à un utilisateur de choisir un délégué pour répondre ou gérer les appels en son nom. Cette fonctionnalité est utile si un utilisateur dispose d’un assistant administratif qui gère régulièrement les appels de l’utilisateur. Dans le contexte de l’apparence de ligne partagée, un responsable est une personne qui autorise un délégué à passer ou recevoir des appels en son nom. Un délégué peut passer ou recevoir des appels au nom du délégant.

> [!IMPORTANT]
> Cette fonctionnalité est disponible uniquement en mode de déploiement Teams Uniquement. Pour plus d’informations sur les modes de déploiement Teams, consultez [Comprendre Microsoft Teams et Skype Entreprise coexistence et interopérabilité](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licence requise

Les responsables et les délégués doivent disposer d’une licence système téléphonique avec connectivité RTC (forfait d’appels, connexion d’opérateur ou routage direct). L’expérience de ligne partagée fait partie de la délégation et est incluse avec le système téléphonique. Pour plus d’informations sur les licences, consultez la [description du service Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="shared-line-appearance-feature-availability"></a>Disponibilité des fonctionnalités d’apparence de ligne partagée

L’apparence de ligne partagée est actuellement prise en charge par les applications et appareils suivants.

| Fonctionnalité | Bureau Teams | Application Mac Teams | Teams Web App (Edge) |Application mobile iOS/Android Teams | Téléphone IP Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurer la délégation | Oui | Oui | Oui | Non | Oui |
| Recevoir des appels au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un numéro de téléphone au nom d’un autre | Oui | Oui | Oui | Oui | Oui |
| Appeler un utilisateur Teams pour le compte d’un autre | Oui | Oui | Oui | Oui | Oui |
| Voir la vue déléguée des lignes partagées | Oui | Oui | Oui | Non | Oui |
| Voir la vue déléguée des activités d’appel du responsable | Oui | Oui | Oui | Non | Oui |
| Voir la vue gestionnaire des délégués | Oui | Oui | Oui | Non | Oui |
| Le délégué ou le responsable peut conserver ou reprendre | Oui | Oui | Oui | Non | Oui |

## <a name="limitations"></a>Limites

Les gestionnaires peuvent ajouter jusqu’à 25 délégués et les délégués peuvent avoir jusqu’à 25 gestionnaires. Il n’existe aucune limite au nombre de relations de délégation qui peuvent être créées dans un locataire. 
 
Si le délégateur et le délégué ne se trouvent pas dans le même emplacement géographique, le fournisseur RTC doit autoriser l’ID d’appelant à s’afficher à partir d’un autre emplacement géographique pour un appel délégué. 

La configuration de délégation circulaire n’est pas autorisée. Si les utilisateurs délégués ont également des délégations entre eux, ils ne pourront voir que leur délégation et non la délégation initiale.

## <a name="enable-delegation-and-shared-line-appearance"></a>Activer la délégation et l’apparence de ligne partagée

Vous activez la délégation à l’aide du paramètre **AllowDelegation TeamsCallingPolicy** . Vous pouvez utiliser le Centre d’administration Teams ou Teamms PowerShell. 

Lorsqu’il est activé, l’utilisateur final peut configurer ses relations de délégation directement dans Teams. 

> [!IMPORTANT]
> Lorsque vous désactivez la délégation pour un utilisateur, vous devez également nettoyer les relations de délégation pour cet utilisateur dans le Centre d’administration Teams afin d’éviter un routage d’appel incorrect.

## <a name="use-teams-admin-center"></a>Utiliser le Centre d’administration Teams

Pour configurer la délégation et l’apparence de ligne partagée à l’aide du Centre d’administration Teams, consultez [Configurer les paramètres d’appel pour vos utilisateurs](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Utiliser PowerShell

Pour configurer la délégation et l’apparence de ligne partagée à l’aide de Teams PowerShell, utilisez les applets de commande suivantes :

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>Exemples

Dans l’exemple suivant, user2@contoso.com est ajouté en tant que délégué de user1@contoso.com disposant des autorisations nécessaires pour passer et recevoir un appel au nom de l’utilisateur1, et pour modifier les paramètres des autres délégués :

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

Dans l’exemple suivant, le délégué user2@contoso.com n’est plus autorisé à passer des appels pour le compte de l’utilisateur1 :

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

Dans l’exemple suivant, user2@contoso.com est supprimé en tant que délégué de user1@contoso.com :

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>Plus d’informations

[Partager une ligne téléphonique avec un délégué](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Stratégie d’appel Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
