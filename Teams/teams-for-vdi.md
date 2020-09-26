---
title: Teams pour l’Infrastructure de bureau virtualisée (VDI)
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
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0d7d20c9faa8dd214c73e1ea759d32c931c7442
ms.sourcegitcommit: 4f7870f0958a3c73bbf57ad4d4f6b228f8dead73
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286110"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour l’Infrastructure de bureau virtualisée (VDI)

Cet article décrit les exigences et limitations relatives à l’utilisation de Microsoft teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce qu’un infrastructure VDI ?

La technologie VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation et des applications de bureau sur un serveur centralisé dans un centre de données. Cela permet d’offrir une expérience de bureau entièrement personnalisée aux utilisateurs dotés d’une source centralisée entièrement sécurisée et compatible.

Microsoft teams dans un environnement virtualisé prend en charge les discussions et la collaboration. Outre les plates-formes Windows Virtual Desktop, Citrix et VMware, les fonctionnalités d’appel et de réunion sont également prises en charge.

Teams dans un environnement virtualisé prend en charge plusieurs configurations. Cela inclut les modes VDI, dédié, partagé, permanent et non persistant. Les fonctionnalités sont en développement continu et sont ajoutées régulièrement, et les fonctionnalités seront développées dans les prochains mois et années.

L’utilisation des équipes dans un environnement virtualisé peut être légèrement différente de l’utilisation d’équipes dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées risquent de ne pas être disponibles dans un environnement virtualisé et la résolution vidéo peut varier.

Pour garantir une utilisation optimale des utilisateurs, suivez les recommandations de cet article.

 > [!Note]
> Pour plus d’informations sur les équipes VDI sur différentes plateformes, voir [fonctionnalités d’équipe par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Équipes sur les composants VDI

L’utilisation des équipes dans un environnement virtualisé nécessite les composants suivants.

- **Broker de virtualisation**: le gestionnaire de ressources et de connexions au fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel**: pile d’ordinateurs virtuels qui exécute Microsoft teams
- **Client léger**: point de terminaison avec lequel l’utilisateur s’est connecté physiquement
- **Application de bureau teams**: application de bureau teams

## <a name="teams-on-vdi-requirements"></a>Exigences des équipes sur VDI

### <a name="virtualization-provider-requirements"></a>Configuration requise pour les fournisseurs de virtualisation

L’application de bureau teams a été validée avec les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous conseillons de consulter le fournisseur de votre solution de virtualisation pour vérifier que vous respectez la configuration minimale requise.
  
Pour l’instant, les équipes sur VDI avec l’optimisation de l’audio/vidéo (AV) sont certifiées avec la version de bureau virtuelle de Windows, Citrix et VMware. Passez en revue les informations de cette section pour vérifier que vous respectez toutes les conditions requises pour les fonctionnalités appropriées.

### <a name="platforms-certified-for-teams"></a>Plates-formes certifiées pour teams

Les plateformes suivantes disposent de solutions d’infrastructure de bureau virtuel pour Teams.

|Plateforme|Solution|
|----|---|
|![Logo représentant Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Bureau virtuel Windows</a> |
|![Le logo représentant Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Applications virtuelles et ordinateurs de bureau Citrix</a> |
|![Le logo représentant VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">Horizon VMware</a> |

### <a name="windows-virtual-desktop"></a>Bureau virtuel Windows

Le bureau virtuel Windows fournit une optimisation AV pour les équipes sur VDI. Pour plus d’informations et la configuration requise et l’installation, voir [utiliser teams sur le bureau virtuel Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Configurations requises pour les applications virtuelles et les postes de travail Citrix

Les applications virtuelles et ordinateurs de bureau Citrix (auparavant appelées XenApp et XenDesktop) offrent une optimisation AV pour teams sur VDI. Grâce aux applications virtuelles et aux ordinateurs de bureau Citrix, teams sur VDI prend en charge les fonctionnalités d’appel et de réunion en plus de la fonctionnalité de conversation et de collaboration.

Vous pouvez télécharger la dernière version des applications virtuelles et des bureaux sur [le site de téléchargement de Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Vous devrez d’abord vous connecter.) Les composants nécessaires sont regroupés par défaut dans l' [application d’espace de travail Citrix (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’agent de remise virtuel (VDA). Vous n’avez pas besoin d’installer d’autres composants ou plugin sur CWA ou sur VDA.

Pour obtenir les dernières exigences relatives au serveur et au client, consultez [ce site Web de Citrix](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html).

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Espace de travail d’horizon VMware et configuration requise pour le Bureau

VMware horizon est une plate-forme moderne pour la remise sécurisée d’applications et de bureaux virtuels dans le Cloud hybride. Pour offrir une remarquable qualité de l’utilisation de l’utilisateur final, VMware horizon fournit une optimisation multimédia pour Teams. Cette optimisation améliore la productivité générale des bureaux et applications virtuels, et améliore l’expérience utilisateur lors de l’appel et de la réunion à l’aide d’équipes.

Vous pouvez télécharger la dernière version de VMware horizon sur la page [téléchargements de VMware](https://my.vmware.com/web/vmware/downloads/#all_products) . Les composants d’optimisation de média requis font partie du client de l’agent d’horizon et de l’horizon par défaut, et il est inutile d’installer un plug-in supplémentaire pour utiliser la fonctionnalité d’optimisation des équipes.

Pour obtenir les dernières exigences et instructions sur la configuration de l’optimisation des contenus multimédias pour Teams, consultez [ce site Web VMware](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html).

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installation ou mise à jour de l’application de bureau teams sur VDI

Vous pouvez déployer l’application de bureau teams pour VDI à l’aide d’une installation par ordinateur ou d’une installation par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser varie selon que vous utilisez une configuration persistante ou non persistante et que vous avez besoin de fonctionnalités de votre organisation.

Pour une configuration persistante dédiée, l’une d’elles fonctionnerait. Toutefois, pour une configuration non persistante, teams nécessite une installation par ordinateur pour fonctionner efficacement. Voir la section [configuration non persistante](#non-persistent-setup) .

Sur une installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour l’application Teams, vous devez désinstaller la version actuelle pour mettre à jour vers une version plus récente. Dans le cas d’une installation par utilisateur, les mises à jour automatiques sont activées. Pour la plupart des déploiements d’infrastructure VDI, nous vous conseillons de déployer des équipes via une installation par ordinateur.

Pour effectuer une mise à jour vers la version la plus récente d’Teams, commencez par la procédure de désinstallation suivie du déploiement de la dernière version d’Teams.

Pour que l’optimisation de l’utilisation des services AUDIOVISUELs dans les environnements VDI fonctionne correctement, le point de terminaison client léger doit avoir accès à Internet. Si l’accès à Internet n’est pas disponible au point de terminaison client léger, le démarrage de l’optimisation échoue. Cela signifie que l’utilisateur se trouve dans un État multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Configuration persistante dédiée

Dans une configuration persistante dédiée, les modifications du système d’exploitation local des utilisateurs sont conservées après la fermeture de la session de l’utilisateur. Pour la configuration persistante, teams prend en charge les installations par utilisateur et par ordinateur.

Voici la configuration minimale recommandée pour les ordinateurs virtuels.

|Paramètre  |Système d’exploitation Workstation  |Système d’exploitation serveur  |
|---------|---------|---------|
|CPU   |    2 cœurs     |  4, 6 ou 8<br>Il est important de comprendre la configuration de NUMA (non-Uniform Memory Access) sous-jacente et de configurer vos ordinateurs virtuels en conséquence.     |
|Mémoire RAM     |   4 GO      | 512 à 1024 Mo par utilisateur        |
|Stockage    | 8 Go        | 40 à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non persistante

Dans une configuration non persistante, les modifications du système d’exploitation local des utilisateurs ne sont pas conservées lorsque les utilisateurs se déconnectent. Ces paramètres sont fréquemment partagés par des sessions multi-utilisateurs. La configuration de l’ordinateur virtuel varie en fonction du nombre d’utilisateurs et des ressources de zone physiques disponibles.

Dans le cas d’une configuration non persistante, l’application de bureau teams doit être installée par ordinateur vers l’image Golden. (Pour en savoir plus, voir la section [installer ou mettre à jour l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .) Cela garantit un lancement efficace de l’application teams lors d’une session utilisateur.

L’utilisation de teams avec une configuration non persistante nécessite également un gestionnaire de mise en cache de profil pour une synchronisation des données d’exécution teams efficace. Cela permet de s’assurer que les informations spécifiques à l’utilisateur (par exemple, les données utilisateur, le profil et les paramètres) sont mises en cache lors de la session utilisateur. Vérifiez que les données de ces deux dossiers sont synchronisées.  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Users\username\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

Il existe de nombreuses solutions de gestionnaire de mise en cache disponibles. Par exemple, [FSLogix](https://docs.microsoft.com/fslogix/overview). Pour obtenir des instructions de configuration spécifiques, contactez le fournisseur du gestionnaire de cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste d’exclusions de contenu mise en cache dans teams pour une configuration non persistante

Exclure les éléments suivants du dossier teams Caching,% AppData%/Microsoft/Teams. L’exclusion de ces éléments permet de réduire la taille de la mise en cache utilisateur pour optimiser davantage votre configuration non persistante.

- fichiers. txt
- Média-dossier pile
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Considérations relatives aux applications 365 Microsoft pour les entreprises

Prenez en compte les points suivants lorsque vous déployez des équipes avec les applications Microsoft 365 pour Enterprise sur une infrastructure VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Déploiement de nouvelles équipes par le biais d’applications 365 Microsoft pour les entreprises

Avant de déployer des équipes via les applications Microsoft 365 pour les entreprises, vous devez d’abord désinstaller toutes les applications d’équipe existantes si elles ont été déployées à l’aide d’une installation par ordinateur.

Les équipes par le biais des applications 365 Microsoft pour entreprises sont installées par utilisateur. Pour en savoir plus, voir la section [installation ou mise à jour de l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Déploiement d’équipes par le biais des applications 365 Microsoft pour les mises à jour d’entreprise

Des équipes sont également ajoutées aux installations existantes d’applications 365 Microsoft pour entreprises. Dans la mesure où les applications Microsoft 365 pour l’entreprise installent uniquement teams par utilisateur, voir la section [installer ou mettre à jour l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Utilisation de teams avec une installation par ordinateur et des applications 365 Microsoft pour les entreprises

Les applications Microsoft 365 pour l’entreprise ne prennent pas en charge les installations par poste de teams. Pour utiliser une installation par ordinateur, vous devez exclure les équipes des applications 365 Microsoft pour entreprises. Reportez-vous à l' [application déploiement de l’application de bureau teams dans l’ordinateur virtuel](#deploy-the-teams-desktop-app-to-the-vm) et [Comment exclure le déploiement d’équipes via les applications Microsoft 365 pour les entreprises](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) .

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Comment exclure le déploiement d’équipes via les applications 365 Microsoft pour les entreprises

Pour en savoir plus sur les équipes et les applications 365 Microsoft pour les entreprises, voir [Comment exclure des équipes de nouvelles installations des applications microsoft 365 pour l’entreprise](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) et [utiliser une stratégie de groupe pour contrôler l’installation d’teams](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déploiement de l’application de bureau teams sur l’ordinateur virtuel

1. Téléchargez le package MSI teams qui correspond à votre système d’exploitation VM VDI en utilisant l’un des liens suivants :

    - [version 32 bits](https://statics.teams.cdn.office.net/production-windows/1.3.00.21759/Teams_windows.msi)
    - [version 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.3.00.21759/Teams_windows_x64.msi)

    La version minimum de l’application de bureau teams requise est la version 1.3.00.4461. (La conservation RTC n’est pas prise en charge dans les versions antérieures.)

2. Installez le MSI sur la machine virtuelle VDI en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Ce processus est l’installation par défaut, qui installe teams sur le dossier% AppData% User. À ce stade, la configuration de l’image Golden est terminée. Teams ne fonctionne pas correctement avec une installation par utilisateur sur une configuration non persistante.

    - Installation par ordinateur

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Ce processus installe teams vers le dossier Program Files (x86) sur un système d’exploitation 64 bits et le dossier Program Files sur un système d’exploitation 32 bits. À ce stade, la configuration de l’image Golden est terminée. L’installation d’équipes par machine est requise pour les configuration non persistantes.

        La prochaine session interactive de connexion démarre teams et demande des informations d’identification.

        > [!NOTE]
        > Ces exemples utilisent également le paramètre **ALLUSERS = 1** . Lorsque vous définissez ce paramètre, le programme d’installation à l’échelle de l’entreprise teams apparaît dans programmes et fonctionnalités dans le panneau de configuration et dans applications & fonctionnalités dans les paramètres Windows de tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent alors désinstaller teams s’ils possèdent des informations d’identification d’administrateur.
        Il est important de comprendre la différence entre **ALLUSERS = 1** et **ALLUSER = 1**. Le paramètre **ALLUSERS = 1** peut être utilisé dans les environnements non-VDI et VDI, alors que le paramètre **ALLUSER = 1** est utilisé uniquement dans les environnements VDI pour spécifier une installation par ordinateur.

3. Désinstaller le MSI de l’ordinateur virtuel VDI.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Ce processus désinstalle les équipes du dossier Program Files (x86) ou Program Files, en fonction de l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Considérations relatives aux performances d’une équipe sur VDI

Il existe de nombreuses configurations virtualisées, chacune ayant un focus différent sur l’optimisation. Par exemple, une configuration peut se focaliser sur la densité utilisateur. Lors de la planification, prenez en compte les éléments suivants pour vous aider à optimiser votre configuration en fonction de la charge de travail de votre organisation.

- Configuration minimale : certaines charges de travail peuvent nécessiter une configuration qui utilise des ressources inférieures à la configuration minimale requise. Par exemple, les charges de travail pour les développeurs qui utilisent des applications qui nécessitent plus de ressources informatiques.
- Dépendances : il s’agit de dépendances en matière d’infrastructure, de charge de travail et d’autres aspects environnementaux extérieurs à l’application de bureau Teams.
- Fonctionnalités désactivées sur VDI : teams désactive les fonctionnalités gourmandes en GPU pour VDI, ce qui permet d’améliorer l’utilisation de l’UC temporaire. Les fonctionnalités suivantes sont désactivées :
    - Animation CSS teams
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Équipes sur VDI avec les appels et les réunions

En plus des discussions et de la collaboration, les équipes sur VDI utilisant les appels et les réunions sont disponibles avec des plateformes de fournisseurs de virtualisation prises en charge. Les fonctionnalités prises en charge sont basées sur la mise en œuvre de la pile multimédia WebRTC et du fournisseur de virtualisation. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant les équipes dans l’architecture VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si vous exécutez actuellement des équipes sans optimisation AV dans l’infrastructure VDI et que vous utilisez des fonctionnalités qui ne sont pas encore prises en charge pour l’optimisation (telles que l’octroi et la prise de contrôle lors du partage d’application), vous devez définir les stratégies du fournisseur de virtualisation pour désactiver la redirection d’équipes. Cela signifie que les sessions multimédias des équipes ne sont pas optimisées. Pour plus d’informations sur la façon de définir des stratégies pour désactiver la redirection d’équipes, contactez votre fournisseur de virtualisation.

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

- L’interface de diffusion audio et vidéo peut ne pas être optimale. Les utilisateurs peuvent rencontrer des retards ou une qualité réduite.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des appareils est gérée par le biais du navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Il peut également être nécessaire de définir les paramètres de l’appareil dans la gestion des appareils Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur un VDI avec les discussions et la collaboration

Si votre organisation veut uniquement utiliser les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies en utilisant le centre d’administration Microsoft teams ou PowerShell. L’exécution de la stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez dans quelques heures.

[**Politiques d’appel**](teams-calling-policy.md): teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent des équipes dans un environnement virtualisé.

[**Stratégies de réunion**](meeting-policies-in-teams.md): teams inclut la stratégie de réunion AllOff intégrée dans laquelle les fonctionnalités de réunion sont désactivées. Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent des équipes dans un environnement virtualisé.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du centre d’administration Microsoft teams

Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff à un utilisateur, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **stratégie d’appel**, cliquez sur **DisallowCalling**.
    2.  Sous **stratégie de réunion**, cliquez sur **AllOff**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la stratégie que vous voulez attribuer. Par exemple :
    - Accédez à **Voice**  >  **stratégies d’appel**vocal, puis cliquez sur **DisallowCalling**.
    - Accédez à **Meetings**  >  **stratégies de réunion**, puis cliquez sur **AllOff**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez la rubrique [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migration des équipes sur l’infrastructure VDI grâce aux discussions et à la collaboration pour optimiser les équipes grâce aux appels et aux réunions

Si vous disposez d’une implémentation de teams sur VDI avec les fonctionnalités de conversation et de collaboration dans lesquelles vous avez défini des stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion et que vous effectuez une migration à l’aide de l’optimisation AV, vous devez définir des stratégies pour activer les fonctionnalités d’appel et de réunion pour ces équipes sur les utilisateurs de VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer les fonctionnalités d’appel et de réunion

Vous pouvez utiliser le centre d’administration Microsoft teams ou PowerShell pour définir et affecter des stratégies d’appel et de réunion à vos utilisateurs. Le temps nécessaire pour que les modifications de la stratégie soient propagées peut prendre un certain temps. Si vous ne voyez pas les modifications pour un compte donné immédiatement, réessayez après quelques heures.

Politiques d' [**appel**](teams-calling-policy.md): les stratégies d’appel en équipe contrôlent les fonctionnalités d’appel disponibles aux utilisateurs. Teams inclut la stratégie d’appel AllowCalling intégrée dans laquelle toutes les fonctions d’appel sont activées. Pour activer toutes les fonctions d’appel, affectez la stratégie AllowCalling. Vous pouvez créer une stratégie d’appel personnalisée pour activer les fonctions d’appel que vous souhaitez attribuer à vos utilisateurs. 

[**Stratégies**](meeting-policies-in-teams.md)de la réunion : les stratégies de réunion dans les équipes contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles pour les participants à la réunion, qui sont planifiés par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion intégrée de la réunion, dans laquelle toutes les fonctions de réunion sont activées. Pour activer toutes les fonctionnalités de réunion, affectez la stratégie d’activation. Vous pouvez créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion de votre choix et les affecter à des utilisateurs.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du centre d’administration Microsoft teams

Pour affecter la stratégie d’appel AllowCalling et la stratégie de réunion inconforme à un utilisateur, procédez comme suit :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **stratégie d’appel**, cliquez sur **AllowCalling**.
    2.  Sous **stratégie de réunion**, **cliquez sur**inverser.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur l' **&#x2713;** (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à la stratégie que vous voulez attribuer. Par exemple :
    - Accédez à **Voice**  >  **stratégies d’appel**vocal, puis cliquez sur **AllowCalling**.
    - Accédez à **Meetings**  >  stratégies de réunion, puis cliquez sur **AllOn****intentn**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel AllowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser l' [autorisation Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion d’autorisation à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez la rubrique [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Contrôle du mode de secours dans teams

Lorsque les utilisateurs se connectent à partir d’un point de terminaison non pris en charge, les utilisateurs sont en mode de secours, dans lesquels l’AV n’est pas optimisé. Vous pouvez désactiver ou activer le mode Fallback en définissant l’une des valeurs DWORD de Registre suivantes :

- HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER \SOFTWARE\Microsoft\Office\Teams\DisableFallback

Pour désactiver le mode de basculement, définissez la valeur sur **1**. Pour activer l’audio uniquement, définissez la valeur sur **2**. Si la valeur n’est pas présente ou est égale à **0** (zéro), le mode de secours est activé.

Cette fonctionnalité est disponible dans teams version 1.3.00.13565 et les versions ultérieures.

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

### <a name="client-deployment-installation-and-setup"></a>Déploiement de clients, installation et configuration

- Dans le cas d’une installation par ordinateur, teams sur VDI n’est pas automatiquement mis à jour de la même manière que les clients teams de l’infrastructure non VDI. Vous devez mettre à jour l’image de l’ordinateur virtuel en installant un nouveau MSI comme décrit dans la section [installation ou mise à jour de l’application de bureau teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- Teams doit être déployée par l’utilisateur ou par machine. Le déploiement d’équipes pour le déploiement simultané par utilisateur et par ordinateur n’est pas pris en charge. Pour effectuer une migration à partir de l’une ou l’autre de ces modes par poste de passe, suivez la procédure de désinstallation et redéployez en mode.
- Pour le moment, les utilisateurs de bureau virtuel et de VMware ne prennent pas en charge les clients MacOS et Linux.
- Citrix ne prend pas en charge les clients MacOs pour le moment.
- Citrix ne prend pas en charge l’utilisation de proxys HTTP explicites définis sur un point de terminaison.

### <a name="calling-and-meetings"></a>Appels et réunions

Les fonctionnalités d’appel et de réunion suivantes ne sont pas prises en charge :

- Amélioration des services d’urgence
- Boutons HID et contrôles LED entre l’application et les appareils teams
- Effets et atténuation d’arrière-plan
- Rôles de présentateur et de producteur d’événement de diffusion
- Routage basé sur l’emplacement (LBR)
- Parcage d'appel
- File d’attente d’appels
- Son de l’ordinateur du système partagé
- Contournement de média pour le routage Direct

> [!NOTE]
> Nous travaillons actuellement pour ajouter des fonctionnalités d’appel et de réunion qui ne sont disponibles que dans les environnements non-VDI. Il peut s’agir de davantage de contrôle d’administration sur la qualité, de scénarios de partage d’écran supplémentaires et de fonctionnalités avancées récemment ajoutées à Teams. Contactez votre représentant pour en savoir plus sur les fonctionnalités à venir.

Vous trouverez ci-après des problèmes connus et des limitations relatives aux appels et aux réunions :

- L’interopérabilité avec Skype entreprise est limité aux appels audio. Il n’y a pas de modalité vidéo.
- Un seul flux vidéo entrant est pris en charge dans les réunions ou les appels de groupe. Lorsque plusieurs personnes envoient de la vidéo, seule la vidéo dominante de haut-parleur est affichée à tout moment.
- La résolution du flux vidéo entrant et sortant est limitée à la résolution 720p. Il s’agit d’une limitation WebRTC.
- Un seul flux vidéo à partir d’un appareil photo ou d’un flux de partage d’écran entrant est pris en charge. Lorsque le partage d’écran est reçu, ce partage d’écran est affiché, au lieu de la vidéo de l’intervenant dominant.
- Partage d’écran sortant :
    - Le partage d’applications n’est pas pris en charge.
- Donnez le contrôle et prenez le contrôle :
    - Non pris en charge lors d’une session de partage d’écran ou d’application.
    - Pris en charge lors d’une session de partage PowerPoint.
- Limitations de Citrix uniquement
    - L’interaction DTMF (multifrequency multifrequency) avec des systèmes de téléphonie n’est actuellement pas prise en charge.
    - Lorsque le partage d’écran est configuré dans une configuration à plusieurs moniteurs, seul le moniteur principal est partagé.
    - La mise à l’échelle PPP élevée sur CWA n’est pas prise en charge.

Pour les problèmes connus qui ne sont pas liés à VDI, voir [équipe de support au sein de votre organisation](Known-issues.md).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes liés aux composants Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloque ou l’écran de connexion de teams est vide

Il s’agit d’un problème connu de la version d' 1906 et 1909 du Citrix. Pour contourner ce problème, ajoutez la valeur DWORD de Registre suivante, puis définissez-la sur 204 (hexadécimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Ensuite, redémarrez VDA. Pour plus d’informations, reportez-vous à cet article du support Citrix intitulé [résolution des problèmes d’optimisation HDX pour teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Sujets associés

- [Installation de Microsoft teams à l’aide de MSI](msi-deployment.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser Microsoft teams sur le bureau virtuel Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
