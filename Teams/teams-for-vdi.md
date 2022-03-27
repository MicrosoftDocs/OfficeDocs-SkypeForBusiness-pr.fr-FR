---
title: Teams pour l’Infrastructure de bureau virtualisée (VDI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Découvrez comment exécuter une Microsoft Teams dans un environnement VDI (Virtualized Desktop Infrastructure).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0f2364471b3800042e7536d1013b82d76209a02
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64457067"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour l’Infrastructure de bureau virtualisée (VDI)

Cet article décrit les exigences et les limitations de l’utilisation de Microsoft Teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce que VDI ?

L’infrastructure VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation de bureau et des applications sur un serveur centralisé dans un centre de données. Cela permet aux utilisateurs d’une source centralisée complète et conforme d’obtenir une expérience de bureau complète et personnalisée.

Teams dans un environnement virtualisé prend en charge la conversation et la collaboration. Par ailleurs, grâce aux plateformes Azure Virtual Desktop, Citrix et VMware, les fonctionnalités d’appel et de réunion sont également pris en charge.

Teams prend également en charge plusieurs configurations dans des environnements virtuels. Il s’agit de modes VDI, dédiés, partagés, persistants et non persistants. Les fonctionnalités sont en développement continu et sont régulièrement ajoutées, et elles seront étendues au fil du temps.

L Teams dans un environnement virtualisé peut être quelque peu différent de l’utilisation de Teams dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées peuvent ne pas être disponibles dans un environnement virtualisé, et la résolution vidéo peut différer.

Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

> [!Note]
> Pour plus d’informations sur Teams VDI sur différentes plateformes, voir Teams [fonctionnalités par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams sur des composants VDI

L’Teams dans un environnement virtualisé nécessite les composants suivants.

- **Courtier en virtualisation** : gestionnaire de ressources et de connexions du fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel** : pile de machines virtuelles qui s’Teams
- **Client fin** : appareil avec qui l’utilisateur interface physiquement
- **Teams de bureau :** application Teams client de bureau Windows

## <a name="teams-on-vdi-requirements"></a>Teams la exigences VDI

### <a name="virtualization-provider-requirements"></a>Exigences du fournisseur de virtualisation

L Teams de bureau a été validée avec les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous recommandons de consulter votre fournisseur de solutions de virtualisation pour vous assurer que vous répondez aux conditions minimales requises.
  
Actuellement, les Teams sur VDI avec l’optimisation audio/vidéo (AV) sont certifiées avec Azure Virtual Desktop, Citrix et VMware. Examinez les informations de cette section pour vous assurer que vous respectez toutes les conditions requises pour utiliser les fonctionnalités adéquates.

### <a name="platforms-certified-for-teams"></a>Plateformes certifiées pour Teams

Les plateformes suivantes ont des solutions d’infrastructure de bureau virtuel pour Teams.

|Plateforme|Solution|
|----|---|
|![Logo représentant Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Bureau virtuel Azure</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Logo représentant Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Applications et bureaux virtuels Citrix</a> |
|![Logo représentant VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Bureau virtuel Azure

Azure Virtual Desktop permet d’optimiser AV pour Teams sur VDI. Pour en savoir plus sur la exigences et l’installation, voir [Utiliser Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 utilise l’optimisation AV fournie par Azure Virtual Desktop pour garantir une expérience optimale Teams des PC Cloud. Pour en savoir plus sur la exigences et l’installation, voir [Utiliser Teams cloud PC](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops requirements

Citrix Virtual Apps and Desktops (anciennement XenApp et XenDesktop) fournit l’optimisation d’AV pour les Teams sur VDI. Avec Citrix Virtual Apps et Desktops, Teams sur VDI prend en charge les fonctionnalités d’appel et de réunion en plus de la conversation et de la collaboration.

Vous pouvez télécharger la dernière version des applications et bureaux virtuels Citrix sur le [site de téléchargements de Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Vous devez tout d’abord vous connectez.) Les composants nécessaires sont regroupés dans l’application [Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’agent de remise virtuelle (VDA) par défaut. Vous n’avez pas besoin d’installer d’autres composants ou plug-ins sur CWA ou VDA.

Pour obtenir les dernières exigences en matière de serveur et de client, voir l’article [Optimisation Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) sur le site web Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace and Desktop requirements

VMware Horizon est une plateforme moderne qui offre une livraison sécurisée des bureaux et applications virtuels dans le cloud hybride. Pour offrir une expérience excellente aux utilisateurs finaux, VMware Horizon offre une optimisation des médias pour Teams. Cette optimisation améliore la productivité globale sur les bureaux virtuels et les applications, et améliore l’expérience utilisateur lors des appels et des réunions à l’aide Teams.

Vous pouvez télécharger la dernière version de VMware Horizon à partir de la page [Téléchargements de VMware](https://customerconnect.vmware.com/downloads/#all_products) . Les composants d’optimisation multimédia requis font partie de l’agent Horizon et du client Horizon par défaut et il n’est pas nécessaire d’installer de plug-in supplémentaire pour utiliser la fonctionnalité d’optimisation de Teams.

Pour obtenir les dernières exigences et instructions sur la configuration de l’optimisation des médias pour Teams, consultez l’article Configuration de l’optimisation des médias pour [Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) sur le site web VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installer ou mettre à jour l Teams de bureau en environnement VDI

Vous pouvez déployer l’Teams de bureau pour VDI à l’aide d’une installation par ordinateur ou par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser dépend de l’utilisation d’une configuration permanente ou non permanente et des besoins en fonctionnalités associés de votre organisation.

Pour une installation permanente dédiée, l’installation par ordinateur et par utilisateur fonctionne. Toutefois, pour une installation sans Teams, une installation par ordinateur est nécessaire pour fonctionner efficacement. Consultez la section [configuration non](#non-persistent-setup) permanente.

Avec l’installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour Teams’application, vous devez désinstaller la version actuelle pour la mettre à jour vers une version plus récente. Avec l’installation par utilisateur, les mises à jour automatiques sont activées.

Pour la plupart des déploiements VDI, nous vous recommandons de Teams l’installation par ordinateur. Pour mettre à jour vers la dernière version Teams, commencez par la procédure de désinstallation suivie de la dernière Teams version de déploiement.

Pour Teams optimisation AV dans les environnements VDI fonctionnent correctement, l’appareil fin client doit avoir accès à Internet. Si l’accès Internet n’est pas disponible sur l’appareil fin client, l’optimisation du démarrage ne réussira pas. Cela signifie que l’utilisateur se trouve dans un état multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Configuration permanente dédiée

Dans une installation permanente dédiée, les modifications apportées au système d’exploitation local des utilisateurs sont conservées une fois que les utilisateurs se déconnectent. Pour la configuration permanente, Teams prend en charge l’installation par utilisateur et par ordinateur.

Voici la configuration VM minimale recommandée.

|Paramètre  |Système d’exploitation de station de travail  |Système d’exploitation serveur  |
|---------|---------|---------|
|vCPU   |    2 cœurs     |  4, 6 ou 8 cœurs<br>Il est important de comprendre la configuration sous-jacente de l’accès mémoire non uniforme (NUMA) et de configurer vos VM en conséquence.     |
|Mémoire RAM     |   4 Go      | 512 Mo à 1 Go par utilisateur        |
|Stockage    | 8 Go        | 40 Go à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non permanente

Dans une configuration non permanente, les modifications apportées au système d’exploitation local des utilisateurs ne sont pas conservées une fois que les utilisateurs se déconnectent. De telles configurations sont généralement partagées entre utilisateurs. La configuration de la VM varie en fonction du nombre d’utilisateurs et des ressources de serveur physique disponibles.

Pour une configuration non permanente, l’application de bureau Teams doit être installée par ordinateur sur l’image d’or. Cela garantit un lancement efficace de l’Teams pendant une session utilisateur. Pour en savoir plus, consultez la section [Installer ou mettre à jour Teams l’application de bureau sur VDI](#install-or-update-the-teams-desktop-app-on-vdi).

L’Teams dans une configuration non permanente nécessite également un gestionnaire de mise en cache de profil pour une synchronisation efficace des données Teams runtime. Une synchronisation efficace des données garantit la mise en cache des informations spécifiques de l’utilisateur (telles que les données, le profil ou les paramètres d’un utilisateur) pendant la session de l’utilisateur. Assurez-vous que les données de ces deux dossiers sont synchronisées :<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Un dossier d’itinérance (ou, si vous utilisez la redirection de dossiers, un gestionnaire de mise en cache) est nécessaire pour vous assurer que l’application Teams possède les données et fichiers d’runtime requis pour exécuter l’application. Ceci est nécessaire pour réduire les problèmes de latence réseau ou les problèmes réseau, ce qui entraînerait des erreurs d’application et une expérience lente en raison de données et de fichiers indisponibles.

Diverses solutions de gestionnaire de mise en cache sont disponibles, [telles que FSLogix](/fslogix/overview). Pour obtenir des instructions de configuration spécifiques, consultez le fournisseur du Gestionnaire de mise en cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Teams d’exclusion de contenu mis en cache dans le cas d’une configuration non permanente

Excluez ce qui suit du Teams de mise en cache, `%AppData%/Microsoft/Teams`. En excluant ces éléments, vous réduisez la taille de la mise en cache des utilisateurs pour optimiser votre configuration non permanente.

- .txt fichiers
- Dossier de pile de médias
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Applications Microsoft 365 pour les grandes entreprises considérations

Prenons les considérations suivantes lorsque vous Teams des Applications Microsoft 365 pour les grandes entreprises sur VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nouveaux déploiements de déploiements Teams’Applications Microsoft 365 pour les grandes entreprises

Avant de déployer Teams via Applications Microsoft 365 pour les grandes entreprises, vous devez désinstaller les applications Teams existantes si elles ont été déployées via une installation par ordinateur.

Teams via Applications Microsoft 365 pour les grandes entreprises est installé par utilisateur. Pour en savoir plus, consultez la section [Installer ou mettre à jour Teams l’application de bureau sur VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Teams des déploiements via Applications Microsoft 365 pour les grandes entreprises mises à jour

Teams des installations existantes d’Applications Microsoft 365 pour les grandes entreprises. Étant donné Applications Microsoft 365 pour les grandes entreprises uniquement les Teams utilisateurs, consultez la section Installer ou mettre à jour l’application Teams [bureau sur VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Utilisation d Teams avec l’installation par ordinateur et la Applications Microsoft 365 pour les grandes entreprises

Applications Microsoft 365 pour les grandes entreprises ne prend pas en charge les installations par ordinateur d’Teams. Pour utiliser une installation par ordinateur, vous devez exclure l’Teams de Applications Microsoft 365 pour les grandes entreprises. Consultez [l’application Teams de bureau](#deploy-the-teams-desktop-app-to-the-vm) pour la messagerie automatique et comment exclure un déploiement [Teams’Applications Microsoft 365 pour les grandes entreprises](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Comment exclure un déploiement Teams via Applications Microsoft 365 pour les grandes entreprises

Pour en savoir plus sur Teams et Applications Microsoft 365 pour les grandes entreprises, voir Comment exclure Teams de nouvelles [installations d’Applications Microsoft 365 pour les grandes entreprises](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) et [utiliser une stratégie de groupe pour contrôler l’installation d’Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déployer l’Teams de bureau sur la messagerie vm

1. Téléchargez le Teams package MSI qui correspond à votre système d’exploitation VDI VM à l’aide de l’un des liens suivants :

    - [Version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Dans le cas des nuages du gouvernement, consultez [l’Teams en bloc Windows installer (MSI)](msi-deployment.md) pour consulter les liens de téléchargement vers les fichiers MSI.

    La version minimale de Teams de bureau requise est la version 1.3.00.4461. La prise en charge PSTN n’est pas prise en charge dans les versions antérieures.

2. Installez le MSI sur la VDI VM en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Ce processus est l’installation par défaut, qui Teams au dossier `%AppData%` utilisateur. À ce stade, la configuration de l’image dorée est terminée.

        > [!IMPORTANT]
        > Teams ne fonctionne pas correctement avec l’installation par utilisateur sur une configuration non permanente.

    - Installation par ordinateur

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Ce processus ajoute une clé de Registre requise à l’ordinateur, qui permet au Teams de savoir qu’il s’agit d’une instance VDI.  Sans ce dernier, le programme d’installation échouera, en indiquant : « L’installation a échoué.  Installation impossible pour tous les utilisateurs lorsqu’un environnement VDI n’est pas détecté. »

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Ce processus installe Teams au dossier sur un système d’exploitation 64 bits `%ProgramFiles(x86)%` `%ProgramFiles%` et au dossier sur un système d’exploitation 32 bits. À ce stade, la configuration de l’image dorée est terminée.

        > [!IMPORTANT]
        >  L’Teams’installation par ordinateur est requise pour les configurations sans permanente.

        Lorsque la prochaine session d’ouverture de session interactive commence, Teams vous demande les informations d’identification.

        > [!NOTE]
        > Ces exemples utilisent également le `ALLUSERS=1` paramètre. Lorsque vous définissez ce paramètre, **Teams Machine-Wide Installer** s’affiche dans  Programmes et fonctionnalités  du Panneau de &  et dans les fonctionnalités & dans **Windows Paramètres** pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams’ils ont des informations d’identification d’administrateur.
        >
        > Il est important de comprendre la différence entre `ALLUSERS=1` et `ALLUSER=1`. Le `ALLUSERS=1` paramètre peut être utilisé dans des environnements non VDI et VDI, `ALLUSER=1` tandis que le paramètre est utilisé uniquement dans les environnements VDI pour spécifier une installation par ordinateur.

3. Désinstallez le MSI de la VDI VDI VM. Il existe deux façons de désinstaller Teams.

    - **Script PowerShell** : vous pouvez utiliser le script de nettoyage [de Teams](scripts/powershell-script-deployment-cleanup.md) PowerShell pour désinstaller Teams et supprimer le dossier Teams d’un utilisateur. Exécutez le script pour chaque profil utilisateur dans lequel Teams été installé sur l’ordinateur.
    - **Ligne de commande** : exécutez la commande suivante.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Ce processus désinstalle Teams dossier `%ProgramFiles(x86)%` `%ProgramFiles%`, selon l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Teams considérations en ce qui Teams sur les performances VDI

Il existe plusieurs configurations de configuration virtualisées, avec une attention différente pour l’optimisation. Par exemple, une configuration peut se concentrer sur la densité d’utilisateurs. Lors de la planification, envisagez les opérations suivantes pour optimiser votre configuration en fonction des besoins de charge de travail de votre organisation.

- **Configuration minimale requise** : certaines charges de travail peuvent nécessiter une configuration à l’aide de ressources qui dépassent la configuration minimale requise. Par exemple, les charges de travail des développeurs qui utilisent des applications qui demandent plus de ressources informatiques.
- **Dépendances :** il peut s’agir de dépendances en relation avec l’infrastructure, la charge de travail et d’autres considérations environnementales en dehors de l Teams de bureau.
- **Fonctionnalités désactivées sur VDI** : Teams fonctionnalités intensives de l’UC pour une utilisation VDI qui peuvent contribuer à améliorer l’utilisation intensive de l’UC. Les fonctionnalités suivantes sont désactivées :
    - Teams animation CSS
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams sur VDI avec des appels et des réunions

Outre la conversation et la collaboration, les Teams sur VDI avec les appels et les réunions sont disponibles avec les plateformes de fournisseurs de virtualisation pris en charge. Les fonctionnalités prise en charge sont basées sur la pile de médias WebRTC et l’implémentation du fournisseur de virtualisation. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant l Teams sur l’architecture VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si vous exécutez actuellement des Teams sans optimisation AV dans VDI et que vous utilisez des fonctionnalités qui ne sont pas encore pris en charge pour l’optimisation (telles que Donner et prendre le contrôle du partage d’application), vous devez définir les stratégies des fournisseurs de virtualisation pour désactiver Teams redirection. Cela signifie que Teams sessions multimédias ne seront pas optimisées. Pour savoir comment définir des stratégies pour désactiver Teams redirection, contactez votre fournisseur de virtualisation.

### <a name="network-requirements"></a>Configuration réseau requise

Nous vous recommandons d’évaluer votre environnement afin d’identifier les risques et les exigences qui peuvent influencer votre déploiement voix et vidéo dans le cloud dans son ensemble. Utilisez [l’Skype Entreprise d’évaluation du](https://www.microsoft.com/download/details.aspx?id=53885) réseau pour tester si votre réseau est prêt à Teams.

Pour en savoir plus sur la préparation de votre réseau pour l’Teams, voir Préparer le réseau de votre organisation [pour l’Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrer d Skype Entreprise d’une équipe VDI vers Teams VDI

Si vous migrez de Skype Entreprise sur VDI vers Teams sur un VDI, outre les différences entre les deux applications, il existe quelques différences lorsque VDI est également implémenté. Certaines fonctionnalités actuellement non pris en charge dans Teams VDI disponibles dans Skype Entreprise VDI sont les suivantes :

- Stratégie par plate-forme pour la désactivation de certaines fonctionnalités AV dans VDI
- Donner et prendre le contrôle lors du partage d’application
- Partage d’écran à partir d’une conversation sans son
- Envoi et réception simultanés de vidéos et de partages d’écran

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams dans le navigateur Chrome et dans l Teams appe de bureau pour VDI

Teams navigateur Chrome ne remplace pas l’application de bureau Teams pour VDI par l’optimisation AV. L’expérience de conversation et de collaboration fonctionne comme prévu. Lorsque des médias sont nécessaires, certaines expériences peuvent ne pas répondre aux attentes des utilisateurs sur le navigateur Chrome :

- L’expérience de diffusion en continu audio et vidéo n’est peut-être pas optimale. Les utilisateurs peuvent faire l’expérience de retards ou d’une qualité réduite.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des périphériques est gérée via le navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Il se peut que les paramètres des appareils doivent également être réglés dans Windows gestion des appareils.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur VDI avec la conversation et la collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Teams d’administration de l’entreprise ou de PowerShell. La propagation des modifications de stratégie peut prendre quelques heures. Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau dans quelques heures.

[**Polices d’appel**](teams-calling-policy.md) : Teams inclut la stratégie d’appel **DisallowCalling** intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez **la stratégie DisallowCalling** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de**](meeting-policies-overview.md) réunion : Teams inclut la stratégie de réunion **AllOff** intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez **la stratégie AllOff** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Teams d’administration

Pour affecter la stratégie **d’appel DisallowCalling** et la stratégie de **réunion AllOff** à un utilisateur :

1. Dans le panneau de navigation gauche du Teams d’administration, allez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, cliquez **sur DisallowCalling**.
    2. Sous **Stratégie de réunion**, cliquez **sur AllOff**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le panneau de navigation de gauche du Teams d’administration, allez dans Utilisateurs **, puis** recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs que vous souhaitez.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez **sur&#x2713;** (coche) dans la partie supérieure du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également :

1. Dans le navigation gauche du Teams d’administration, allez à la stratégie que vous voulez attribuer. Par exemple :
    - Consultez **les stratégies** **VoiceCalling** > , puis cliquez **sur DisallowCalling**.
    - Consultez **les stratégies** **MeetingsMeeting** > , puis cliquez **sur AllOff**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter `DisallowCalling` la stratégie d’appel à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOff` pour affecter la stratégie de réunion à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrer des Teams sur un VDI avec la conversation et la collaboration afin d’optimiser Teams avec les appels et les réunions

Si vous avez déjà mis en œuvre des Teams sur VDI avec la conversation et la collaboration dans lesquelles vous avez définie des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion, et que vous migrez vers Teams avec l’optimisation AV, vous devez définir des stratégies pour activer les fonctionnalités d’appel et de réunion pour ces Teams sur les utilisateurs VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer les fonctionnalités d’appel et de réunion

Vous pouvez utiliser le centre Teams d’administration de l’entreprise ou PowerShell pour définir et affecter des stratégies d’appel et de réunion à vos utilisateurs. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau après quelques heures.

[**Polices d’appel : les stratégies**](teams-calling-policy.md) d Teams contrôlent quelles fonctionnalités d’appel sont disponibles pour les utilisateurs. Teams inclut la stratégie d’appel **AllowCalling** intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Pour activer toutes les fonctionnalités d’appel, affectez **la stratégie AllowCalling** . Vous pouvez également créer une stratégie d’appel personnalisée pour activer les fonctionnalités d’appel de votre souhaitez et les affecter aux utilisateurs.

[**Stratégies de**](meeting-policies-overview.md) réunion : les stratégies de réunion dans Teams contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles aux participants à la réunion qui sont prévues par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion **AllOn** intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Pour activer toutes les fonctionnalités de réunion, affectez **la stratégie AllOn** . Vous pouvez également créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion que vous souhaitez et affecter aux utilisateurs.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Teams d’administration

Pour affecter la **stratégie d’appel AllowCalling** et la stratégie **de réunion AllOn** à un utilisateur :

1. Dans le panneau de navigation gauche du Teams d’administration, allez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, **cliquez sur AllowCalling**.
    2. Sous **Stratégie de réunion**, cliquez **sur AllOn**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le panneau de navigation de gauche du Teams d’administration, allez dans Utilisateurs **, puis** recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs que vous souhaitez.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez **sur&#x2713;** (coche) dans la partie supérieure du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également :

1. Dans le navigation gauche du Teams d’administration, allez à la stratégie que vous voulez attribuer. Par exemple :
    - Consultez **les stratégies** **VoiceCalling** > , puis cliquez **sur AllowCalling**.
    - Allez dans **Stratégies MeetingsMeeting** > , puis cliquez sur **AllOn**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter `AllowCalling` la stratégie d’appel à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) `AllOn` pour affecter la stratégie de réunion à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Contrôler le mode de récupération dans Teams

Lorsque les utilisateurs se connectent à partir d’un point de terminaison non pris en compte, ils sont en mode de récupération, dans lequel AV n’est pas optimisé. Vous pouvez désactiver ou activer le mode de récupération en setting une des valeurs de Registre suivantes `DWORD` :

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Pour désactiver le mode de récupération, définissez la valeur **1**. Pour activer l’audio uniquement, définissez la valeur **sur 2**. Si la valeur n’est pas présente ou est définie sur **0** (zéro), le mode de récupération est activé.

Cette fonctionnalité est disponible dans Teams version 1.3.00.13565 et ultérieures.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Désactiver les paramètres audio et vidéo pour VDI

Teams stratégies VDI sont disponibles dans le module Teams’équipe. Ces stratégies sont actives et appliquées sur des environnements VDI non optimisés.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Cela s’agit uniquement pour les environnements non optimisés.

### <a name="update-a-module-name"></a>Mettre à jour le nom d’un module

```PowerShell
Update-Module -Name MicrosoftTeams -AllowPrerelease

<# Import and connect to online (CSOnline runs the policies) #>
Import-Module microsoftTeams
if( -not $sess){
    $session = New-CsOnlineSession
    $pss = Import-PSSession $session
}
<# Check out the commands #>
Get-Command -Noun *VDI*
<#
```

### <a name="set-policies-to-limit-calling-features"></a>Définir des stratégies pour limiter les fonctionnalités d’appel

Lorsque les utilisateurs dont la stratégie VDI `DisableCallsAndMeetings` est définie pour `$true` se Teams sur VDI, ils ne peuvent pas :

- Appels.
- Participez à des réunions.
- Partage d’écran à partir de la conversation.

Tous les types d’appels doivent être désactivés.

> [!NOTE]
> Cela s’agit uniquement pour les environnements non optimisés.

```PowerShell
New-CsTeamsVdiPolicy -Identity DisableCallsAndMeetingsTrue -DisableCallsAndMeetings $true -DisableAudioVideoInCallsAndMeetings $false

<# Assign policy #>
$user = 'meganb@jvteams.xyz'
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName DisableCallsAndMeetingsTrue

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -Identity $user | FL UserPrincipalName, *vdi*

<# Show all policies #>
Get-CsTeamsVdiPolicy | FT Iden*, Disable*
```

Lorsque les utilisateurs dont la stratégie VDI `DisableAudioVideoInCallsAndMeetings` est définie pour `$true` se Teams à une VDI, ils :

- Peut partager un écran à partir de la conversation.
- Peut participer à une réunion et partager un écran et déplacer son audio vers un téléphone.
- Vous ne pouvez pas organiser d’appels audio et vidéo de personne à personne à partir d’une équipe VDI.

> [!NOTE]
> Cela s’agit uniquement pour les environnements non optimisés.

```powershell
$PolName = "DisableCallsAndMeetingsAV"

New-CsTeamsVdiPolicy -Identity $PolName -DisableCallsAndMeetings $false -DisableAudioVideoInCallsAndMeetings $true
Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $PolName

<# Wait for some time until the policy is applied #>
Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

<# Cleanup afterwards #>
$cleanup = $false
if($cleanup){

    "Doing cleanup"

    # De-assign policy from user  
    Grant-CsTeamsVdiPolicy -Identity $user -PolicyName $null
    Get-CSOnlineUser -identity $user | FL UserPrincipalName, *vdi*

    # Remove policies
    Get-CsTeamsVdiPolicy | ?{$_.identity -ne 'Global'} | remove-csTeamsVdiPolicy
}
```

## <a name="known-issues-and-limitations"></a>Problèmes et limitations connus

### <a name="client-deployment-installation-and-setup"></a>Déploiement, installation et configuration de clients

- Avec l’installation par ordinateur, les Teams sur VDI ne sont pas mises à jour automatiquement comme le sont les clients de Teams-VDI. Vous devez mettre à jour l’image VM en installant un nouveau MSI comme décrit dans la section Installer ou mettre à jour l’application de bureau [Teams sur une version VDI](#install-or-update-the-teams-desktop-app-on-vdi). Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- Dans les environnements Citrix, si l’utilisateur se déconnecte de la machine virtuelle pendant que Teams est en cours d’exécution, les mises à jour Teams peuvent avoir pour effet que l’utilisateur soit dans un état non optimisé pour AV lorsqu’il se reconnecte. Nous recommandons aux utilisateurs de quitter Teams se déconnecter de Citrix Virtual Machine pour éviter ce scénario.
- Teams doivent être déployés par utilisateur ou par ordinateur. Le déploiement de Teams pour les utilisateurs simultanés et par ordinateur n’est pas pris en charge. Pour migrer d’un mode par ordinateur ou par utilisateur vers l’un de ces modes, suivez la procédure de désinstallation et redéployer l’un ou l’autre.
- Pour le moment, Azure Virtual Desktop ne prend pas en charge les clients macOS et Linux.
- Le changement de client rapide peut entraîner des problèmes liés aux appels dans une environnement VDI, tels que le partage d’écran, qui ne sont pas disponibles. Le redémarrage du client permet d’atténuer ces problèmes.

### <a name="notifications"></a>Notifications

- La notification et la présence de nombre de messages dans la barre Windows des tâches n’est pas prise en charge sur Windows Server 2016 hôte.

### <a name="calling-and-meetings"></a>Appels et réunions

Les fonctionnalités d’appel et de réunion suivantes ne sont pas pris en charge :

- Toute fonctionnalité à plusieurs fenêtres telles que les nouvelles expériences de réunion ou toute fonctionnalité qui est livré avec la nouvelle expérience de réunion
- Boutons HID et contrôles LED entre l’application Teams et les appareils pour Citrix et VMware
- Flou et effets d’arrière-plan
- Rôles de producteur et de présentateur de diffusion et d’événement en direct
- Location-Based routage des biens (LBR)
- Sonnerie d’appel PSTN
- Son système/ordinateur partagé
- Contournement de média pour le routage Direct
- Commande Zoom

> [!NOTE]
> Nous travaillons à l’ajout de fonctionnalités d’appel et de réunion qui sont actuellement disponibles uniquement dans les environnements non VDI. Ceux-ci peuvent inclure un contrôle plus administratif sur la qualité, des scénarios de partage d’écran supplémentaires et des fonctionnalités avancées récemment ajoutées Teams. Contactez votre représentant Teams pour en savoir plus sur les fonctionnalités à venir.

Voici des problèmes connus et des limitations pour les appels et les réunions :

- L’interopérabilité Skype Entreprise est limitée aux appels audio ; il n’existe pas de modalité vidéo.
- La résolution des flux vidéo entrants et sortants est limitée à la résolution 720p.
- Un seul flux vidéo d’une caméra ou d’un flux de partage d’écran entrant est pris en charge. Lorsqu’un partage d’écran entrant est partagé, ce partage d’écran s’affiche à la place de la vidéo du principal orateur.
- Teams ne bascule pas pour utiliser le dernier périphérique audio sélectionné par un utilisateur, s’il est déconnecté, puis reconnecté.
- Les événements en direct ne sont pas optimisés.
- Partage d’écran sortant :
  - Le partage d’applications n’est pas pris en charge.
- Prenez le contrôle :
  - Non pris en charge lors d’une session de partage d’écran ou d’application.
  - Prise en charge pendant PowerPoint session de partage.

Pour Teams problèmes connus qui ne sont pas liés à une VDI, consultez le [support Teams dans votre organisation](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes des composants Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se connecte ou l Teams’écran de se connecte est vide

Il s’agit d’un problème connu avec Citrix VDA versions 1906 et 1909. Pour contourner ce problème, ajoutez la valeur de Registre `DWORD` suivante et `204` définissez-la (hexadécimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Redémarrez ensuite VDA. Pour en savoir plus, consultez cet article de support citrix, [qui explique comment résoudre les problèmes d’optimisation HDX pour Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Sujets associés

- [Installer en bloc Teams l’aide Windows programme d’installation en bloc (MSI)](msi-deployment.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser Microsoft Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd)
