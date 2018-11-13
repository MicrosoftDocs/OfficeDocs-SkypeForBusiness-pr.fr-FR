---
title: Configurer des événements en temps réel dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Découvrez comment configurer les paramètres de l’événement en direct dans Microsoft Teams, y compris la définition de la visibilité des participants et des options d’enregistrement.
appliesto:
- Microsoft Teams
ms.openlocfilehash: fcd9bc02257d67f1af959d2158042ea73545a25e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296104"
---
# <a name="configure-live-events-in-microsoft-teams"></a>Configurer des événements en temps réel dans Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

## <a name="set-up-event-support-link"></a>Configurer le lien de prise en charge des événements
Il s’agit le lien qui s’affichera pour les participants de l’événement en direct. 

Dans Windows PowerShell, exécutez la commande suivante :
```
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
## <a name="configure-attendee-visibility-options"></a>Configurer les options de visibilité de participant
Ainsi, événement live organisateurs créer des événements avec visibilité attendee approprié.

|**Valeurs**  |**Comportement**  |
|---------|---------|
|Tout le monde     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : Public, tout le monde dans la société et des personnes spécifiques. |
|EveryoneInCompany     |L’utilisateur dispose d’une option pour créer des événements en temps réel avec la visibilité attendee suivantes : tout le monde dans la société et des personnes spécifiques. L’utilisateur ne peut pas créer des événements en temps réel qui peuvent être contrôlés par des utilisateurs anonymes.|
|InvitedUsers |L’utilisateur peut uniquement créer des événements en temps réel qui sont limitées à des personnes spécifiques entré par l’organisateur de l’événement. L’utilisateur ne peut pas créer des événements live avec Public et tout le monde dans l’authentification de la société. |

Utilisez le paramètre BroadcastAttendeeVisibility dans TeamsMeetingBroadcastPolicy dans PowerShell pour contrôler si les utilisateurs peuvent planifier la diffusion des événements qui peuvent être surveillés par les participants anonymes. 

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui a la valeur EveryoneInCompany par défaut. 
 
Dans Windows PowerShell, exécutez ce qui suit pour permettre aux utilisateurs de créer des événements anonyme dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastAttendeeVisibility Everyone  
```
## <a name="configure-recording-options"></a>Configurer les options d’enregistrement
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’administrateurs au contrôle si les événements live sont toujours enregistrées, jamais enregistré, ou si l’organisateur de l’événement peut décider d’enregistrer l’événement ou non.  

|**Valeurs**  |**Comportement**  |
|---------|---------|
|Toujours activé |Les événements live organisées par cet utilisateur sont toujours enregistrées. L’utilisateur n’est pas une option pour remplacer. Si l’événement live est enregistré, les membres de l’équipe des événements sont en mesure de télécharger l’enregistrement après l’événement et les participants peuvent suivre l’événement après l’événement. |
|AlwaysDisabled |Les événements live organisées par cet utilisateur ne sont jamais enregistrées. L’utilisateur n’est pas une option pour remplacer. Si l’événement live est enregistré, aucun enregistrement n’est créé pour les membres de l’équipe d’événement et les participants ne peuvent pas voir l’événement après l’avoir sur. |
|UserOverride |Utilisateur peut décider si l’événement live est enregistré afin qu’un fichier d’enregistrement peut être créé pour les membres de l’équipe d’événement et les participants peuvent suivre l’événement après l’événement. |

Utilisez le paramètre *BroadcastRecordingMode* dans **TeamsMeetingBroadcastPolicy** dans PowerShell pour contrôler des options des événements live créés par l’organisateur de l’événement live d’enregistrement.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour mettre à jour le mode d’enregistrement de la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -BroadcastRecordingMode AlwaysDisabled 
```
## <a name="configure-real-time-transcription-and-translation-in-teams-live-events-coming-soon"></a>Configurer la transcription en temps réel et traduction dans événements live équipes (bientôt disponible)
> [!NOTE]
> Cette option ne s’applique aux événements qui utilisent la méthode de production de démarrage rapide uniquement.

Cela permet d’organisateurs d’événement live activer les légendes en temps réel et translation pour les participants de l’événement en direct. 

Utilisez le paramètre *AllowBroadcastTranscription* dans **TeamsMeetingBroadcastPolicy** dans PowerShell pour contrôler si les participants direct sera en mesure de voir la transcription et traduction. Pour plus d’informations sur la gestion des **TeamsMeetingBroadcastPolicy** avec Office 365 PowerShell ici.  

Sauf si vous avez assigné une stratégie personnalisée pour les utilisateurs, les utilisateurs obtiennent la stratégie globale, qui possède la transcription et traduction désactivée par défaut.

Dans Windows PowerShell, exécutez l’applet de commande suivante pour activer la transcription et traduction sur des participants de l’événement dans la stratégie globale :
```
Set-CsTeamsMeetingBroadcastPolicy -Identity Global -AllowBroadcastTranscription $true 
```
## <a name="administrative-tools"></a>Outils d’administration 
Bien que Microsoft directement aux contrôles de tous les centres de données Office 365 en ligne et est chargé de performances globales du système, il peut contrôler qu’une partie des éléments qui associent pour fournir l’expérience pour les utilisateurs d’Office 365. Les entreprises se sont responsables pour les connexions réseau vers les centres de données, le réseau du client étendu (WAN), et du client réseau local (LAN). En outre, ils sont chargés de périphériques de l’utilisateur et leur configuration.Ils sont également chargés de gérer les licences requises par l’utilisateur pour n’importe quelle fonctionnalité souhaitée, y compris, mais non limité à la possibilité de gérer ces fonctionnalités, pour tant que l’utilisateur a besoin d’accéder à la fonctionnalité.

Clients pouvant utiliser les outils suivants pour gérer un grand nombre de tâches associées d’équipes événements en direct.
- [Centre d’administration Microsoft Office 365](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_Office365admincenterl)
- [Microsoft Teams et Skype pour le centre d’administration Business en ligne](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_ExchangeAdministrationCenter)
- [Centre d’administration de Microsoft Stream](https://stream.microsoft.com)
- [À distance Windows PowerShell](https://technet.microsoft.com/library/exchange-online-administration-and-management.aspx?f=255&MSPPError=-2147217396#BKMK_RemoteWindowsPowerShell)

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?
Lorsqu’il s’agit de Windows PowerShell, il des informations supplémentaires sur la gestion des utilisateurs et les utilisateurs autorisés ou non autorisés. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype pour Business Online à l’aide d’un point unique d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
 - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
 - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l’utilisation du centre d’administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
 - [Meilleures méthodes de gestion d’Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
 - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
 - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
