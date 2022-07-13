---
title: Teams pour l’Infrastructure de bureau virtualisée (VDI)
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Découvrez comment exécuter Microsoft Teams dans un environnement VDI (Virtualized Desktop Infrastructure).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90e577f9d6ef7567387fbc7a26a944d20e976f66
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773703"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour l’Infrastructure de bureau virtualisée (VDI)

Cet article décrit les exigences et les limitations liées à l’utilisation de Microsoft Teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce que VDI ?

L’infrastructure VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation de bureau et des applications sur un serveur centralisé dans un centre de données. Cela permet une expérience de bureau complète et personnalisée pour les utilisateurs disposant d’une source centralisée entièrement sécurisée et conforme.

Teams dans un environnement virtualisé prend en charge la conversation et la collaboration. Avec les plateformes Azure Virtual Desktop, Citrix et VMware, les fonctionnalités d’appel et de réunion sont également prises en charge.

Teams prend également en charge plusieurs configurations dans des environnements virtuels. Il s’agit notamment des modes VDI, dédiés, partagés, persistants et non persistants. Les fonctionnalités sont en développement continu et sont ajoutées régulièrement, et les fonctionnalités se développeront au fil du temps.

L’utilisation de Teams dans un environnement virtualisé peut être légèrement différente de l’utilisation de Teams dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées peuvent ne pas être disponibles dans un environnement virtualisé, et la résolution vidéo peut différer.

Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

> [!Note]
> Pour plus d’informations sur Teams VDI sur différentes plateformes, consultez [fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams sur les composants VDI

L’utilisation de Teams dans un environnement virtualisé nécessite les composants suivants.

- **Broker de virtualisation** : gestionnaire de ressources et de connexions au fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel** : pile de machines virtuelles qui exécute Teams
- **Client fin** : appareil avec lequel l’utilisateur se connecte physiquement
- **Application de bureau Teams** : application cliente de bureau Teams

## <a name="teams-on-vdi-requirements"></a>Teams sur les exigences VDI

### <a name="virtualization-provider-requirements"></a>Exigences du fournisseur de virtualisation

L’application de bureau Teams a été validée avec les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous recommandons de consulter votre fournisseur de solutions de virtualisation pour vous assurer que vous répondez aux exigences minimales.
  
Actuellement, Teams sur VDI avec optimisation audio/vidéo (AV) est certifié avec Azure Virtual Desktop, Citrix et VMware. Passez en revue les informations contenues dans cette section pour vous assurer que vous répondez à toutes les exigences en matière de fonctionnalités appropriées.

### <a name="platforms-certified-for-teams"></a>Plateformes certifiées pour Teams

Les plateformes suivantes ont des solutions d’infrastructure de bureau virtuel pour Teams.

|Plateforme|Solution|
|----|---|
|![Logo représentant Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Logo représentant Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![Logo représentant VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop fournit une optimisation av pour Teams sur VDI. Pour en savoir plus sur les exigences et l’installation, consultez [Utiliser Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 utilise l’optimisation av fournie par Azure Virtual Desktop pour garantir des expériences Teams optimales à partir des PC cloud. Pour en savoir plus sur les exigences et l’installation, consultez [Utiliser Teams sur le PC cloud](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Configuration requise pour Citrix Virtual Apps and Desktops

Citrix Virtual Apps and Desktops (anciennement XenApp et XenDesktop) offre une optimisation av pour Teams sur VDI. Avec Citrix Virtual Apps and Desktops, Teams sur VDI prend en charge les fonctionnalités d’appel et de réunion en plus de la conversation et de la collaboration.

Vous pouvez télécharger la dernière version de Citrix Virtual Apps and Desktops sur le [site de téléchargement Citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Vous devez d’abord vous connecter.) Les composants nécessaires sont regroupés par défaut dans [l’application d’espace de travail Citrix (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’Agent de remise virtuelle (VDA). Vous n’avez pas besoin d’installer d’autres composants ou plug-ins sur CWA ou VDA.

Pour connaître les dernières exigences du serveur et du client, consultez [l’article Optimisation pour Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) sur le site web Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Configuration requise pour l’espace de travail et le bureau VMware Horizon

VMware Horizon est une plateforme moderne pour la livraison sécurisée de bureaux virtuels et d’applications dans le cloud hybride. Pour offrir une expérience utilisateur final optimale, VMware Horizon assure l’optimisation des médias pour Teams. Cette optimisation améliore la productivité globale sur les bureaux virtuels et les applications, et améliore l’expérience utilisateur lors de l’appel et de la réunion à l’aide de Teams.

Vous pouvez télécharger la dernière version de VMware Horizon à partir de la page [Téléchargements VMware](https://customerconnect.vmware.com/downloads/#all_products) . Les composants d’optimisation multimédia requis font partie de l’agent Horizon et du client Horizon par défaut et il n’est pas nécessaire d’installer un plug-in supplémentaire pour utiliser la fonctionnalité d’optimisation pour Teams.

Pour obtenir les dernières exigences et instructions sur la configuration de l’optimisation des médias pour Teams, consultez l’article [Configuring Media Optimization for Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) sur le site web VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installer ou mettre à jour l’application de bureau Teams sur VDI

Vous pouvez déployer l’application de bureau Teams pour VDI à l’aide d’une installation par ordinateur ou par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser varie selon que vous utilisez une configuration persistante ou non persistante et les besoins en fonctionnalités associés de votre organisation.

Pour une installation permanente dédiée, l’installation par ordinateur et par utilisateur fonctionnera. Toutefois, pour une installation non persistante, Teams requiert une installation par ordinateur pour fonctionner efficacement. Consultez la section [d’installation non persistante](#non-persistent-setup) .

Avec l’installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour l’application Teams, vous devez désinstaller la version actuelle pour la mettre à jour vers une version plus récente. Avec l’installation par utilisateur, les mises à jour automatiques sont activées.

> [!IMPORTANT]
> Maintenez l’application de bureau Teams à jour dans votre environnement VDI. Les versions d’application de bureau Teams dont les dates de publication sont antérieures de plus de 90 jours à la [date de publication de la version actuelle](/officeupdates/teams-app-versioning) ne sont pas prises en charge. Les versions d’application de bureau Teams non prises en charge affichent une page bloquante pour les utilisateurs et demandent qu’ils mettent à jour leur application.

Pour la plupart des déploiements VDI, nous vous recommandons de déployer Teams à l’aide de l’installation par ordinateur. Pour mettre à jour vers la dernière version de Teams, commencez par la procédure de désinstallation suivie du déploiement de la dernière version de Teams.

Pour que l’optimisation de l’av Teams dans les environnements VDI fonctionne correctement, l’appareil à client léger doit avoir accès à Internet. Si l’accès à Internet n’est pas disponible sur l’appareil à client léger, le démarrage de l’optimisation ne réussira pas. Cela signifie que l’utilisateur est dans un état multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Installation persistante dédiée

Dans une configuration permanente dédiée, les modifications apportées au système d’exploitation local des utilisateurs sont conservées une fois que les utilisateurs se déconnectent. Pour une installation persistante, Teams prend en charge l’installation par utilisateur et par ordinateur.

Voici la configuration minimale de machine virtuelle recommandée.

|Paramètre  |Système d’exploitation de station de travail  |Système d’exploitation serveur  |
|---------|---------|---------|
|processeur virtuel   |    2 cœurs     |  4, 6 ou 8 cœurs<br>Il est important de comprendre la configuration de l’accès à la mémoire non uniforme (NUMA) sous-jacente et de configurer vos machines virtuelles en conséquence.     |
|Mémoire RAM     |   4 Go      | 512 Mo à 1 Go par utilisateur        |
|Stockage    | 8 Go        | 40 Go à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non persistante

Dans une configuration non persistante, les modifications apportées au système d’exploitation local des utilisateurs ne sont pas conservées une fois que les utilisateurs se déconnectent. Ces configurations sont généralement des sessions multi-utilisateurs partagées. La configuration de la machine virtuelle varie en fonction du nombre d’utilisateurs et des ressources de serveur physique disponibles.

Pour une configuration non persistante, l’application de bureau Teams doit être installée par ordinateur sur l’image d’or. Cela garantit un lancement efficace de l’application Teams pendant une session utilisateur. Pour plus d’informations, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

L’utilisation de Teams dans une configuration non persistante nécessite également un gestionnaire de mise en cache de profils pour une synchronisation efficace des données du runtime Teams. Une synchronisation efficace des données garantit que les informations spécifiques à l’utilisateur appropriées (telles que les données, le profil ou les paramètres d’un utilisateur) sont mises en cache pendant la session de l’utilisateur. Vérifiez que les données de ces deux dossiers sont synchronisées :<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Un dossier itinérant (ou, si vous utilisez la redirection de dossiers, un gestionnaire de mise en cache) est requis pour s’assurer que l’application Teams dispose des données et fichiers d’exécution requis pour exécuter l’application. Cela est nécessaire pour atténuer les problèmes de latence réseau ou les problèmes réseau, ce qui entraînerait des erreurs d’application et une expérience lente en raison de données et de fichiers indisponibles.

Diverses solutions de gestionnaire de mise en cache sont disponibles, telles que [FSLogix](/fslogix/overview). Consultez votre fournisseur de gestionnaire de mise en cache pour obtenir des instructions de configuration spécifiques.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste d’exclusions de contenu mises en cache Teams pour la configuration non persistante

Excluez les éléments suivants du dossier de mise en cache Teams. `%AppData%/Microsoft/Teams` L’exclusion de ces éléments permet de réduire la taille de mise en cache de l’utilisateur afin d’optimiser davantage votre installation non persistante.

- fichiers .txt
- Dossier De la pile multimédia
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Applications Microsoft 365 pour les grandes entreprises considérations

Tenez compte des éléments suivants lorsque vous déployez Teams avec Applications Microsoft 365 pour les grandes entreprises sur VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nouveaux déploiements de Teams via Applications Microsoft 365 pour les grandes entreprises

Avant de déployer Teams via Applications Microsoft 365 pour les grandes entreprises, vous devez d’abord désinstaller toutes les applications Teams préexistantes si elles ont été déployées à l’aide de l’installation par ordinateur.

Teams via Applications Microsoft 365 pour les grandes entreprises est installé par utilisateur. Pour plus d’informations, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Déploiements Teams via des mises à jour Applications Microsoft 365 pour les grandes entreprises

Teams est également ajouté aux installations existantes de Applications Microsoft 365 pour les grandes entreprises. Étant donné que Applications Microsoft 365 pour les grandes entreprises installe Teams uniquement par utilisateur, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Utilisation de Teams avec l’installation par machine et Applications Microsoft 365 pour les grandes entreprises

Applications Microsoft 365 pour les grandes entreprises ne prend pas en charge les installations par ordinateur de Teams. Pour utiliser l’installation par machine, vous devez exclure Teams de Applications Microsoft 365 pour les grandes entreprises. Consultez déployer [l’application de bureau Teams sur la machine virtuelle](#deploy-the-teams-desktop-app-to-the-vm) et [comment exclure le déploiement Teams via Applications Microsoft 365 pour les grandes entreprises](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) sections.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Comment exclure le déploiement teams via Applications Microsoft 365 pour les grandes entreprises

Pour en savoir plus sur Teams et Applications Microsoft 365 pour les grandes entreprises, consultez [Comment exclure Teams des nouvelles installations de Applications Microsoft 365 pour les grandes entreprises](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) et [Utiliser stratégie de groupe  pour contrôler l’installation de Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déployer l’application de bureau Teams sur la machine virtuelle

1. Téléchargez le package MSI Teams qui correspond à votre système d’exploitation de machine virtuelle VDI à l’aide de l’un des liens suivants :

    - [Version 32 bits](https://statics.teams.cdn.office.net/production-windows/1.5.00.11865/Teams_windows.msi)
    - [Version 64 bits](https://statics.teams.cdn.office.net/production-windows-x64/1.5.00.11865/Teams_windows_x64.msi)

    > [!NOTE]
    > Pour les clouds gouvernementaux, consultez [Installation en bloc de Teams à l’aide de Windows Installer (MSI)](msi-deployment.md) pour les liens de téléchargement vers les fichiers MSI.

2. Installez le MSI sur la machine virtuelle VDI en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Ce processus est l’installation par défaut, qui installe Teams dans le `%AppData%` dossier utilisateur. À ce stade, la configuration de l’image d’or est terminée.

        > [!IMPORTANT]
        > Teams ne fonctionne pas correctement avec l’installation par utilisateur sur une configuration non persistante.

    - Installation par ordinateur

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Ce processus ajoute une clé de Registre requise à l’ordinateur qui permet au programme d’installation teams de savoir qu’il s’agit d’une instance VDI.  Sans lui, le programme d’installation s’affiche en indiquant : « L’installation a échoué.  Impossible d’installer pour tous les utilisateurs lorsqu’un environnement VDI n’est pas détecté. »

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Ce processus installe Teams dans le `%ProgramFiles(x86)%` dossier d’un système d’exploitation 64 bits et dans le `%ProgramFiles%` dossier d’un système d’exploitation 32 bits. À ce stade, la configuration de l’image d’or est terminée.

        > [!IMPORTANT]
        >  L’installation de Teams par machine est requise pour les configurations non persistantes.

        Lorsque la session d’ouverture de session interactive suivante démarre, Teams démarre et demande des informations d’identification.

        > [!NOTE]
        > Ces exemples utilisent également le `ALLUSERS=1` paramètre. Lorsque vous définissez ce paramètre, **Teams Machine-Wide Installer** apparaît dans **programmes et fonctionnalités** dans **Panneau de configuration** et dans **Applications & fonctionnalités** dans **paramètres Windows** pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams s’ils ont des informations d’identification d’administrateur.
        >
        > Il est important de comprendre la différence entre `ALLUSERS=1` et `ALLUSER=1`. Le `ALLUSERS=1` paramètre peut être utilisé dans des environnements non VDI et VDI, tandis que le `ALLUSER=1` paramètre est utilisé uniquement dans les environnements VDI pour spécifier une installation par machine.

3. Désinstallez le MSI de la machine virtuelle VDI. Il existe deux façons de désinstaller Teams.

    - **Script PowerShell** : vous pouvez utiliser le script PowerShell de [nettoyage de déploiement Teams](scripts/powershell-script-deployment-cleanup.md) pour désinstaller Teams et supprimer le dossier Teams pour un utilisateur. Exécutez le script pour chaque profil utilisateur dans lequel Teams a été installé sur l’ordinateur.
    - **Ligne de commande** : exécutez la commande suivante.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Ce processus désinstalle Teams du dossier ou `%ProgramFiles%` du `%ProgramFiles(x86)%` dossier, en fonction de l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Considérations relatives aux performances de Teams sur VDI

Il existe une variété de configurations d’installation virtualisées, chacune avec un focus différent pour l’optimisation. Par exemple, une configuration peut se concentrer sur la densité d’utilisateurs. Lors de la planification, tenez compte des éléments suivants pour optimiser votre configuration en fonction des besoins de charge de travail de votre organisation.

- **Condition minimale** : certaines charges de travail peuvent nécessiter une configuration utilisant des ressources supérieures à la configuration minimale requise. Par exemple, les charges de travail pour les développeurs qui utilisent des applications qui nécessitent plus de ressources informatiques.
- **Dépendances** : celles-ci incluent les dépendances sur l’infrastructure, la charge de travail et d’autres considérations environnementales en dehors de l’application de bureau Teams.
- **Fonctionnalités désactivées sur VDI** : Teams désactive les fonctionnalités gourmandes en GPU pour VDI, ce qui peut aider à améliorer l’utilisation temporaire du processeur. Les fonctionnalités suivantes sont désactivées :
    - Animation CSS Teams
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams sur VDI avec appels et réunions

Outre la conversation et la collaboration, Teams sur VDI avec appels et réunions est disponible avec les plateformes de fournisseur de virtualisation prises en charge. Les fonctionnalités prises en charge sont basées sur la pile multimédia WebRTC et l’implémentation du fournisseur de virtualisation. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant Teams sur l’architecture VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si vous exécutez actuellement Teams sans optimisation av dans VDI et que vous utilisez des fonctionnalités qui ne sont pas encore prises en charge pour l’optimisation (par exemple, Donner et prendre le contrôle lors du partage d’applications), vous devez définir des stratégies de fournisseur de virtualisation pour désactiver la redirection Teams. Cela signifie que les sessions multimédias Teams ne seront pas optimisées. Pour savoir comment définir des stratégies pour désactiver la redirection Teams, contactez votre fournisseur de virtualisation.

### <a name="network-requirements"></a>Configuration réseau requise

Nous vous recommandons d’évaluer votre environnement pour identifier tous les risques et exigences susceptibles d’influencer votre déploiement global de voix et de vidéos dans le cloud. Utilisez [l’outil d’évaluation réseau Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885) pour tester si votre réseau est prêt pour Teams.

Pour en savoir plus sur la préparation de votre réseau pour Teams, consultez [Préparer le réseau de votre organisation pour Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrer de Skype Entreprise sur VDI vers Teams sur VDI

Si vous effectuez une migration de Skype Entreprise sur VDI vers Teams sur VDI, outre les différences entre les deux applications, il existe certaines différences lorsque VDI est également implémenté. Certaines fonctionnalités qui ne sont actuellement pas prises en charge dans Teams VDI qui se trouvent dans Skype Entreprise VDI sont les suivantes :

- Stratégie par plateforme pour désactiver certaines fonctionnalités av dans VDI
- Donner et prendre le contrôle lors du partage d’application
- Partage d’écran à partir d’une conversation sans audio
- Envoi et réception simultanés de vidéos et de partages d’écran

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Navigateur Teams sur Chrome et application de bureau Teams pour VDI

Le navigateur Teams sur Chrome ne remplace pas l’application de bureau Teams pour VDI par l’optimisation av. L’expérience de conversation et de collaboration fonctionne comme prévu. Lorsque le support est nécessaire, certaines expériences peuvent ne pas répondre aux attentes des utilisateurs sur le navigateur Chrome :

- L’expérience de streaming audio et vidéo peut ne pas être optimale. Les utilisateurs peuvent rencontrer des retards ou une qualité réduite.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des appareils est gérée via le navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Les paramètres d’appareil peuvent également être définis dans la gestion des appareils Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur VDI avec conversation et collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau de l’utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Centre d’administration Teams ou de PowerShell. Il peut s’écouler quelques heures avant que les modifications de stratégie ne se propagent. Si vous ne voyez pas de modifications pour un compte donné immédiatement, réessayez dans quelques heures.

[**Polices d’appel**](teams-calling-policy.md) : Teams inclut la stratégie d’appel **DisallowCalling** intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie **DisallowCalling** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de réunion**](meeting-policies-overview.md) : Teams inclut la stratégie de réunion **AllOff** intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez la stratégie **AllOff** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Teams

Pour affecter la stratégie **d’appel DisallowCalling** et la stratégie de réunion **AllOff** à un utilisateur :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, cliquez sur **DisallowCalling**.
    2. Sous **Stratégie de réunion**, cliquez sur **AllOff**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez la vue pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur la **&#x2713;** (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à la stratégie que vous souhaitez affecter. Par exemple :
    - Accédez aux **stratégies d’appel** **vocal** > , puis cliquez sur **DisallowCalling**.
    - Accédez aux **stratégies** **réunions** > , puis cliquez sur **AllOff**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la `DisallowCalling` stratégie d’appel à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, consultez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la `AllOff` stratégie de réunion à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrer Teams sur VDI avec conversation et collaboration pour optimiser Teams avec les appels et les réunions

Si vous disposez d’une implémentation existante de Teams sur VDI avec conversation et collaboration dans laquelle vous aviez défini des stratégies de niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion, et que vous migrez vers Teams avec l’optimisation av, vous devez définir des stratégies pour activer les fonctionnalités d’appel et de réunion pour ces utilisateurs Teams sur VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer les fonctionnalités d’appel et de réunion

Vous pouvez utiliser le Centre d’administration Teams ou PowerShell pour définir et affecter des stratégies d’appel et de réunion à vos utilisateurs. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas de modifications pour un compte donné immédiatement, réessayez après quelques heures.

[**Polices d’appel**](teams-calling-policy.md) : les stratégies d’appel dans Teams contrôlent les fonctionnalités d’appel disponibles pour les utilisateurs. Teams inclut la stratégie d’appel **AllowCalling** intégrée, dans laquelle toutes les fonctionnalités d’appel sont activées. Pour activer toutes les fonctionnalités d’appel, affectez la stratégie **AllowCalling** . Vous pouvez également créer une stratégie d’appel personnalisée pour activer les fonctionnalités d’appel souhaitées et l’affecter aux utilisateurs.

[**Stratégies de réunion**](meeting-policies-overview.md) : les stratégies de réunion dans Teams contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion **AllOn** intégrée, dans laquelle toutes les fonctionnalités de réunion sont activées. Pour activer toutes les fonctionnalités de réunion, **affectez la stratégie AllOn** . Vous pouvez également créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion souhaitées et lui affecter des utilisateurs.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Teams

Pour affecter la stratégie **d’appel AllowCalling** et la stratégie de réunion **AllOn** à un utilisateur :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, cliquez sur **AllowCalling**.
    2. Sous **Stratégie de réunion**, cliquez sur **AllOn**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez la vue pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur la **&#x2713;** (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à la stratégie que vous souhaitez affecter. Par exemple :
    - Accédez aux **stratégies d’appel** **vocal** > , puis cliquez sur **AllowCalling**.
    - Accédez aux **stratégies** **réunions** > , puis cliquez sur **AllOn**.
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer**.

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la `AllowCalling` stratégie d’appel à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, consultez [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

L’exemple suivant montre comment utiliser [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la `AllOn` stratégie de réunion à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, consultez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

## <a name="control-fallback-mode-in-teams"></a>Contrôler le mode de secours dans Teams

Lorsque les utilisateurs se connectent à partir d’un point de terminaison non pris en charge, ils sont en mode de secours, dans lequel AV n’est pas optimisé. Vous pouvez désactiver ou activer le mode de secours en définissant l’une des valeurs de Registre `DWORD` suivantes :

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Pour désactiver le mode de secours, définissez la valeur **sur 1**. Pour activer l’audio uniquement, définissez la valeur sur **2**. Si la valeur n’est pas présente ou est définie sur **0** (zéro), le mode de secours est activé.

Cette fonctionnalité est disponible dans Teams version 1.3.00.13565 et ultérieure.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Désactiver les paramètres audio et vidéo pour VDI

Les stratégies VDI Teams sont disponibles dans le module Teams. Ces stratégies sont actives et appliquées sur les environnements VDI non optimisés.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Cela concerne uniquement les environnements non optimisés.

### <a name="update-a-module-name"></a>Mettre à jour un nom de module

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

Lorsque les utilisateurs dont la stratégie VDI `DisableCallsAndMeetings` est définie pour se connecter à `$true` Teams sur VDI ne peuvent pas :

- Passer des appels.
- Participez à des réunions.
- Partage d’écran à partir d’une conversation.

Tous les types d’appels doivent être désactivés.

> [!NOTE]
> Cela concerne uniquement les environnements non optimisés.

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

Quand les utilisateurs dont la stratégie VDI `DisableAudioVideoInCallsAndMeetings` est définie pour `$true` se connecter à Teams sur VDI :

- Partage d’écran à partir d’une conversation.
- Peut participer à une réunion et partager un écran et déplacer son vers un téléphone.
- Impossible de contenir des appels audio et vidéo de personne à personne à partir de VDI.

> [!NOTE]
> Cela concerne uniquement les environnements non optimisés.

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

## <a name="known-issues-and-limitations"></a>Problèmes connus et limitations

### <a name="client-deployment-installation-and-setup"></a>Déploiement, installation et installation du client

- Avec l’installation par ordinateur, Teams sur VDI n’est pas automatiquement mis à jour de la même façon que les clients Teams non VDI. Vous devez mettre à jour l’image de machine virtuelle en installant une nouvelle identité MSI, comme décrit dans la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- Dans les environnements Citrix, si l’utilisateur se déconnecte de la machine virtuelle pendant l’exécution de Teams, les mises à jour Teams peuvent entraîner l’utilisation d’un état non optimisé pour AV lorsqu’il se reconnecte. Nous recommandons aux utilisateurs de quitter Teams avant de se déconnecter de la machine virtuelle Citrix pour éviter ce scénario.
- Teams doit être déployé par utilisateur ou par ordinateur. Le déploiement de Teams simultanément par utilisateur et par ordinateur n’est pas pris en charge. Pour migrer de l’ordinateur ou de l’utilisateur vers l’un de ces modes, suivez la procédure de désinstallation et redéployez-la vers l’un de ces modes.
- Azure Virtual Desktop ne prend pas en charge les clients macOS et Linux pour l’instant.
- Le changement de locataire rapide peut entraîner des problèmes liés à l’appel sur VDI, tels que le partage d’écran, qui n’est pas disponible. Le redémarrage du client atténuera ces problèmes.

### <a name="notifications"></a>Notifications

- La notification et la présence du nombre de messages dans la barre des tâches Windows ne sont pas prises en charge sur un hôte Windows Server 2016.

### <a name="calling-and-meetings"></a>Appels et réunions

Les fonctionnalités d’appel et de réunion suivantes ne sont pas prises en charge :

- Boutons HID et contrôles LED entre l’application Teams et les appareils pour Citrix et VMware
- Flou et effets d’arrière-plan pour Citrix et VMware
- Rôles de producteur et de présentateur d’événements diffusés et en direct
- Location-Based Routage (LBR)
- Tonalité de rappel RTC
- Son audio/ordinateur du système partagé
- Contournement de média pour le routage Direct
- Contrôle zoom

> [!NOTE]
> Nous travaillons à l’ajout de fonctionnalités d’appel et de réunion qui sont actuellement disponibles uniquement dans les environnements non-VDI. Il peut s’agir d’un contrôle plus accru de la qualité par l’administrateur, de scénarios de partage d’écran supplémentaires et de fonctionnalités avancées récemment ajoutées à Teams. Contactez votre représentant Teams pour en savoir plus sur les fonctionnalités à venir.

Voici les problèmes connus et les limitations pour les appels et les réunions :

- L’interopérabilité avec Skype Entreprise est limitée aux appels audio ; il n’existe aucune modalité vidéo.
- La résolution de flux vidéo entrant et sortant est limitée à une résolution de 720p.
- Teams ne bascule pas pour utiliser le dernier périphérique audio sélectionné par un utilisateur, si l’appareil est déconnecté, puis reconnecté.
- Les événements en direct ne sont pas optimisés.
- Partage d’écran sortant :
  - Le partage d’applications n’est pas pris en charge pour VMware et AVD/W365.
- Donnez le contrôle et prenez le contrôle :
  - Non pris en charge pendant la session de partage d’applications.

Pour les problèmes connus de Teams qui ne sont pas liés à VDI, consultez [Support Teams dans votre organisation](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes liés aux composants Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloque ou l’écran de connexion Teams est vide

Il s’agit d’un problème connu avec citrix VDA versions 1906 et 1909. Pour contourner ce problème, ajoutez la valeur de Registre `DWORD` suivante et définissez-la `204` sur (hexadécimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Ensuite, redémarrez VDA. Pour plus d’informations, consultez cet article de support Citrix sur la [résolution des problèmes d’optimisation HDX pour Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Sujets associés

- [Installer Teams en bloc à l’aide de Windows Installer (MSI)](msi-deployment.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser Microsoft Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd)
