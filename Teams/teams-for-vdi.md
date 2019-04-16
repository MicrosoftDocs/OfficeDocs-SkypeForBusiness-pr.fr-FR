---
title: Équipes pour l’Infrastructure de bureau virtualisé
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Découvrez comment exécuter Microsoft Teams dans un environnement virtualisé Desktop Infrastructure (VDI).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c351e0cefc5e4de4ff74a175af4dee064bf96f3f
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869829"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Équipes pour l’Infrastructure de bureau virtualisé

Cet article décrit les exigences et les limitations de l’utilisation de Microsoft Teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>What ' s VDI ?

Infrastructure VDI (Virtual Desktop) est la technologie de virtualisation qui héberge un système d’exploitation et des applications sur un serveur dans un centre de données centralisé. Cela permet une expérience entièrement personnalisée aux utilisateurs avec une source centralisée entièrement sécurisée et de conformité. 
 
Actuellement, les équipes dans un environnement virtualisé est disponible avec prise en charge des fonctionnalités de collaboration et de conversation avec un ordinateur dédié de virtualisé permanente (VM). Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article. 

## <a name="teams-requirements"></a>Configuration requise des équipes

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Définir des stratégies pour désactiver l’appel et fonctionnalités dans les équipes de réunion

Les équipes appelant et l’expérience de réunion n’est pas optimisé pour un environnement VDI (bientôt disponible). Nous vous recommandons de que définir des stratégies de niveau utilisateur pour désactiver l’appel et fonctionnalités dans les équipes de réunion.

Vous pouvez toujours choisir d’exécuter des équipes entièrement dans VDI à l’aide de l’application de bureau équipes ou le web app. Toutefois, nous vous recommandons de définir les stratégies d’éviter de compromettre l’expérience utilisateur.  

Elle peut prendre un certain temps (quelques heures) pour propager les modifications de stratégie. Si vous ne voyez pas immédiatement les modifications pour un compte donné, essayez à nouveau dans quelques heures.

> [!NOTE]
> Lors de l’appel des équipes et des réunions sont optimisées pour une utilisation dans des environnements de bureau virtuels, vous pouvez restaurer ces stratégies et permettre aux utilisateurs d’utiliser des équipes comme ils le feriez normalement. 

#### <a name="calling"></a>Appels

Utilisez les applets de commande **CSTeamsCallingPolicy** pour contrôler si les utilisateurs sont autorisés à utiliser l’appel et options d’appel en privé et conversations de groupe. Voici la liste des paramètres de stratégie et les valeurs recommandées.

|Nom de la stratégie  |Description |Valeur recommandée  |
|---------|---------|---------|
|AllowCalling    |Interopérabilité de contrôles capacités d’appel. Permet d’activer cette fonctionnalité Skype pour les utilisateurs professionnels pour que les appels en tête-à-tête avec les utilisateurs des équipes et inversement.         |La valeur False pour empêcher les appels Skype pour les utilisateurs professionnels d’arrivée dans les équipes.          |
|AllowPrivateCalling     | Contrôle si l’application d’appel est disponible dans la barre d’application sur le côté gauche du client équipes et si les utilisateurs voient appel et vidéo dans la conversation privée, les options d’appel         |La valeur False pour supprimer l’application de l’appel de la barre d’application sur le côté gauche des équipes et de supprimer les options d’appel appel et la vidéo dans la conversation privée.          |

#### <a name="create-and-assign-a-calling-policy"></a>Créer et affecter une stratégie d’appel

1. Démarrer une session Windows PowerShell en tant qu’administrateur.
2. Se connecter au connecteur Skype en ligne.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Afficher la liste des options de stratégie d’appel.

       Get-CsTeamsCallingPolicy
 
4. Recherchez l’option stratégie intégrée où toutes les stratégies d’appel sont désactivées. Il se présente comme suit.
   
        Identity                        : Tag:DisallowCalling
        AllowCalling                    : False
        AllowPrivateCalling             : False
        AllowVoicemail                  : False
        AllowCallGroups                 : False
        AllowDelegation                 : False
        AllowUserControl                : False
        AllowCallForwardingToUser       : False
        AllowCallForwardingToPhone      : False
        PreventTollBypass               : False

5. Appliquer l’option de stratégie intégrée DisallowCalling à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Pour plus d’informations sur les équipes appelant des stratégies, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Réunions

Utilisez les applets de commande **CsTeamsMeetingPolicy** pour contrôler le type de réunions que les utilisateurs peuvent créer, les fonctionnalités auxquels ils peuvent accéder dans une réunion et les fonctionnalités de réunion qui sont accessibles aux utilisateurs anonymes et externes. Voici la liste des paramètres de stratégie et les valeurs recommandées.

|Nom de la stratégie |Description|Valeur recommandée                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Détermine si un utilisateur est autorisé à planifier des réunions privées.| La valeur False pour empêcher l’utilisateur de pouvoir planifier des réunions privées.  |
|AllowChannelMeetingScheduling  | Détermine si un utilisateur est autorisé à planifier des réunions de canal. | La valeur False pour empêcher l’utilisateur de pouvoir planifier des réunions de canal.                       |
|AllowMeetNow |Détermine si un utilisateur est autorisé à créer ou démarrer des réunions ad hoc.              |  Définissez cette valeur False pour interdire à l’utilisateur de pouvoir démarrer des réunions ad hoc.                     |
|ScreenSharingMode | Détermine le mode dans lequel un utilisateur est autorisé à partager leur écran dans les appels ou des réunions. | La valeur désactivé pour empêcher l’utilisateur de partager leurs écrans                          |
|AllowIPVideo |Détermine si la vidéo est activée dans les réunions ou les appels d’un utilisateur.                  |    La valeur False pour empêcher l’utilisateur de partager leur vidéo                                         |
| AllowAnonymousUsersToDialOut | Détermine si les utilisateurs anonymes sont autorisés à appeler un numéro RTC. | La valeur False pour empêcher les utilisateurs anonymes à partir d’un appel sortant                                  |
| AllowAnonymousUsersToStartMeeting | Détermine si les utilisateurs anonymes peuvent démarrer une réunion.     |  La valeur False pour empêcher les utilisateurs de démarrer une réunion                                            |
| AllowOutlookAddIn |Détermine si un utilisateur peut planifier des réunions d’équipes dans le client de bureau Outlook.| La valeur False pour empêcher un utilisateur de planifier des réunions d’équipes dans le client de bureau Outlook|
| AllowParticipantGiveRequestControl|Détermine si les participants peuvent demander ou donner le contrôle du partage d’écran.| La valeur False pour empêcher l’utilisateur d’octroyer et demander le contrôle à une réunion    |
| AllowExternalParticipantGiveRequestControl | Détermine si les participants externes peuvent demander ou donner le contrôle du partage d’écran.| La valeur False pour empêcher un utilisateur externe de donner, demander le contrôle à une réunion|
|AllowPowerPointSharing|Détermine si le partage de PowerPoint est autorisé dans les réunions d’un utilisateur. |La valeur False pour empêcher un utilisateur à partir du partage de fichiers PowerPoint dans une réunion  |
|AllowWhiteboard | Détermine si le tableau blanc est autorisée dans les réunions d’un utilisateur. |   La valeur False pour empêcher le tableau blanc dans une réunion |
| AllowTranscription |Détermine si les légendes en temps réel et/ou postérieures à la réunions et des transcriptions sont autorisées dans les réunions d’un utilisateur.|    La valeur False pour empêcher la transcription et des légendes à une réunion  |  
| AllowSharedNotes | Détermine si les utilisateurs sont autorisés à prendre des notes partagées. | La valeur False pour empêcher les utilisateurs de prendre des notes partagées |
|MediaBitRateKB |Détermine la vitesse de transmission multimédia pour audio/vidéo / d’application dans les réunions, les transmissions de partage  | Valeur suggérée est 5 000 (5 Mo). Vous pouvez modifier en fonction des besoins de votre organisation.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Créer et attribuer une stratégie de réunion

1. Démarrer une session Windows PowerShell en tant qu’administrateur.
2. Se connecter au connecteur Skype en ligne.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Afficher la liste des options de la stratégie de réunion.

       Get-CsTeamsMeetingPolicy
 
4. Recherchez l’option stratégie intégrée où toutes les stratégies de réunion sont désactivées. Il se présente comme suit.
   
        Identity                                    : Tag:AllOff
        Description                                 :
        AllowChannelMeetingScheduling               : False
        AllowMeetNow                                : False
        AllowIPVideo                                : False
        AllowAnonymousUsersToDialOut                : False
        AllowAnonymousUsersToStartMeeting           : False
        AllowPrivateMeetingScheduling               : False
        AutoAdmittedUsers                           : False
        AllowCloudRecording                         : False
        AllowOutlookAddIn                           : False
        AllowPowerPointSharing                      : False
        AllowParticipantGiveRequestControl          : False
        AllowExternalParticipantGiveRequestControl  : False
        AllowSharedNotes                            : False
        AllowWhiteboard                             : False
        AllowTranscription                          : False
        MediaBitRateKb                              : False
        ScreenSharingMode                           : False

5. Appliquer l’option de stratégie intégrée AllOff à tous les utilisateurs qui emploient des équipes dans un environnement virtualisé. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Pour plus d’informations sur les stratégies de réunion équipes, voir [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Configuration requise de fournisseur de la virtualisation

L’application équipes a été validée sur les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, consultez votre fournisseur de solutions de virtualisation pour vérifier la configuration minimale requise est respectée.

### <a name="virtual-machine-requirements"></a>Configuration requise de Machine virtuelle

Avec les diverses charges de travail et les besoins des utilisateurs dans un environnement virtualisé, voici la configuration minimale recommandée de configuration de l’ordinateur virtuel.

|Paramètre  |Mesure  |
|---------|---------|
|processeurs virtuels    |  2 cœurs       |
|RAM     |  4 GO      |
|Stockage     | 8 Go       |

### <a name="virtual-machine-operating-system-requirements"></a>Configuration requise du système d’exploitation Machine virtuelle

Les systèmes d’exploitation pris en charge pour l’ordinateur virtuel sont les suivants :

- Windows 10 et versions ultérieures
- Windows Server 2012 R2 et versions ultérieures

## <a name="install-teams-on-vdi"></a>Installer des équipes sur VDI

Voici le processus et les outils nécessaires pour déployer l’application de bureau équipes. 

1. Téléchargez le package MSI équipes à l’aide d’un des liens suivants en fonction de l’environnement. Nous vous recommandons la version 64 bits pour une VM VDI avec un système d’exploitation 64 bits.

    - [version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Exécutez la commande suivante pour installer le fichier MSI de VM VDI (ou effectuer la mise à jour).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Cela installe des équipes pour les fichiers de programme. À ce stade, le programme d’installation or image est terminée.
 
    La prochaine ouverture de session interactive démarre les équipes et demande des informations d’identification. Notez qu’il n’est pas possible de désactiver le démarrage automatique des équipes lors de l’installation des équipes sur VDI à l’aide de la propriété ALLUSER. 

3. Exécutez la commande suivante pour désinstaller le fichier MSI de la VM VDI (ou préparer la mise à jour).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Les équipes est désinstallé à partir des fichiers de programme.

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

Les éléments suivants sont problèmes connus et limitations pour les équipes sur VDI.

- **Déploiements de type Shared session hôte**: déploiements de type Shared session hôte (par exemple, non persistants VM configuration partagé) ne sont pas dans l’étendue.
- **Appel et réunions**:

    - Appel et scénarios de réunion ne sont pas optimisés pour VDI. Ces scénarios sont médiocres. Nous recommandons l’utilisation de stratégies au niveau de l’utilisateur comme décrit dans la section [définir des stratégies pour désactiver l’appel et fonctionnalités dans les équipes de réunion](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - Appliquer les stratégies décrites dans cet article a un impact sur la possibilité d’utiliser les fonctionnalités d’appel et de réunion, qui peut affecter d’autres utilisateurs de votre organisation en fonction d’autres stratégies. Si les utilisateurs de votre organisation utilisent des clients de non VDI, vous pouvez choisir de ne pas appliquer les stratégies.  

- **Participer à des appels et les réunions créées par les autres utilisateurs**: bien que les stratégies d’empêcher les utilisateurs de créer des réunions, ils peuvent toujours participer aux réunions si un autre utilisateur se connecte à leur de la réunion. Ces réunions, la possibilité de l’utilisateur à partager une vidéo, utiliser un tableau blanc et autres fonctionnalités dépendent si vous avez désactivé les fonctionnalités de TeamsMeetingPolicy.  
- **Contenu mis en cache**: si l’environnement virtuel dans les équipes est en cours d’exécution n’est pas persistant (et données sont nettoyées à la fin de chaque session de l’utilisateur), les utilisateurs peuvent remarquer une dégradation des performances en raison de l’actualisation du contenu, quelle que soit ou non l’utilisateur accède à la même contenu dans une session précédente.
- **Mises à jour du client**: équipes sur VDI n’est pas automatiquement mis à jour de la même manière que les clients non - VDI équipes.  Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau fichier MSI, comme décrit dans la section [Installer des équipes sur VDI](#install-teams-on-vdi) . Vous devez désinstaller la version actuelle de mise à jour vers une version plus récente.
- **Expérience utilisateur**: équipes l’expérience de l’utilisateur dans un environnement VDI peut être différente d’un environnement non VDI. Les différences peuvent être en raison des paramètres de stratégie et/ou fonctionnalité prise en charge dans l’environnement.

Pour les équipes qui ne sont pas liés à VDI problèmes connus, voir [problèmes connus relatifs aux équipes Microsoft](Known-issues.md).

## <a name="related-topics"></a>Rubriques connexes

- [Installer Microsoft Teams à l’aide de MSI](msi-deployment.md)