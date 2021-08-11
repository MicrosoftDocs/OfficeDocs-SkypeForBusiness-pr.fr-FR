---
title: Prise en charge de l’utilisation de la fonctionnalité SEFAUtil dans PowerShell Skype Entreprise Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Découvrez comment utiliser PowerShell pour obtenir la fonctionnalité SEFAUtil dans Skype Entreprise Server 2019 après l’installation de la mise à jour cumulative 1.'
ms.openlocfilehash: afb0c34afedde91bac40ee90b155809ed3c2b557d88608028b77e0835eb9661d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277619"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utilisation de la fonctionnalité SEFAUtil via PowerShell Skype Entreprise Server 2019

SEFAUtil (Secondary Extension Feature Activation) permet aux administrateurs Skype Entreprise Server et aux agents du service d’aide de configurer les paramètres de sonnerie de délégué, de transfert d’appel et de prise d’appel de groupe au nom d’un utilisateur Skype Entreprise Server. Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. Après avoir installé la mise à jour cumulative de juillet Skype Entreprise Server 2019, les fonctionnalités suivantes qui ne peuvent actuellement être gérées que par le biais de SEFAUtil sont également gérables via PowerShell :

- [Paramètres de forwarding d’appel](#call-forwarding-settings)
- [Paramètres de délégation](#delegation-settings)
- [Membres de l’équipe et paramètres associés](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Paramètres de forwarding d’appel

Les administrateurs peuvent modifier les paramètres de forwarding d’appel à l’aide de l’cmdlet suivante dans PowerShell :

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Cette cmdlet renvoie les paramètres de forwarding d’appel de l’utilisateur spécifié en tant qu’objet et affiche la même chose à l’écran.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Cette cmdlet modifie les paramètres de forwarding d’appel de l’utilisateur spécifié. Cette cmdlet renvoie les paramètres de forwardage d’appel de l’utilisateur spécifié en tant qu’objet et affiche la même chose à l’écran, en cas de réussite. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette cmdlet désactive les paramètres de forwardage d’appel de l’utilisateur (nous vous présentons deux exemples de paramètres différents ici).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette cmdlet modifie les paramètres de forwardage d’appel de l’utilisateur.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Cette cmdlet modifie les paramètres de sonnerie simultanée (là encore, avec deux exemples de paramètres, l’un pour la messagerie vocale sans réponse et l’autre pour les autres).

## <a name="delegation-settings"></a>Paramètres de délégation

Les administrateurs peuvent modifier les paramètres de délégation à l’aide de l’cmdlet suivante dans PowerShell :

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Cette cmdlet renvoie un objet de liste de délégués et affiche la liste des délégués de l’utilisateur spécifié, en cas de réussite. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Cette cmdlet modifie les paramètres de délégation de l’utilisateur spécifié, renvoie un objet de liste de délégués et affiche la liste des délégués, en cas de réussite. En cas d’échec, un message d’erreur approprié s’affiche. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Cette cmdlet ajoute ou supprime un délégué.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Cette cmdlet définit une liste de délégués pour des délégués spécifiques.

## <a name="team-members-and-related-settings"></a>Membres de l’équipe et paramètres associés

Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’cmdlet suivante dans PowerShell :

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Cette cmdlet renvoie un objet qui contient la liste des membres de l’équipe et l’affiche à l’écran, en cas de réussite. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Cette cmdlet modifie la liste des membres de l’équipe de l’utilisateur spécifié, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Cette cmdlet ajoute ou supprime des membres de l’équipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Cette cmdlet définit une liste d’équipes pour des membres spécifiques.

## <a name="more-information"></a>Informations supplémentaires

Pour les déploiements locaux, les cmdlets introduites dans cette fonctionnalité peuvent uniquement être exécutés par les membres des groupes suivants, selon le niveau d’accès spécifié ci-dessous :

- CsAdministrator : obtenir et définir pour toutes les cmdlets
- CsVoiceAdministrator - Obtenir et définir pour toutes les cmdlets
- CsHelpDesk - Obtenir pour toutes les cmdlets

Pour plus d’informations sur ces rôles d’administrateur, [voir Create Skype Entreprise Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L’administrateur peut accéder à ces cmdlets en se connectant directement ou à distance à un ordinateur serveur.
Pour un déploiement hybride, Skype Entreprise administrateurs doivent être en mesure d’appeler Get et Set pour toutes les cmdlets. Pour plus d’informations sur la liste complète des rôles, voir [à propos des rôles d’administrateur.](/microsoft-365/admin/add-users/about-admin-roles)

> [!NOTE]
> La découverte automatique du serveur doit être activée. Aucune exigence de licence supplémentaire n’est introduite pour l’utilisation des cmdlets.
