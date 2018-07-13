---
title: Exécutez Microsoft Teams dans un environnement virtuel
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/12/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jaym
description: Découvrez comment exécuter Microsoft Teams dans un environnement virtualisé.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: d00ee6a3c14b5a1bb97685124293b13977c323af
ms.sourcegitcommit: 411d59a92ad73555cf39d9c64822b24240b5af8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2018
ms.locfileid: "20328734"
---
<a name="run-microsoft-teams-in-a-virtual-environment"></a>Exécutez Microsoft Teams dans un environnement virtuel
============================================

Cet article décrit les configurations requises et restrictions pour l’utilisation d’équipes dans un environnement virtualisé.

Un environnement VDI (Virtual Desktop Infrastructure) est utilisé dans certaines entreprises pour lesquelles les aspects liés à la sécurité et à la conformité sont particulièrement cruciaux. Les utilisateurs effectuent leur travail sur un bureau virtuel contenant leurs applications de bureau et les fichiers à l’aide des Services Bureau à distance ou une connexion à distance similaire. Étant donné que les équipes sur le bureau virtuel n’a pas été optimisée pour accéder ou utiliser les périphériques audio ou vidéos sur le périphérique l’utilisateur local (sans les logiciels supplémentaires), dans un environnement VDI ont généralement les défis liés à des scénarios tels que l’appel, multimédias appel vidéo, partage d’écran, partage d’application, la co-création et plus. 

> [!NOTE]
> Les organisations peuvent choisir d’exécuter des équipes entièrement dans VDI (à l’aide de l’application Web ou le Client de bureau), mais il est recommandé que les stratégies suivantes soit désactivé, afin que les utilisateurs ne disposent d’une mauvaise expérience dans un environnement virtualisé. Notez qu’il peut prendre un certain temps pour que ces modifications de stratégie propager. Si vous ne voyez pas immédiatement les modifications pour un compte donné, puis réessayez quelques heures. 

## <a name="calling"></a>Appels

Les applets de commande *CsTeamsCallingPolicy* permettent aux administrateurs de contrôler si l’appelant, les options en privé et salles de conversation de groupe sont activés ou non. 


|Nom de la stratégie |Description  |Valeur recommandée  |
|---------|---------|---------|
|AllowPrivateCalling   |Contrôle si l’application d’appel est disponible dans la barre de gauche du client équipes ou non. Détermine également si les utilisateurs voient des options d’appel et appel vidéo dans la conversation privée. |Attribuez à la **valeur False** pour supprimer l’application de l’appel de la barre de gauche et de supprimer les options d’appel et appel vidéo dans la conversation privée. |

### <a name="powershell-instructions"></a>Instructions PowerShell

1.  Lancez PowerShell en tant qu’administrateur.
2.  Se connecter à un connecteur en ligne Skype :<br>
\>> *# Définir le nom d’utilisateur Office 365 et le mot de passe*<br>
\>> *$username = « adresse de messagerie d’administration »*<br>
\>> *$password = « mot de passe » ConvertTo-SecureString - AsPlainText-Force*<br>
\>> *$LiveCred = typename - nouvel objet System.Management.Automation.PSCredential - argumentlist $username, $password*<br><br>
\>> *# Se connecter à Skype en ligne*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred d’informations d’identification*<br>
\>> *Import-PSSession $sfboSession*<br>
3.  Afficher la liste des Options de stratégie de l’appel :<br>
\>> *Get-CsTeamsCallingPolicy*
4.  Recherchez l’option prédéfinie où toutes les stratégies de réunion sont désactivés :<br>
![Capture d’écran de l’option de réunions avec toutes les stratégies de réunion désactivé.](media/virtual-environment-image2.png)
5.  Appliquer l’option « DisallowCalling » prédéfini à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé :<br>
\>> *Grant-CsTeamsMeetingPolicy - PolicyName AllOff-Identity « id de messagerie utilisateur »*

## <a name="meetings"></a>Réunions

Les cmdlets de *CsTeamsMeetingPolicy* permettent aux administrateurs de contrôler le type de réunions par les utilisateurs ou les fonctionnalités auxquels ils peuvent accéder dans une réunion. Il permet également de déterminer comment gérer des réunions avec des utilisateurs anonymes ou externes.

|Nom de la stratégie |Description  |Valeur recommandée  |
|---------|---------|---------|
|AllowPrivateMeetingScheduling    |Détermine si un utilisateur est autorisé à planifier des réunions privées.         |Attribuez à la **valeur False** pour interdire à l’utilisateur de pouvoir planifier des réunions privées.         |
|AllowChannelMeetingScheduling     |Détermine si un utilisateur est autorisé à planifier des réunions de canal.         |Attribuez à la **valeur False** pour interdire à l’utilisateur de pouvoir planifier des réunions de canal.         |
|AllowMeetNow     |Détermine si un utilisateur est autorisé à créer ou démarrer des réunions ad hoc.         |Attribuez à la **valeur False** pour interdire à l’utilisateur de pouvoir démarrer des réunions ad hoc.         |
|ScreenSharingMode     |Détermine le mode dans lequel un utilisateur est autorisé à partager écran dans les appels ou des réunions.         |Définir sur **désactivé** pour empêcher l’utilisateur de partager leurs écrans.         |
|AllowIPVideo     |Détermine si la vidéo est activée dans les réunions ou les appels d’un utilisateur.         |Attribuez à la **valeur False** pour interdire à l’utilisateur de partager leur vidéo.         |
|AllowAnonymousUsersToDialOut     |Détermine si les utilisateurs anonymes sont autorisés à appeler un numéro RTC.         |Attribuez à la **valeur False** pour interdire aux utilisateurs anonymes à partir d’un appel sortant.         |
|AllowAnonymousUsersToStartMeeting     |Détermine si les utilisateurs anonymes peuvent lancer une réunion.         |Attribuez à la **valeur False** pour empêcher l’initialisation d’une réunion.         |
|AllowOutlookAddIn     |Détermine si un utilisateur peut planifier des réunions d’équipes dans le client de bureau Outlook.         |Attribuez à la **valeur False** pour interdire à un utilisateur de la planification des réunions d’équipes dans le client Outlook.         |
|AllowParticipantGiveRequestControl     |Détermine si les participants peuvent demander ou donner le contrôle du partage d’écran.         |Attribuez à la **valeur False** pour empêcher l’utilisateur d’octroyer, demander le contrôle à une réunion.         |
|AllowExternalParticipantGiveRequestControl     |Détermine si les participants externes peuvent demander ou donner le contrôle du partage d’écran.         |Définir sur **False** pour empêcher un utilisateur externe de donner, demander le contrôle à une réunion.         |
|AllowPowerPointSharing     |Détermine si le partage de PowerPoint est autorisé dans les réunions d’un utilisateur.         |Définir sur **True** pour autoriser.<br>Attribuez à la **valeur False** pour interdire à l’utilisateur à partir du partage de fichiers PowerPoint dans une réunion.         |
|AllowWhiteboard     |Détermine si le tableau blanc est autorisée dans les réunions d’un utilisateur.         |Attribuez à la **valeur False** pour interdire l’application de tableau blanc dans une réunion.         |
|AllowTranscription     |Détermine si les légendes en temps réel et/ou postérieures à la réunions et des transcriptions sont autorisées dans les réunions d’un utilisateur.         |Attribuez à la **valeur False** pour interdire la transcription et légendes dans une réunion.         |

### <a name="powershell-instructions"></a>Instructions PowerShell

1.  Lancez PowerShell en tant qu’administrateur.
2.  Se connecter à un connecteur en ligne Skype :<br>
\>> *# Définir le nom d’utilisateur Office 365 et le mot de passe*<br>
\>> *$username = « adresse de messagerie d’administration »*<br>
\>> *$password = « mot de passe » ConvertTo-SecureString - AsPlainText-Force*<br>
\>> *$LiveCred = typename - nouvel objet System.Management.Automation.PSCredential - argumentlist $username, $password*<br><br>
\>> *# Se connecter à Skype en ligne*<br>
\>> *Import-Module SkypeOnlineConnector*<br>
\>> *$sfboSession = New-CsOnlineSession-$LiveCred d’informations d’identification*<br>
\>> *Import-PSSession $sfboSession*
3.  Afficher la liste des Options de la stratégie de réunion :<br>
\>> *Get-CsTeamsMeetingPolicy*
4.  Recherchez l’option prédéfinie où toutes les stratégies de réunion sont désactivés :<br>
![Capture d’écran d’option l'appel toutes les stratégies de réunion désactivé.](media/virtual-environment-image1.png)
5.  Appliquer l’option « AllOff » prédéfini à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé :<br>
\>> *Grant-CsTeamsMeetingPolicy - PolicyName AllOff-Identity « id de messagerie utilisateur »*

##<a name="known-limitations"></a>Limitations connues

Outre le limitations audio et vidéo previosly mentionné, il existe certaines limitations de supplémentaires aux utilisateurs dans des environnements virtualisés peut être confronté :

- **Participation à des réunions créées par d’autres.** Bien que les stratégies ci-dessus empêcher les utilisateurs de créer des réunions, ils seront toujours en mesure de participer à des réunions envoyées par les autres utilisateurs. Dans ces réunions, sa capacité à partager une vidéo, utilisez le tableau blanc et autres fonctionnalités dépend de si l’administrateur désactivés ou non.

- **Problèmes liés au contenu mis en cache.** Si les équipes s’exécute dans l’environnement virtuel n’est pas conservée (les données sont nettoyées à la fin de chaque session de l’utilisateur), les utilisateurs peuvent remarquer une dégradation des performances en raison du client que vous ayez à nouveau télécharger tout le contenu, quelle que soit ou non l’utilisateur accéder à la même contenu dans une session précédente. Cet impact sur les performances peut être atténué en utilisant des solutions de cache itinérants, telles que celles fournies par FSLogix.

Une fois équipes a été optimisé pour une utilisation dans des environnements d’ordinateurs virtuels, administrateurs peuvent rétablir ces stratégies et permettre aux utilisateurs d’utiliser des équipes comme ils le feriez normalement.

         
        
        
        
        
        
        
        
        
        
        


