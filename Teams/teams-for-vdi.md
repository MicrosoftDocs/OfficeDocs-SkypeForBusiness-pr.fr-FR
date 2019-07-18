---
title: Teams pour une infrastructure bureau virtualisée(VDI)
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 04/10/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi
description: Découvrez comment exécuter Microsoft teams dans un environnement VDI (Virtual Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 132bd532ae8f7da98edb38a81363b4d5b6501532
ms.sourcegitcommit: 9751f34318119991b1bd32b384b8e1479c83cb0e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2019
ms.locfileid: "35768147"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour une infrastructure bureau virtualisée(VDI)

Cet article décrit les exigences et limitations relatives à l’utilisation de Microsoft teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce qu’un infrastructure VDI?

La technologie VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation et des applications de bureau sur un serveur centralisé dans un centre de données. Cela permet d’offrir une expérience de bureau entièrement personnalisée aux utilisateurs dotés d’une source centralisée entièrement sécurisée et compatible. 
 
Pour le moment, teams dans un environnement virtualisé est disponible avec la prise en charge de la fonctionnalité de collaboration et de conversation avec un ordinateur virtuel permanent dédié. Pour garantir une utilisation optimale des utilisateurs, suivez les recommandations de cet article. 

## <a name="teams-requirements"></a>Exigences des équipes

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality-in-teams"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion dans teams

Les équipes d’appel et de réunion ne sont pas optimisées dans un environnement VDI (bientôt disponible). Nous vous recommandons de définir les stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

Vous pouvez toujours choisir d’exécuter entièrement des équipes dans une infrastructure VDI à l’aide de l’application de bureau teams ou de l’application Web. Toutefois, nous vous recommandons de définir les stratégies afin d’éviter d’entraver l’utilisation de l’utilisateur.  

L’exécution de la stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez dans quelques heures.

> [!NOTE]
> Lorsque les équipes appelant et rendez-vous sont optimisées pour une utilisation dans les environnements de bureau virtuels, vous pouvez rétablir ces stratégies et permettre aux utilisateurs d’utiliser teams comme vous le feriez habituellement. 

#### <a name="calling"></a>Appels

Utilisez les applets de commande **CSTeamsCallingPolicy** pour contrôler si les utilisateurs sont autorisés à utiliser les options d’appel et d’appel dans les discussions privées et de groupe. Voici la liste des paramètres de stratégie et des valeurs recommandées.

|Nom de la stratégie  |Description |Valeur recommandée  |
|---------|---------|---------|
|AllowCalling    |Contrôle les fonctionnalités d’appel d’interopérabilité. L’activation de cette option permet aux utilisateurs de Skype entreprise d’avoir des appels en tête-à-tête avec les utilisateurs de Microsoft Teams, et vice versa.         |Valeur définie sur false pour empêcher les appels d’utilisateurs Skype entreprise dans Teams.          |
|AllowPrivateCalling     | Indique si l’application à l’origine de l’appel est disponible dans la barre de l’application, sur le côté gauche du client teams et si les utilisateurs voient les options d’appel et de vidéo dans une conversation privée         |False pour supprimer l’application à l’origine de l’appel dans la barre de l’application, sur le côté gauche de teams, et supprimer les options d’appel et de vidéo dans une conversation privée.          |

#### <a name="create-and-assign-a-calling-policy"></a>Création et affectation d’une stratégie d’appel

1. Démarrez une session Windows PowerShell en tant qu’administrateur.
2. Connectez-vous au connecteur en ligne Skype.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Affichez la liste des options de stratégie d’appel.

       Get-CsTeamsCallingPolicy
 
4. Recherchez l’option de stratégie intégrée dans laquelle toutes les stratégies d’appel sont désactivées. Elle se présente comme suit.
   
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

5. Appliquez l’option de stratégie intégrée à DisallowCalling à tous les utilisateurs qui utiliseront teams dans un environnement virtualisé.

        Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”

Pour plus d’informations sur les stratégies d’appel d’équipe, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

#### <a name="meetings"></a>Réunions

Utilisez les applets de commande **CsTeamsMeetingPolicy** pour contrôler le type de réunion que les utilisateurs peuvent créer, les fonctionnalités auxquelles ils peuvent accéder pendant une réunion, ainsi que les fonctionnalités de réunion disponibles pour les utilisateurs anonymes et externes. Voici la liste des paramètres de stratégie et des valeurs recommandées.

|Nom de la stratégie |Description|Valeur recommandée                   |
|-------------------|-----------------|-----------------------|
|AllowPrivateMeetingScheduling  | Détermine si un utilisateur est autorisé à planifier des réunions privées.| Valeur définie sur false pour empêcher l’utilisateur d’être en mesure de planifier des réunions privées.  |
|AllowChannelMeetingScheduling  | Détermine si un utilisateur est autorisé à planifier des réunions de canal. | Valeur définie sur false pour empêcher l’utilisateur d’être en mesure de planifier des réunions de canal.                       |
|AllowMeetNow |Détermine si un utilisateur est autorisé à créer ou à démarrer des réunions ad hoc.              |  Définissez cette valeur sur false pour empêcher l’utilisateur de démarrer des réunions ad hoc.                     |
|ScreenSharingMode | Détermine le mode dans lequel un utilisateur est autorisé à partager son écran dans des appels ou des réunions. | Défini sur Disabled pour empêcher l’utilisateur de partager son écran                          |
|AllowIPVideo |Détermine si la vidéo est activée dans les réunions ou les appels d’un utilisateur.                  |    Valeur définie sur false pour empêcher l’utilisateur de partager sa vidéo                                         |
| AllowAnonymousUsersToDialOut | Détermine si les utilisateurs anonymes sont autorisés à appeler un numéro PSTN. | Valeur définie sur false pour interdire aux utilisateurs anonymes de composer un numéro                                  |
| AllowAnonymousUsersToStartMeeting | Détermine si les utilisateurs anonymes peuvent démarrer une réunion.     |  Valeur définie sur false pour interdire aux utilisateurs de démarrer une réunion                                            |
| AllowOutlookAddIn |Détermine si un utilisateur peut planifier des réunions d’équipes dans le client de bureau Outlook.| Défini sur false pour empêcher un utilisateur de planifier des réunions teams dans le client de bureau Outlook|
| AllowParticipantGiveRequestControl|Détermine si les participants peuvent demander ou donner le contrôle du partage d’écran.| Valeur définie sur false pour empêcher l’utilisateur d’attribuer et de demander le contrôle pendant une réunion    |
| AllowExternalParticipantGiveRequestControl | Détermine si les participants externes peuvent demander ou donner le contrôle du partage d’écran.| Défini sur false pour interdire à un utilisateur externe de demander le contrôle pendant une réunion|
|AllowPowerPointSharing|Détermine si le partage PowerPoint est autorisé dans les réunions d’un utilisateur. |Défini sur false pour empêcher un utilisateur de partager des fichiers PowerPoint dans une réunion  |
|AllowWhiteboard | Détermine si le tableau blanc est autorisé dans les réunions d’un utilisateur. |   Valeur définie sur false pour interdire le tableau blanc dans une réunion |
| AllowTranscription |Détermine si les légendes et les transcriptions en temps réel et/ou après réunion sont autorisées dans les réunions d’un utilisateur.|    Valeur false pour interdire la transcription et les légendes dans une réunion  |  
| AllowSharedNotes | Détermine si les utilisateurs sont autorisés à prendre des notes partagées. | Défini sur false pour interdire aux utilisateurs de suivre des notes partagées |
|MediaBitRateKB |Détermine le taux de bits média pour les transmissions du partage audio/vidéo/d’application en réunions.  | La valeur suggérée est 5000 (5 Mo). Vous pouvez le modifier en fonction des besoins de votre organisation.| 

#### <a name="create-and-assign-a-meeting-policy"></a>Création et affectation d’une stratégie de réunion

1. Démarrez une session Windows PowerShell en tant qu’administrateur.
2. Connectez-vous au connecteur en ligne Skype.

        # Set Office 365 User Name and Password
        $username = “admin email address”
        password = ConvertTo-SecureString "password" -AsPlainText -Force
        $LiveCred = new-object -typename System.Management.Automation.PSCredential -argumentlist $username, $password
        # Connect to Skype Online
        Import-Module SkypeOnlineConnector
        $sfboSession = New-CsOnlineSession -Credential $LiveCred
        Import-PSSession $sfboSession```

3. Afficher une liste des options de stratégie de réunion

       Get-CsTeamsMeetingPolicy
 
4. Recherchez l’option de stratégie prédéfinie dans laquelle toutes les stratégies de réunion sont désactivées. Elle se présente comme suit.
   
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

5. Appliquez l’option de stratégie intégrée à AllOff à tous les utilisateurs qui utiliseront teams dans un environnement virtualisé. 

        Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”

 Pour plus d’informations sur les stratégies de réunion Teams, voir [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

### <a name="virtualization-provider-requirements"></a>Configuration requise pour les fournisseurs de virtualisation

L’application teams a été validée sur les principaux fournisseurs de solutions de virtualisation. Auprès de plusieurs fournisseurs de marché, contactez votre fournisseur de solutions de virtualisation pour vous assurer que les exigences minimales sont satisfaites.

### <a name="virtual-machine-requirements"></a>Configuration requise pour les machines virtuelles

En ce qui concerne les diverses charges de travail et les besoins des utilisateurs dans un environnement virtualisé, voici la configuration minimale recommandée pour les ordinateurs virtuels.

|Paramètre  |Action  |
|---------|---------|
|CPU    |  2 cœurs       |
|RAM     |  4 GO      |
|Stockage     | 8 Go       |

### <a name="virtual-machine-operating-system-requirements"></a>Configuration requise pour le système d’exploitation de l’ordinateur virtuel

Les systèmes d’exploitation pris en charge pour les VM sont les suivants:

- Windows 10 et versions ultérieures
- Windows Server 2012 R2 et version ultérieure

## <a name="install-teams-on-vdi"></a>Installer teams sur un infrastructure VDI

Voici le processus et les outils de déploiement de l’application de bureau Teams. 

1. Téléchargez le package MSI teams à l’aide de l’un des liens suivants selon l’environnement. Nous vous recommandons d’utiliser la version 64 bits d’un VM VDI doté d’un système d’exploitation 64 bits.

    - [version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Exécutez la commande suivante pour installer le MSI sur la machine virtuelle VDI (ou terminer la mise à jour).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    Cette opération permet d’installer teams pour programmer des fichiers. À ce stade, la configuration de l’image Golden est terminée.
 
    La prochaine session interactive de connexion démarre teams et demande des informations d’identification. Notez qu’il n’est pas possible de désactiver le lancement automatique d’équipes lors de l’installation d’équipes sur VDI à l’aide de la propriété ALLUSER. 

3. Exécutez la commande suivante pour désinstaller le MSI de l’ordinateur virtuel VDI (ou préparer la mise à jour).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Cela a pour cela la désinstallation de teams.

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

Vous trouverez ci-après des problèmes connus et des limitations applicables aux équipes sur VDI.

- **Déploiements de type hôte de session partagée**: les déploiements de type hôte de session partagée (par exemple, configuration VM non persistante partagée) ne sont pas dans l’étendue.
- **Appels et réunions**:

    - Les scénarios d’appel et de réunion ne sont pas optimisés pour VDI. Ces scénarios d’exécution seront médiocres. Nous vous recommandons d’utiliser des stratégies de niveau utilisateur comme décrit dans la section [définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion dans teams](#set-policies-to-turn-off-calling-and-meeting-functionality-in-teams) .  
    - Le recours aux stratégies décrites dans cet article affecte la possibilité d’utiliser les fonctionnalités d’appel et de réunion, qui varient en fonction des autres stratégies, peuvent affecter d’autres utilisateurs au sein de votre organisation. Si les utilisateurs de votre organisation utilisent des clients non-VDI, vous pouvez choisir de ne pas appliquer les stratégies.  

- **Participation à des appels et des réunions créées par d’autres utilisateurs**: bien que les stratégies restreignent les utilisateurs de la création de réunions, elles peuvent quand même participer à des réunions lorsqu’un autre utilisateur les appelle à partir de la réunion. Lors de ces réunions, la capacité de l’utilisateur à partager la vidéo, utiliser le tableau blanc et les autres fonctionnalités selon que vous avez désactivé ces fonctionnalités à l’aide de TeamsMeetingPolicy.  
- **Contenu mis en cache**: si l’environnement virtuel dans lequel teams est en cours d’exécution n’est pas permanent (et si les données sont nettoyées à la fin de chaque session utilisateur), les utilisateurs peuvent remarquer une dégradation des performances en raison de l’actualisation du contenu, que l’utilisateur ait accédé ou non. contenu d’une session précédente.
- **Mises à jour du client**: teams sur VDI n’est pas automatiquement mis à jour avec l’installation de MSI par ordinateur. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans la section [installer teams sur VDI](#install-teams-on-vdi) . Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- **** Environnement d’utilisation: l’environnement d’utilisation des équipes dans un environnement VDI est différent d’un environnement non-VDI. Il y a des différences en raison des paramètres de stratégie et de la prise en charge des fonctionnalités dans l’environnement.

Pour les problèmes connus qui ne sont pas liés à VDI, voir [problèmes connus de Microsoft teams](Known-issues.md).

## <a name="related-topics"></a>Voir aussi

- [Installation de Microsoft teams à l’aide de MSI](msi-deployment.md)
