---
title: Teams pour une infrastructure bureau virtualisée(VDI)
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Découvrez comment exécuter Microsoft teams dans un environnement VDI (Virtual Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2afe86014bcce01d60ceef768f6f888718c3696c
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952847"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour une infrastructure bureau virtualisée(VDI)

Cet article décrit les exigences et limitations relatives à l’utilisation de Microsoft teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce qu’un infrastructure VDI ?

La technologie VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation et des applications de bureau sur un serveur centralisé dans un centre de données. Cela permet d’offrir une expérience de bureau entièrement personnalisée aux utilisateurs dotés d’une source centralisée entièrement sécurisée et compatible.
 
Microsoft teams dans un environnement virtualisé prend en charge les discussions et la collaboration, et les fonctionnalités d’appel et de réunion de la plateforme Citrix sont également prises en charge.

Teams dans un environnement virtualisé prend en charge plusieurs configurations. Cela inclut les modes VDI, dédié, partagé, permanent et non persistant. Les fonctionnalités sont en développement continu et sont ajoutées régulièrement, et les fonctionnalités seront développées dans les prochains mois et années.
 
L’utilisation de teams dans un environnement virtualisé est légèrement différente de l’utilisation d’équipes dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées peuvent ne pas être disponibles dans un environnement virtualisé et la résolution vidéo peut varier. Pour garantir une utilisation optimale des utilisateurs, suivez les recommandations de cet article.

## <a name="teams-on-vdi-components"></a>Équipes sur les composants VDI

L’utilisation des équipes dans un environnement virtualisé nécessite les composants suivants.

- **Broker de virtualisation**: le gestionnaire de ressources et de connexions au fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel**: pile d’ordinateurs virtuels qui exécute Microsoft teams
- **Client léger**: point de terminaison avec lequel l’utilisateur s’est connecté physiquement
- **Application de bureau teams**: il s’agit de l’application client de bureau teams

## <a name="teams-on-vdi-requirements"></a>Exigences des équipes sur VDI

### <a name="virtualization-provider-requirements"></a>Configuration requise pour les fournisseurs de virtualisation

L’application de bureau teams a été validée avec les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous conseillons de consulter le fournisseur de votre solution de virtualisation pour vous assurer que les exigences minimales sont satisfaites.
  
Pour l’instant, les équipes sur VDI avec l’optimisation de l’audio/vidéo (AV) sont certifiées avec Citrix. Passez en revue les informations de cette section pour vous assurer que les exigences de Citrix et d’équipes sont satisfaites.

### <a name="partners-certified-for-teams"></a>Partenaires certifiés pour teams

Les partenaires suivants disposent de solutions d’infrastructure de bureau virtuel pour Teams.

|Partenaire|Solution de partenariat|
|----|---|
|![Le logo représentant Citrix](media/citrix.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Applications virtuelles et ordinateurs de bureau Citrix</a> |

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Configurations requises pour les applications virtuelles et les postes de travail Citrix

Les applications virtuelles et ordinateurs de bureau Citrix (auparavant appelées XenApp et XenDesktop) offrent une optimisation AV pour teams sur VDI. Grâce aux applications virtuelles et aux ordinateurs de bureau Citrix, teams sur VDI prend en charge les fonctionnalités d’appel et de réunion en plus de la fonctionnalité de conversation et de collaboration.

Vous pouvez télécharger la dernière version des applications virtuelles et des bureaux [.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Vous devrez d’abord vous connecter.) Les composants nécessaires sont regroupés par défaut dans l' [application d’espace de travail Citrix (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’agent de remise virtuel (VDA). Vous n’avez pas besoin d’installer d’autres composants ou plugin sur CWA ou sur VDA.

Pour obtenir les dernières exigences relatives au serveur et au client, consultez [ce site Web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installation ou mise à jour de l’application de bureau teams sur VDI

Vous pouvez déployer l’application de bureau teams pour VDI à l’aide d’une installation par ordinateur ou d’une installation par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser varie selon que vous utilisez une configuration persistante ou non persistante et que vous avez besoin de fonctionnalités de votre organisation.
Pour une configuration persistante dédiée, l’une d’elles fonctionnerait.  Toutefois, dans le cas d’une configuration non persistante, l’installation par machine est nécessaire pour que teams fonctionne efficacement. Voir la section [configuration non persistante](#non-persistent-setup) .

Sur une installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour l’application Teams, vous devez désinstaller la version actuelle pour mettre à jour vers une version plus récente. Dans le cas d’une installation par utilisateur, les mises à jour automatiques sont activées. Pour la plupart des déploiements d’infrastructure VDI, nous vous conseillons de déployer des équipes via une installation par ordinateur.

Pour effectuer une mise à jour vers la version la plus récente d’Teams, commencez par la procédure de désinstallation suivie du déploiement de la dernière version d’Teams.

Pour que l’optimisation de l’utilisation des services AUDIOVISUELs dans les environnements VDI fonctionne correctement, le point de terminaison client léger doit avoir accès à Internet. Si l’accès à Internet n’est pas disponible au point de terminaison client léger, le démarrage de l’optimisation échoue. Cela signifie que l’utilisateur se trouve dans un État multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Configuration persistante dédiée

Dans une configuration persistante dédiée, les modifications du système d’exploitation local des utilisateurs sont conservées après la fermeture de la session de l’utilisateur.  Pour une configuration persistante, teams prend en charge les installations par utilisateur et par ordinateur.

Voici la configuration minimale recommandée pour les ordinateurs virtuels.

|Paramètre  |Système d’exploitation Workstation  |Système d’exploitation serveur  |
|---------|---------|---------|
|CPU   |    2 cœurs     |  4, 6 ou 8<br>Il est important de comprendre la configuration de NUMA (non-Uniform Memory Access) sous-jacente et de configurer vos ordinateurs virtuels en conséquence.     |
|RAM     |   4 GO      | 512 à 1024 Mo par utilisateur        |
|Stockage    | 8 Go        | 40 à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non persistante

Dans une configuration non persistante, les modifications du système d’exploitation local des utilisateurs ne sont pas conservées lorsque les utilisateurs se déconnectent. Ces paramètres sont fréquemment partagés par des sessions multi-utilisateurs. La configuration de l’ordinateur virtuel varie en fonction du nombre d’utilisateurs et des ressources de zone physiques disponibles.

Dans le cas d’une configuration non persistante, l’application de bureau teams doit être installée par ordinateur vers l’image Golden. Pour en savoir plus, voir la section [installer ou mettre à jour l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Cela garantit un lancement efficace de l’application teams lors d’une session utilisateur. L’utilisation de teams avec une configuration non persistante nécessite également un gestionnaire de mise en cache de profil pour une synchronisation des données d’exécution teams efficace. Cela permet de s’assurer que les informations spécifiques à l’utilisateur (par exemple, les données utilisateur, le profil et les paramètres) sont mises en cache lors de la session utilisateur.  Il existe plusieurs solutions de gestionnaire de mise en cache disponibles. Par exemple, [FSLogix](https://docs.microsoft.com/fslogix/overview). Pour obtenir des instructions de configuration spécifiques, contactez le fournisseur du gestionnaire de cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste d’exclusions de contenu mise en cache dans teams pour une configuration non persistante

Exclure les éléments suivants du dossier teams Caching,% AppData%/Microsoft/Teams.  À l’exception de ces informations, vous réduisez la taille de la mise en cache utilisateur pour optimiser votre configuration non permanente.

- fichiers. txt
- Média-dossier pile

### <a name="office-365-proplus-considerations"></a>Considérations relatives à Office 365 ProPlus

Prenez en compte les points suivants lorsque vous déployez teams avec Office 365 ProPlus sur VDI.

#### <a name="new-deployments-of-teams-through-office-365-proplus"></a>Nouveaux déploiements d’équipes via Office 365 ProPlus

Avant de déployer des équipes via Office 365 ProPlus, vous devez commencer par désinstaller toutes les applications d’équipe déjà existantes si elles ont été déployées à l’aide d’une installation par ordinateur.

Teams via Office 365 ProPlus est installé par utilisateur. Pour en savoir plus, voir la section [installation ou mise à jour de l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-office-365-proplus-updates"></a>Déploiement d’équipes via les mises à jour d’Office 365 ProPlus

Des équipes sont également ajoutées aux installations d’Office 365 ProPlus existantes. Dans la mesure où Office 365 ProPlus installe uniquement les équipes par utilisateur, voir la section [installation ou mise à jour de l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="using-teams-with-per-machine-installation-and-office-365-proplus"></a>Utilisation de teams avec une installation par ordinateur et Office 365 ProPlus

Office 365 ProPlus ne prend pas en charge les installations par poste de teams. Pour utiliser une installation par ordinateur, vous devez exclure des équipes d’Office 365 ProPlus. Reportez-vous à l' [application déploiement de l’application de bureau teams dans l’ordinateur virtuel](#deploy-the-teams-desktop-app-to-the-vm) et [Comment exclure le déploiement d’équipes via les sections Office 365 ProPlus](#how-to-exclude-teams-deployment-through-office-365-proplus) .

#### <a name="how-to-exclude-teams-deployment-through-office-365-proplus"></a>Comment exclure le déploiement d’équipes via Office 365 ProPlus

Pour en savoir plus sur teams et Office 365 ProPlus, voir [Comment exclure des équipes des nouvelles installations d’office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) et [utiliser une stratégie de groupe pour contrôler l’installation d’teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déploiement de l’application de bureau teams sur l’ordinateur virtuel

1. Téléchargez le package MSI teams qui correspond à votre système d’exploitation VM VDI en utilisant l’un des liens suivants :

    - [version 32 bits](https://statics.teams.cdn.office.net/production-windows/1.2.00.32462/Teams_windows.msi)
    - [version 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.2.00.32462/Teams_windows_x64.msi)

    La version minimum de l’application de bureau teams requise est la version 1.2.00.31357. (La conservation RTC n’est pas prise en charge dans les versions antérieures.)

2. Installez le MSI sur la machine virtuelle VDI en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name>
        ```
    
        Il s’agit de l’installation par défaut, qui installe teams sur le dossier% AppData%. À ce stade, la configuration de l’image Golden est terminée. Teams ne fonctionne pas correctement avec une installation par utilisateur sur une configuration non persistante.
    
    - Installation par ordinateur

        ```
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1
        ```

        Cette opération permet d’installer teams vers le dossier Program Files (x86) sur un système d’exploitation 64 bits et dans le dossier Program Files sur un système d’exploitation 32 bits. À ce stade, la configuration de l’image Golden est terminée. L’installation d’équipes par machine est requise pour les configuration non persistantes.
 
        La prochaine session interactive de connexion démarre teams et demande des informations d’identification.

3. Désinstaller le MSI de l’ordinateur virtuel VDI. 

    Il existe deux façons de désinstaller teams :  
  
    - Script PowerShell (recommandé) : vous pouvez utiliser ce [script PowerShell](scripts/powershell-script-teams-deployment-clean-up.md) pour nettoyer les équipes des utilisateurs ou des ordinateurs cibles. Il doit être exécuté pour chaque utilisateur sur un ordinateur ciblé. 
    
    - Ligne de commande : cette approche supprime Teams, mais empêche la réinstallation de teams. Exécutez la commande suivante :
  
      ```
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```
      Cette opération désinstalle les équipes du dossier Program Files (x86) ou Program Files, en fonction de l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Considérations relatives aux performances d’une équipe sur VDI

Il existe de nombreuses configurations de configuration virtualisées, chacune avec un focus d’optimisation différent. Par exemple, la densité utilisateur. Lors de la planification, prenez en compte les éléments suivants pour vous aider à optimiser votre configuration en fonction des besoins de charge de travail de votre organisation :

- Configuration minimale : certaines charges de travail peuvent nécessiter une configuration qui utilise des ressources inférieures à la configuration minimale requise. Par exemple, les charges de travail pour les développeurs qui utilisent des applications qui nécessitent plus de ressources informatiques.
- Dépendances : il s’agit de dépendances en matière d’infrastructure, de charge de travail et d’autres aspects environnementaux extérieurs à l’application de bureau Teams.
- Fonctionnalités désactivées sur VDI : teams désactive les fonctionnalités gourmandes en GPU pour VDI, ce qui permet d’améliorer l’utilisation de l’UC temporaire. Les fonctionnalités suivantes sont désactivées :
    - Animation CSS teams
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Équipes sur VDI avec les appels et les réunions

En plus des discussions et de la collaboration, les équipes sur VDI dotées d’une prise en charge des appels et des réunions sont disponibles avec les plates-formes basées sur Citrix. Les fonctionnalités prises en charge sont basées sur la pile multimédia WebRTC et l’implémentation propre à Citrix. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant les équipes dans l’architecture VDI](media/teams-on-vdi-architecture.png)

Ces fonctionnalités d’appel et de réunion ne sont pas prises en charge :

- Amélioration des services d’urgence
- Boutons HID et contrôles LED entre l’application et les appareils teams
- Effets et atténuation d’arrière-plan
- Événements de diffusion/en temps réel
- Routage basé sur l’emplacement (LBR)
- Parcage d'appel
- File d’attente d’appels

> [!IMPORTANT]
> Si vous disposez actuellement d’une équipe sans optimisation AV dans l’infrastructure VDI et que vous utilisez des fonctionnalités qui ne sont pas encore prises en charge pour l’optimisation (par exemple, donner et prendre le contrôle lors du partage d’une application), vous devez définir des stratégies Citrix pour désactiver la redirection d’équipes. Cela signifie que les sessions multimédias des équipes ne sont pas optimisées. Pour plus d’informations sur la façon de définir des stratégies pour désactiver la redirection d’équipes, voir ce [site Web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/policies/reference/ica-policy-settings/multimedia-policy-settings.html).

Nous travaillons actuellement pour ajouter des fonctionnalités d’appel et de réunion qui ne sont disponibles que dans les environnements non-VDI. Il s’agit notamment de contrôles d’administration supplémentaires sur la qualité, de scénarios de partage d’écran supplémentaires et de fonctionnalités avancées récemment ajoutées à Teams. Contactez votre représentant pour en savoir plus sur les fonctionnalités à venir.

### <a name="network-requirements"></a>Conditions de réseau requises

Nous vous recommandons d’évaluer votre environnement pour identifier les risques et les exigences qui peuvent influer sur le déploiement global de l’audio et de la vidéo dans le Cloud. Utilisez l' [outil d’analyse du réseau Skype entreprise](https://www.microsoft.com/download/details.aspx?id=53885) pour tester si votre réseau est prêt pour les équipes.

Pour en savoir plus sur la préparation de votre réseau pour Teams, voir [préparer le réseau de votre organisation pour teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migration de Skype entreprise sur VDI vers teams sur VDI

Si vous effectuez une migration à partir de Skype entreprise sur VDI vers teams sur VDI, outre les différences entre les deux applications, il existe des différences au niveau de l’infrastructure VDI. Les fonctionnalités qui ne sont pas actuellement prises en charge dans l’infrastructure VDI de Skype entreprise sont les suivantes :

- Contrôle des expériences d’appel d’infrastructure VDI grâce aux stratégies de limitation du débit multimédia
- Stratégie par plateforme pour désactiver certaines fonctionnalités AV dans un environnement VDI
- Donner et prendre le contrôle lors du partage d’application
- Partage d’écran d’une conversation sans l’audio
- Envoi et réception simultanés de la vidéo et du partage d’écran

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Équipes sur le navigateur Chrome et l’application de bureau teams pour VDI

Les équipes sur le navigateur Chrome ne fournissent pas de remplacement pour l’application de bureau teams pour une infrastructure VDI avec optimisation AV. L’utilisation des discussions et de la collaboration fonctionne comme prévu. Lorsque le contenu multimédia est requis, certaines expériences peuvent ne pas répondre aux attentes des utilisateurs dans le navigateur Chrome :

- L’interface de diffusion audio et vidéo n’est pas idéale. Les utilisateurs peuvent être retardés ou de réduire la qualité.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des appareils est gérée par le biais du navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Les paramètres de l’appareil doivent également être définis dans gestion des appareils Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur un VDI avec les discussions et la collaboration

Si votre organisation veut uniquement utiliser les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams. Ce niveau de fonctionnalité ne nécessite pas les applications virtuelles et les ordinateurs de bureau Citrix.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies en utilisant le centre d’administration Microsoft teams ou PowerShell. L’exécution de la stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez dans quelques heures.

[**Politiques d’appel**](teams-calling-policy.md): teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent des équipes dans un environnement virtualisé.

[**Stratégies de réunion**](meeting-policies-in-teams.md): teams inclut la stratégie de réunion AllOff intégrée dans laquelle les fonctionnalités de réunion sont désactivées. Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent des équipes dans un environnement virtualisé.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du centre d’administration Microsoft teams

Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff aux utilisateurs, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de l’utilisateur, puis sur **modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **stratégie d’appel**, cliquez sur **DisallowCalling**.
    2.  Sous **stratégie de réunion**, cliquez sur **AllOff**.
4. Cliquez sur **Appliquer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la stratégie que vous voulez attribuer. Par exemple :
    - Accédez à **** > **stratégies d’appel**vocal, puis cliquez sur **DisallowCalling**.
    - Accédez à **** > **stratégies de réunion**, puis cliquez sur **AllOff**.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity “user email id”
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity “user email id”
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez la rubrique [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-citrix-with-calling-and-meetings"></a>Migration des équipes sur l’infrastructure VDI avec les discussions et la collaboration vers Citrix avec les appels et les réunions

Si vous disposez d’une implémentation de teams sur VDI avec les fonctionnalités de conversation et de collaboration dans lesquelles vous avez défini des stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion et que vous effectuez une migration vers Citrix avec l’optimisation AV, vous devez définir des stratégies pour activer les appels et fonctionnalités de réunion pour les équipes des utilisateurs de VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer les fonctionnalités d’appel et de réunion

Vous pouvez utiliser le centre d’administration Microsoft teams ou PowerShell pour définir et affecter des stratégies d’appel et de réunion à vos utilisateurs. Le temps nécessaire pour que les modifications de la stratégie soient propagées peut prendre un certain temps. Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez après quelques heures.

Politiques d' [**appel**](teams-calling-policy.md): les stratégies d’appel en équipe contrôlent les fonctionnalités d’appel disponibles aux utilisateurs. Teams inclut la stratégie d’appel AllowCalling intégrée dans laquelle toutes les fonctions d’appel sont activées. Pour activer toutes les fonctions d’appel, affectez la stratégie AllowCalling. Vous pouvez créer une stratégie d’appel personnalisée pour activer les fonctions d’appel que vous souhaitez attribuer à vos utilisateurs. 

[**Stratégies**](meeting-policies-in-teams.md)de la réunion : les stratégies de réunion dans les équipes contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles pour les participants à la réunion, qui sont planifiés par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion intégrée de la réunion, dans laquelle toutes les fonctions de réunion sont activées. Pour activer toutes les fonctionnalités de réunion, affectez la stratégie d’activation. Vous pouvez créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion de votre choix et les affecter à des utilisateurs.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du centre d’administration Microsoft teams

Pour affecter la stratégie d’appel AllowCalling et la stratégie de réunion inconforme aux utilisateurs, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de l’utilisateur, puis sur **modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **stratégie d’appel**, cliquez sur **AllowCalling**.
    2.  Sous **stratégie de réunion**, **cliquez sur**inverser.
4. Cliquez sur **Appliquer**.

Pour attribuer une stratégie à plusieurs utilisateurs à la fois, voir [modifier les paramètres utilisateur d’équipes en bloc](edit-user-settings-in-bulk.md).

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la stratégie que vous voulez attribuer. Par exemple :
    - Accédez à **** > **stratégies d’appel**vocal, puis cliquez sur **AllowCalling**.
    - Accédez à **** > stratégies de réunion, **puis cliquez sur****intentn**.
3. Sélectionnez **gérer les utilisateurs**.
4. Dans le volet **gérer les utilisateurs** , recherchez l’utilisateur par nom complet ou par nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
5. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel AllowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity “user email id”
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser l' [autorisation Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion d’autorisation à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity “user email id”
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez la rubrique [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

### <a name="client-deployment-installation-and-setup"></a>Déploiement de clients, installation et configuration

- Dans le cas d’une installation par ordinateur, teams sur VDI n’est pas automatiquement mis à jour de la même manière que les clients teams de l’infrastructure non VDI. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans la section [installation ou mise à jour de l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- Teams doit être déployée par l’utilisateur ou par machine. Le déploiement d’équipes pour le déploiement simultané par utilisateur et par ordinateur n’est pas pris en charge.  Pour effectuer une migration à partir de l’une ou l’autre de ces modes par poste de passe, suivez la procédure de désinstallation et redéployez en mode.
- Pour le moment, les clients MacOs et Linux ne sont pas pris en charge par Citrix.
- Citrix ne prend pas en charge l’utilisation de proxys HTTP explicites définis sur un point de terminaison. 

### <a name="calling-and-meetings"></a>Appels et réunions

- Le niveau d’interopérabilité avec Skype entreprise est limité aux appels audio et aucune modalité vidéo.
- L’interaction DTMF (multifrequency multifrequency) avec des systèmes de téléphonie n’est actuellement pas prise en charge.
- La participation à des réunions d’équipes en tant qu’utilisateur anonyme n’est pas optimisée pour l’AV. L’utilisateur peut rejoindre la réunion et disposer d’une expérience non optimisée.
- Un seul flux vidéo entrant est pris en charge dans les réunions ou les appels de groupe. Lorsque plusieurs personnes envoient de la vidéo, seule la vidéo dominante de haut-parleur est affichée à tout moment.  
- La résolution du flux vidéo entrant et sortant est limitée à la résolution 720p. Il s’agit d’une limitation WebRTC.
- Un seul flux vidéo à partir d’un appareil photo ou d’un flux de partage d’écran entrant est pris en charge. Lorsque le partage d’écran est reçu, le partage d’écran qui s’affiche à la place de la vidéo du présentateur dominant est affiché.
- Partage d’écran sortant :
    - Le partage d’applications n’est pas pris en charge.
- Donnez le contrôle et prenez le contrôle :  
    - Non pris en charge lors d’une session de partage d’écran ou d’application.
    - Pris en charge lors d’une session de partage PowerPoint.  
- La mise à l’échelle PPP élevée sur CWA n’est pas prise en charge.

Pour les problèmes connus des équipes qui ne sont pas liés à l’infrastructure VDI, voir [problèmes connus de teams](Known-issues.md).

## <a name="troubleshooting"></a>Résolution des problèmes

#### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes liés aux composants Citrix

Pour plus d’informations sur la résolution des problèmes liés à la fonction VDA et CWA, voir [ce site Web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

## <a name="related-topics"></a>Voir aussi

- [Installation de Microsoft teams à l’aide de MSI](msi-deployment.md)
- [Aperçu de Teams PowerShell](teams-powershell-overview.md)
