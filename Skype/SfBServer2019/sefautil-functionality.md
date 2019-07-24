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
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé: Découvrez comment utiliser PowerShell pour obtenir le fonctionnement de SEFAUtil dans Skype entreprise Server 2019 après l’installation de la mise à jour cumulative 1.'
ms.openlocfilehash: 1c5d8d32c1b7b1b988b0ab39c79e4a7f40752875
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821323"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a>Utiliser la fonctionnalité SEFAUtil via PowerShell dans Skype entreprise Server 2019

SEFAUtil (l’activation de la fonctionnalité d’extension secondaire) permet aux administrateurs et aux techniciens du support technique de Skype entreprise de configurer la sonnerie de délégué, le transfert d’appel et les paramètres de cueillette de groupe pour le compte d’un utilisateur de Skype entreprise Server. L’outil permet également aux administrateurs d’interroger les paramètres de routage des appels publiés pour un utilisateur particulier. Après l’installation de cette mise à jour, les fonctionnalités suivantes qui peuvent être gérées uniquement via SEFAUtil peuvent également être gérées via PowerShell:

- [Paramètres de transfert d’appel](#call-forwarding-settings)
- [Paramètres de délégation](#delegation-settings)
- [Membres de l’équipe et paramètres associés](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a>Paramètres de transfert d’appel

Les administrateurs peuvent modifier les paramètres de transfert d’appel à l’aide de l’applet de commande suivante dans PowerShell:

- `Get-CsUserForwardingSettings -Identity <UserIdParameter>`

Cette cmdlet renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même écran sur l’écran.

- `Set-CsUserForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

Cette applet de demande modifie les paramètres de transfert d’appel de l’utilisateur spécifié. Ce cmdlet renvoie les paramètres de transfert d’appel de l’utilisateur spécifié en tant qu’objet et affiche le même écran, en cas de succès. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette applet de demande désactive les paramètres de transfert d’appel de l’utilisateur (nous affichons deux exemples de paramètres différents ici).

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

Cette applet de demande modifie les paramètres de transfert d’appel de l’utilisateur.

- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

Cette applet de cmdlet modifie les paramètres de SimulRing (de nouveau, avec deux exemples de paramètres: un pour sans réponse à la boîte vocale et le second en absence de réponse à d’autres).

## <a name="delegation-settings"></a>Paramètres de délégation

Les administrateurs peuvent modifier les paramètres de délégation en utilisant l’applet de commande suivante dans PowerShell:

- `Get-CsuserDelegates -Identity <UserIdParameter>`

Cette cmdlet renvoie un objet de liste de délégués et affiche la liste de délégués de l’utilisateur spécifié, en cas de succès. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

Cette applet de demande modifie les paramètres de délégation de l’utilisateur spécifié, renvoie un objet de liste délégués et affiche la liste des délégués, en cas de succès. En cas d’échec, un message d’erreur approprié s’affiche. 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

Cette applet de cmdlet ajoute ou supprime un délégué.

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

Cette applet de cmdlet définit une liste de délégués pour des délégués spécifiques.

## <a name="team-members-and-related-settings"></a>Membres de l’équipe et paramètres associés

Les administrateurs peuvent modifier les membres de l’équipe et les paramètres associés à l’aide de l’applet de commande suivante dans PowerShell:

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

Cette cmdlet renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de succès. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

Cette applet de demande modifie la liste des membres de l’équipe spécifiée, renvoie un objet qui contient la liste des membres de l’équipe et affiche l’objet à l’écran, en cas de succès. En cas d’échec, un message d’erreur approprié s’affiche.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

Cette applet de cmdlet ajoute ou supprime des membres de l’équipe.

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

Cette applet de cmdlet définit une liste d’équipes pour des membres spécifiques.

## <a name="more-information"></a>Plus d’informations

Pour les déploiements sur site, les applets de commande introduites dans cette fonctionnalité ne peuvent être exécutées que par les membres des groupes suivants, selon le niveau d’accès indiqué ci-dessous:

- CsAdministrator – Get et Set pour toutes les applets de cmdlet
- CsVoiceAdministrator-Get et Set pour toutes les applets de cmdlet
- CsHelpDesk-obtenir toutes les applets de cmdlet

Pour plus d’informations sur ces rôles d’administrateur, reportez-vous à la rubrique [création d’administrateurs du panneau de configuration Skype entreprise Server](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md). L’administrateur peut accéder à ces applets de commande en se connectant directement ou à distance à un ordinateur serveur.
Pour un déploiement hybride, les administrateurs Skype entreprise doivent pouvoir appeler Get et Set pour toutes les applets de méthode. Pour plus d’informations sur la liste complète des rôles, voir [à propos des rôles d’administrateur Office 365](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)

> [!NOTE]
> La découverte automatique du serveur doit être activée. Aucun besoin de licence supplémentaire n’est introduit pour l’utilisation des cmdlets.
