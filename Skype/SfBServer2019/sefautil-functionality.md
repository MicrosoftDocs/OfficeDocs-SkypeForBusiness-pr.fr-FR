---
title: Prise en charge de l’utilisation de la fonctionnalité SEFAUtil dans PowerShell dans Skype entreprise Server 2019
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
description: 'Résumé : Découvrez comment utiliser PowerShell pour obtenir la fonctionnalité SEFAUtil dans Skype entreprise Server 2019 après avoir installé la mise à jour cumulative 1.'
ms.openlocfilehash: 24040a3da5dc2549996463078a55324f3fc03657
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232555"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utilisation de la fonctionnalité SEFAUtil via PowerShell dans Skype entreprise Server 2019

SEFAUtil (option d’activation secondaire) permet aux administrateurs de Skype entreprise Server et aux agents du support technique de configurer la sonnerie des délégués, le transfert d’appels et les paramètres de prise d’appel de groupe pour le compte d’un utilisateur de Skype entreprise Server. Cet outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. Après avoir installé la mise à jour cumulative de Skype entreprise Server 2019 juillet, les fonctionnalités suivantes, qui peuvent actuellement être gérées uniquement via SEFAUtil, seront également gérables via PowerShell :

- [Paramètres de transfert d’appel](#call-forwarding-settings)
- [Paramètres de délégation](#delegation-settings)
- [Membres de l’équipe et paramètres associés](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Paramètres de transfert d’appel

Les administrateurs peuvent modifier les paramètres de transfert d’appel à l’aide de l’applet de commande suivante dans PowerShell :

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

Cette applet de commande renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même sur l’écran.

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Cette applet de commande modifie les paramètres de transfert d’appel de l’utilisateur spécifié. Cette applet de commande renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même sur l’écran, en cas de réussite. En cas de défaillance, un message d’erreur approprié s’affiche.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette applet de commande désactive les paramètres de transfert d’appel de l’utilisateur (nous affichons deux exemples de paramètres différents ici).

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette applet de commande modifie les paramètres de transfert d’appel de l’utilisateur.

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Cette applet de commande modifie les paramètres sonnerie simultanée (encore une fois, avec deux exemples de paramètres : un pour les messages sans réponse à la messagerie vocale et le second n’a pas répondu à d’autres).

## <a name="delegation-settings"></a>Paramètres de délégation

Les administrateurs peuvent modifier les paramètres de délégation à l’aide de l’applet de commande suivante dans PowerShell :

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Cette applet de commande renvoie un objet de liste de délégués et affiche la liste de délégués de l’utilisateur spécifié, en cas de réussite. En cas de défaillance, un message d’erreur approprié s’affiche.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Cette applet de commande modifie les paramètres de délégation de l’utilisateur spécifié, renvoie une liste d’objets de délégués et affiche la liste des délégués en cas de réussite. En cas de défaillance, un message d’erreur approprié s’affiche. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Cette applet de commande ajoute ou supprime un délégué.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Cette applet de commande définit une liste de délégués à des délégués spécifiques.

## <a name="team-members-and-related-settings"></a>Membres de l’équipe et paramètres associés

Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’applet de commande suivante dans PowerShell :

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Cette applet de commande renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite. En cas de défaillance, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Cette applet de commande modifie la liste des membres de l’équipe spécifiée, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de réussite. En cas de défaillance, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Cette applet de commande ajoute ou supprime des membres de l’équipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Cette applet de commande définit une liste d’équipes sur des membres spécifiques.

## <a name="more-information"></a>Plus d’informations

Pour les déploiements locaux, les applets de commande introduites dans cette fonctionnalité ne peuvent être exécutées que par les membres des groupes suivants, selon le niveau d’accès spécifié ci-dessous :

- CsAdministrator – obtenir et définir pour toutes les cmdlets
- CsVoiceAdministrator-Get et Set pour toutes les cmdlets
- CsHelpDesk-Get pour toutes les cmdlets

Pour plus d’informations sur ces rôles d’administrateur, voir [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L’administrateur peut accéder à ces applets de commande en ouvrant directement ou à distance une session sur un ordinateur serveur.
Pour un déploiement hybride, les administrateurs Skype entreprise doivent pouvoir appeler Get et Set pour toutes les cmdlets. Pour plus d’informations sur la liste complète des rôles, consultez la rubrique [à propos des rôles d’administrateur](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> La découverte automatique de serveur doit être activée. Aucune autre exigence en matière de licences ne sera introduite pour l’utilisation des applets de commande.
