---
title: Prise en charge de l’utilisation des fonctionnalités SEFAUtil dans Skype PowerShell dans Skype Entreprise Server 2019
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
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Résumé : Découvrez comment utiliser PowerShell pour obtenir la fonctionnalité SEFAUtil dans Skype Entreprise Server 2019 après l’installation de la mise à jour cumulative 1.'
ms.openlocfilehash: 07d05ef1687fa9ca14f7e90108ae8b5c0e7e3bb9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676536"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utilisation de la fonctionnalité SEFAUtil via PowerShell dans Skype Entreprise Server 2019

SEFAUtil (activation de fonctionnalité d’extension secondaire) permet aux administrateurs Skype Entreprise Server et aux agents du support technique de configurer les paramètres de sonnerie de délégué, de transfert d’appel et de prise d’appel de groupe pour le compte de Skype Entreprise Server utilisateurs. SEFAUtil permet également aux administrateurs d’interroger les paramètres de routage des appels pour un utilisateur particulier.

Après avoir installé la mise à jour cumulative de juillet 2019 Skype Entreprise Server, les fonctionnalités suivantes qui étaient disponibles uniquement via SEFAUtil seront également disponibles dans Skype PowerShell :

- [Paramètres de transfert d’appel](#call-forwarding-settings)
- [Paramètres de délégation](#delegation-settings)
- [Membres de l’équipe et paramètres associés](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Paramètres de transfert d’appel

Les administrateurs peuvent modifier les paramètres de transfert d’appel à l’aide des commandes suivantes dans PowerShell :

```powershell
Get-CsUserCallForwardingSettings -Identity <UserIdParameter>
```

Cette commande retourne les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche la même chose à l’écran.

```powershell
Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]...
```

Cette commande modifie les paramètres de transfert d’appel de l’utilisateur spécifié. Cette commande retourne les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche la même chose à l’écran. Si la commande échoue, un message d’erreur approprié s’affiche.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Cette commande désactive les paramètres de transfert d’appel de l’utilisateur (nous montrons deux exemples de paramètres différents ici).

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

Cette commande modifie les paramètres de transfert d’appel de l’utilisateur.

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]
```

```powershell
Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]
```

Cette commande modifie les paramètres d’anneau simultanés (là encore, avec deux exemples de paramètres, l’un pour la messagerie vocale sans réponse et le second étant sans réponse à l’autre).

## <a name="delegation-settings"></a>Paramètres de délégation

Les administrateurs peuvent modifier les paramètres de délégation à l’aide de la commande suivante dans PowerShell :

```powershell
Get-CsuserDelegates -Identity <UserIdParameter>
```

Cette commande retourne un objet de liste de délégués et affiche la liste des délégués de l’utilisateur spécifié. Si la commande échoue, un message d’erreur approprié s’affiche.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]
```

Cette commande modifie les paramètres de délégation de l’utilisateur spécifié, retourne un objet de liste de délégués et affiche la liste des délégués. Si la commande échoue, un message d’erreur approprié s’affiche.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]
```

Cette commande ajoute ou supprime un délégué.

```powershell
Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]
```

Cette commande définit une liste de délégués pour des délégués spécifiques.

## <a name="team-members-and-related-settings"></a>Membres de l’équipe et paramètres associés

Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de la commande suivante dans PowerShell :

```powershell
Get-CsUserTeamMembers -Identity <UserIdParameter>
```

Cette commande retourne un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran. Si la commande échoue, un message d’erreur approprié s’affiche.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]
```

Cette commande modifie la liste des membres de l’équipe de l’utilisateur spécifié, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran. Si la commande échoue, un message d’erreur approprié s’affiche.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]
```

Cette commande ajoute ou supprime des membres de l’équipe.

```powershell
Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]
```

Cette commande définit une liste d’équipes pour des membres spécifiques.

## <a name="more-information"></a>Informations supplémentaires

Pour les déploiements locaux, les applets de commande introduites dans cette fonctionnalité ne peuvent être exécutées que par les membres des groupes suivants, selon le niveau d’accès spécifié ci-dessous :

- CsAdministrator : obtenir et définir pour toutes les applets de commande
- CsVoiceAdministrator - Obtenir et définir pour toutes les applets de commande
- CsHelpDesk - Obtenir pour toutes les applets de commande

Pour plus d’informations sur ces rôles d’administrateur, consultez [Créer des administrateurs Skype Entreprise Server Panneau de configuration](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L’administrateur peut accéder à ces applets de commande en se connectant directement ou à distance à un ordinateur serveur.
Pour un déploiement hybride, Skype Entreprise administrateurs doivent être en mesure d’appeler Get et Set pour toutes les applets de commande. Pour plus d’informations sur la liste complète des rôles, consultez [À propos des rôles d’administrateur](/microsoft-365/admin/add-users/about-admin-roles).

> [!NOTE]
> La découverte automatique du serveur doit être activée. Aucune exigence de licence supplémentaire ne sera introduite pour l’utilisation des applets de commande.
