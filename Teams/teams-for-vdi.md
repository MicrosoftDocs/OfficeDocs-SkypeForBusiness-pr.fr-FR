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
ms.openlocfilehash: 3a3193b48559fdfc941181963e493d73668bef52
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307749"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour l’Infrastructure de bureau virtualisée (VDI)

Cet article décrit les exigences et les limitations de l’utilisation de Microsoft Teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce que VDI ?

Virtual Desktop Infrastructure (VDI) est une technologie de virtualisation qui héberge un système d’exploitation de bureau et des applications sur un serveur centralisé dans un centre de données. Cela permet une expérience de bureau complète et personnalisée pour les utilisateurs disposant d’une source centralisée entièrement sécurisée et conforme.

Teams dans un environnement virtualisé prend en charge la conversation et la collaboration. Avec les plateformes Azure Virtual Desktop, Citrix et VMware, la fonctionnalité d’appel et de réunion est également prise en charge.

Teams prend également en charge plusieurs configurations dans les environnements virtuels. Il s’agit notamment des modes VDI, dédiés, partagés, persistants et non persistants. Les fonctionnalités sont en développement continu et sont régulièrement ajoutées, et les fonctionnalités s’étendront au fil du temps.

L’utilisation de Teams dans un environnement virtualisé peut être quelque peu différente de l’utilisation de Teams dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées peuvent ne pas être disponibles dans un environnement virtualisé et la résolution vidéo peut différer.

Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

> [!Note]
> Pour plus d’informations sur Teams VDI sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="teams-on-vdi-components"></a>Teams sur les composants VDI

L’utilisation de Teams dans un environnement virtualisé nécessite les composants suivants.

- **Broker de virtualisation** : gestionnaire de ressources et de connexions du fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel** : pile de machines virtuelles qui exécute Teams
- **Client léger** : appareil avec lequel l’utilisateur interagit physiquement
- **Application de bureau Teams** : l’application cliente de bureau Teams

## <a name="teams-on-vdi-requirements"></a>Conditions requises pour Teams sur VDI

### <a name="virtualization-provider-requirements"></a>Exigences du fournisseur de virtualisation

L’application de bureau Teams a été validée auprès des principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous recommandons de consulter votre fournisseur de solutions de virtualisation pour vous assurer que vous répondez aux exigences minimales.
  
Actuellement, Teams sur VDI avec optimisation audio/vidéo (AV) est certifié avec Azure Virtual Desktop, Citrix et VMware. Passez en revue les informations de cette section pour vous assurer que vous répondez à toutes les exigences en matière de fonctionnalités appropriées.

### <a name="platforms-certified-for-teams"></a>Plateformes certifiées pour Teams

Les plateformes suivantes ont des solutions d’infrastructure de bureau virtuel pour Teams.

|Plateforme|Solution|
|----|---|
|![Logo représentant Microsoft.](media/microsoft-logo.png)| <a href="/azure/virtual-desktop/teams-on-wvd" target="_blank">Azure Virtual Desktop</a>, <a href="/windows-365/enterprise/teams-on-cloud-pc" target="_blank">Windows 365</a> |
|![Logo représentant Citrix.](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Citrix Virtual Apps and Desktops</a> |
|![Logo représentant VMware.](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="azure-virtual-desktop"></a>Azure Virtual Desktop

Azure Virtual Desktop fournit une optimisation av pour Teams sur VDI. Pour en savoir plus sur la configuration requise et l’installation, consultez [Utiliser Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd).

### <a name="windows-365"></a>Windows 365

Windows 365 utilise l’optimisation AV fournie par Azure Virtual Desktop pour garantir des expériences Teams optimales à partir de PC cloud. Pour en savoir plus sur la configuration requise et l’installation, consultez [Utiliser Teams sur un PC cloud](/windows-365/enterprise/teams-on-cloud-pc).

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Configuration requise pour Citrix Virtual Apps and Desktops

Citrix Virtual Apps and Desktops (anciennement XenApp et XenDesktop) fournit une optimisation av pour Teams sur VDI. Avec Citrix Virtual Apps and Desktops, Teams sur VDI prend en charge la fonctionnalité d’appel et de réunion en plus de la conversation et de la collaboration.

Vous pouvez télécharger la dernière version de Citrix Virtual Apps and Desktops sur le [site de téléchargement citrix](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/). (Vous devez d’abord vous connecter.) Les composants nécessaires sont regroupés dans [l’application Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’agent de livraison virtuel (VDA) par défaut. Vous n’avez pas besoin d’installer de composants ou de plug-ins supplémentaires sur CWA ou le VDA.

Pour connaître les dernières exigences du serveur et du client, consultez l’article [Optimisation pour Microsoft Teams](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html) sur le site web Citrix.

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>Configuration requise pour l’espace de travail et le bureau VMware Horizon

VMware Horizon est une plateforme moderne pour la livraison sécurisée de bureaux virtuels et d’applications dans le cloud hybride. Pour offrir une expérience utilisateur optimale, VMware Horizon fournit une optimisation des médias pour Teams. Cette optimisation améliore la productivité globale des bureaux virtuels et des applications, et améliore l’expérience utilisateur lors de l’appel et de la réunion à l’aide de Teams.

Vous pouvez télécharger la dernière version de VMware Horizon à partir de la page [Téléchargements VMware](https://customerconnect.vmware.com/downloads/#all_products) . Les composants d’optimisation multimédia requis font partie de l’agent Horizon et du client Horizon par défaut, et il n’est pas nécessaire d’installer un plug-in supplémentaire pour utiliser la fonctionnalité d’optimisation pour Teams.

Pour obtenir les dernières exigences et instructions sur la configuration de l’optimisation des médias pour Teams, consultez l’article [Configuring Media Optimization for Microsoft Teams](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html) sur le site web VMware.

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installer ou mettre à jour l’application de bureau Teams sur VDI

Vous pouvez déployer l’application de bureau Teams pour VDI à l’aide d’une installation par ordinateur ou d’une installation par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser varie selon que vous utilisez une configuration persistante ou non persistante et les besoins en fonctionnalités associées de votre organisation.

Pour une configuration permanente dédiée, l’installation par ordinateur et par utilisateur fonctionne. Toutefois, pour une configuration non persistante, Teams nécessite une installation par machine pour fonctionner efficacement. Consultez la section [Configuration non persistante](#non-persistent-setup) .

Avec l’installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour l’application Teams, vous devez désinstaller la version actuelle pour effectuer la mise à jour vers une version plus récente. Avec l’installation par utilisateur, les mises à jour automatiques sont activées.

> [!IMPORTANT]
> Maintenez à jour l’application de bureau Teams dans votre environnement VDI. Les versions d’application de bureau Teams dont les dates de publication sont antérieures de plus de 90 jours à la [date de publication de la version actuelle](/officeupdates/teams-app-versioning) ne sont pas prises en charge. Les versions d’application de bureau Teams non prises en charge affichent une page bloquante aux utilisateurs et leur demandent de mettre à jour leur application.

Pour la plupart des déploiements VDI, nous vous recommandons de déployer Teams à l’aide de l’installation par machine. Pour effectuer une mise à jour vers la dernière version de Teams, commencez par la procédure de désinstallation suivie du déploiement de la dernière version de Teams.

Pour que l’optimisation de Teams AV dans les environnements VDI fonctionne correctement, l’appareil client léger doit avoir accès à Internet. Si l’accès à Internet n’est pas disponible sur l’appareil du client léger, le démarrage de l’optimisation échoue. Cela signifie que l’utilisateur est dans un état multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Configuration persistante dédiée

Dans une configuration permanente dédiée, les modifications apportées au système d’exploitation local des utilisateurs sont conservées après la déconnexion des utilisateurs. Pour une configuration permanente, Teams prend en charge l’installation par utilisateur et par ordinateur.

Voici la configuration minimale de machine virtuelle recommandée.

|Paramètre  |Système d’exploitation de station de travail  |Système d’exploitation serveur  |
|---------|---------|---------|
|processeur virtuel   |    2 cœurs     |  4, 6 ou 8 cœurs<br>Il est important de comprendre la configuration sous-jacente de l’accès à la mémoire non uniforme (NUMA) et de configurer vos machines virtuelles en conséquence.     |
|Mémoire RAM     |   4 Go      | 512 Mo à 1 Go par utilisateur        |
|Stockage    | 8 Go        | 40 Go à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non persistante

Dans une configuration non persistante, les modifications apportées au système d’exploitation local des utilisateurs ne sont pas conservées après la déconnexion des utilisateurs. Ces configurations sont généralement des sessions multi-utilisateurs partagées. La configuration de la machine virtuelle varie en fonction du nombre d’utilisateurs et des ressources de serveur physique disponibles.

Pour une configuration non persistante, l’application de bureau Teams doit être installée par machine sur l’image dorée. Cela garantit un lancement efficace de l’application Teams pendant une session utilisateur. Pour plus d’informations, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

L’utilisation de Teams dans une configuration non persistante nécessite également un gestionnaire de mise en cache de profil pour une synchronisation efficace des données du runtime Teams. Une synchronisation efficace des données garantit que les informations appropriées spécifiques à l’utilisateur (telles que les données, le profil ou les paramètres d’un utilisateur) sont mises en cache pendant la session de l’utilisateur. Vérifiez que les données de ces deux dossiers sont synchronisées :<br>

- `C:\Users\username\AppData\Local\Microsoft\IdentityCache (%LocalAppData%\Microsoft\IdentityCache)`
- `C:\Users\username\AppData\Roaming\Microsoft\Teams (%AppData%\Microsoft\Teams)`

> [!NOTE]
> Un dossier itinérant (ou, si vous utilisez la redirection de dossiers, un gestionnaire de mise en cache) est nécessaire pour garantir que l’application Teams dispose des données et fichiers d’exécution nécessaires pour exécuter l’application. Cela est nécessaire pour atténuer les problèmes de latence réseau ou les problèmes réseau, qui entraîneraient des erreurs d’application et une expérience lente en raison de données et de fichiers indisponibles.

Diverses solutions de gestionnaire de mise en cache sont disponibles, telles que [FSLogix](/fslogix/overview). Pour obtenir des instructions de configuration spécifiques, consultez votre fournisseur de gestionnaire de mise en cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste d’exclusion de contenu mis en cache Teams pour une configuration non persistante

Excluez les éléments suivants du dossier de mise en cache Teams, `%AppData%/Microsoft/Teams`. L’exclusion de ces éléments permet de réduire la taille de mise en cache des utilisateurs afin d’optimiser davantage votre configuration non persistante.

- .txt fichiers
- Dossier media-stack
- `%AppData%\Microsoft\Teams\meeting-addin\Cache`

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>considérations relatives à la Applications Microsoft 365 pour les grandes entreprises

Tenez compte des points suivants lorsque vous déployez Teams avec Applications Microsoft 365 pour les grandes entreprises sur VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nouveaux déploiements de Teams via Applications Microsoft 365 pour les grandes entreprises

Avant de déployer Teams via Applications Microsoft 365 pour les grandes entreprises, vous devez d’abord désinstaller les applications Teams préexistantes si elles ont été déployées à l’aide d’une installation par ordinateur.

Teams via Applications Microsoft 365 pour les grandes entreprises est installé par utilisateur. Pour plus d’informations, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) .

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Déploiements Teams via des mises à jour Applications Microsoft 365 pour les grandes entreprises

Teams est également ajouté aux installations existantes de Applications Microsoft 365 pour les grandes entreprises. Étant donné que Applications Microsoft 365 pour les grandes entreprises installe Teams par utilisateur uniquement, consultez la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi).

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Utilisation de Teams avec l’installation et la Applications Microsoft 365 pour les grandes entreprises par ordinateur

Applications Microsoft 365 pour les grandes entreprises ne prend pas en charge les installations par machine de Teams. Pour utiliser l’installation par ordinateur, vous devez exclure Teams de Applications Microsoft 365 pour les grandes entreprises. Consultez les sections [Déployer l’application de bureau Teams sur la machine virtuelle](#deploy-the-teams-desktop-app-to-the-vm) et [Comment exclure le déploiement teams via Applications Microsoft 365 pour les grandes entreprises](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise).

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Comment exclure le déploiement teams via Applications Microsoft 365 pour les grandes entreprises

Pour en savoir plus sur Teams et Applications Microsoft 365 pour les grandes entreprises, consultez [Comment exclure Teams des nouvelles installations de Applications Microsoft 365 pour les grandes entreprises](/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-microsoft-365-apps) et [Utiliser stratégie de groupe  pour contrôler l’installation de Teams](/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams).

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déployer l’application de bureau Teams sur la machine virtuelle

⁠1. Téléchargez le package MSI Teams qui correspond à votre système d’exploitation de machine virtuelle VDI à l’aide de l’un des liens suivants :
    - [Version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [Version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)
    > [!NOTE]
    > Pour les clouds gouvernementaux, consultez [Installation en bloc de Teams à l’aide de Windows Installer (MSI)](msi-deployment.md) pour obtenir les liens de téléchargement vers les fichiers MSI.

2. Installez le MSI sur la machine virtuelle VDI en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Ce processus est l’installation par défaut, qui installe Teams dans le `%AppData%` dossier utilisateur. À ce stade, la configuration de l’image dorée est terminée.

        > [!IMPORTANT]
        > Teams ne fonctionne pas correctement avec l’installation par utilisateur sur une installation non persistante.

    - Installation par ordinateur

        ```console
        reg add "HKLM\SOFTWARE\Microsoft\Teams" /v IsWVDEnvironment /t REG_DWORD /d 1 /f
        ```

        Ce processus ajoute une clé de Registre requise à l’ordinateur qui permet au programme d’installation de Teams de savoir qu’il s’agit d’une instance VDI.  Sans elle, le programme d’installation affiche une erreur indiquant : « L’installation a échoué.  Impossible d’installer pour tous les utilisateurs lorsqu’aucun environnement VDI n’est détecté. »

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Ce processus installe Teams dans le `%ProgramFiles(x86)%` dossier sur un système d’exploitation 64 bits et dans le `%ProgramFiles%` dossier sur un système d’exploitation 32 bits. À ce stade, la configuration de l’image dorée est terminée.

        > [!IMPORTANT]
        >  L’installation de Teams par machine est requise pour les configurations non persistantes.

        Lorsque la session d’ouverture de session interactive suivante démarre, Teams démarre et demande des informations d’identification.

        > [!NOTE]
        > Ces exemples utilisent également le `ALLUSERS=1` paramètre . Lorsque vous définissez ce paramètre, **Teams Machine-Wide Installer** s’affiche dans **Programmes et fonctionnalités** dans **Panneau de configuration** et dans **Applications & fonctionnalités** dans **paramètres Windows** pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams s’ils disposent d’informations d’identification d’administrateur.
        >
        > Il est important de comprendre la différence entre `ALLUSERS=1` et `ALLUSER=1`. Le `ALLUSERS=1` paramètre peut être utilisé dans des environnements non VDI et VDI, tandis que le `ALLUSER=1` paramètre est utilisé uniquement dans les environnements VDI pour spécifier une installation par ordinateur.

3. Désinstallez le MSI de la machine virtuelle VDI. Il existe deux façons de désinstaller Teams.

    - **Script PowerShell** : vous pouvez utiliser le script PowerShell de [nettoyage de déploiement Teams](scripts/powershell-script-deployment-cleanup.md) pour désinstaller Teams et supprimer le dossier Teams pour un utilisateur. Exécutez le script pour chaque profil utilisateur dans lequel Teams a été installé sur l’ordinateur.
    - **Ligne de commande** : exécutez la commande suivante.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Ce processus désinstalle Teams du `%ProgramFiles(x86)%` dossier ou `%ProgramFiles%` du dossier, en fonction de l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Considérations relatives aux performances de Teams sur VDI

Il existe une variété de configurations d’installation virtualisées, chacune avec un objectif différent pour l’optimisation. Par exemple, une configuration peut se concentrer sur la densité des utilisateurs. Lors de la planification, tenez compte des éléments suivants pour vous aider à optimiser votre configuration en fonction des besoins de charge de travail de votre organisation.

- **Configuration minimale requise** : certaines charges de travail peuvent nécessiter une configuration à l’aide de ressources supérieures à la configuration minimale requise. Par exemple, les charges de travail pour les développeurs qui utilisent des applications qui nécessitent davantage de ressources informatiques.
- **Dépendances** : celles-ci incluent les dépendances vis-à-vis de l’infrastructure, de la charge de travail et d’autres considérations environnementales en dehors de l’application de bureau Teams.
- **Fonctionnalités désactivées sur VDI** : Teams désactive les fonctionnalités gourmandes en GPU pour VDI, ce qui peut aider à améliorer l’utilisation temporaire du processeur. Les fonctionnalités suivantes sont désactivées :
    - Animation CSS Teams
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams sur VDI avec appels et réunions

En plus de la conversation et de la collaboration, Teams sur VDI avec appels et réunions est disponible avec les plateformes de fournisseur de virtualisation prises en charge. Les fonctionnalités prises en charge sont basées sur la pile multimédia WebRTC et l’implémentation du fournisseur de virtualisation. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant Teams sur l’architecture VDI.](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si vous exécutez actuellement Teams sans optimisation av dans VDI et que vous utilisez des fonctionnalités qui ne sont pas encore prises en charge pour l’optimisation (telles que Donner et prendre le contrôle lors du partage d’application), vous devez définir des stratégies de fournisseur de virtualisation pour désactiver la redirection Teams. Cela signifie que les sessions multimédias Teams ne seront pas optimisées. Pour savoir comment définir des stratégies pour désactiver la redirection Teams, contactez votre fournisseur de virtualisation.

### <a name="network-requirements"></a>Configuration réseau requise

Nous vous recommandons d’évaluer votre environnement pour identifier les risques et les exigences susceptibles d’influencer votre déploiement global de voix et de vidéo dans le cloud. Utilisez [l’outil d’évaluation réseau Skype Entreprise](https://www.microsoft.com/download/details.aspx?id=53885) pour tester si votre réseau est prêt pour Teams.

Pour en savoir plus sur la préparation de votre réseau pour Teams, consultez [Préparer le réseau de votre organisation pour Teams](prepare-network.md).

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrer de Skype Entreprise sur VDI vers Teams sur VDI

Si vous effectuez une migration de Skype Entreprise sur VDI vers Teams sur VDI, outre les différences entre les deux applications, il existe certaines différences lorsque VDI est également implémenté. Voici quelques fonctionnalités qui ne sont actuellement pas prises en charge dans teams VDI qui se trouvent dans Skype Entreprise VDI :

- Stratégie par plateforme pour désactiver certaines fonctionnalités AV dans VDI
- Donner et prendre le contrôle lors du partage d’application
- Partage d’écran à partir d’une conversation sans audio
- Envoi et réception simultanés d’une vidéo et d’un partage d’écran

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams sur le navigateur Chrome et l’application de bureau Teams pour VDI

Le navigateur Teams sur Chrome ne remplace pas l’application de bureau Teams pour VDI avec optimisation av. L’expérience de conversation et de collaboration fonctionne comme prévu. Lorsque du contenu multimédia est nécessaire, certaines expériences peuvent ne pas répondre aux attentes des utilisateurs sur le navigateur Chrome :

- L’expérience de streaming audio et vidéo peut ne pas être optimale. Les utilisateurs peuvent rencontrer des retards ou une qualité réduite.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des appareils est gérée via le navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Les paramètres de l’appareil doivent également être définis dans la gestion des appareils Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur VDI avec conversation et collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau de l’utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver la fonctionnalité d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Centre d’administration Teams ou de PowerShell. Jusqu’à quelques heures pour que les modifications de stratégie se propagent. Si vous ne voyez pas de modifications pour un compte donné immédiatement, réessayez dans quelques heures.

[**Stratégies d’appel**](teams-calling-policy.md) : Teams inclut la stratégie d’appel **Intégrée DisallowCalling** , dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie **DisallowCalling** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de réunion**](meeting-policies-overview.md) : Teams inclut la stratégie de réunion **AllOff** intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez la stratégie **AllOff** à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Teams

Pour affecter la stratégie **d’appel DisallowCalling** et la stratégie de réunion **AllOff** à un utilisateur :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, cliquez sur **InterdireCalling**.
    2. Sous **Stratégie de réunion**, cliquez sur **ToutOff**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur le **&#x2713;** (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à la stratégie que vous souhaitez attribuer. Par exemple :
    - Accédez à **Stratégies d’appel vocal** > , puis cliquez sur **InterdireCalling**.
    - Accédez à **Réunions Stratégies** > **de réunion**, puis cliquez sur **ToutOff**.
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

Si vous disposez d’une implémentation existante de Teams sur VDI avec conversation et collaboration dans laquelle vous avez défini des stratégies au niveau de l’utilisateur pour désactiver les fonctionnalités d’appel et de réunion, et que vous migrez vers Teams avec optimisation av, vous devez définir des stratégies pour activer les fonctionnalités d’appel et de réunion pour ces utilisateurs Teams sur VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer la fonctionnalité d’appel et de réunion

Vous pouvez utiliser le Centre d’administration Teams ou PowerShell pour définir et affecter des stratégies d’appel et de réunion à vos utilisateurs. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas de modifications pour un compte donné immédiatement, réessayez après quelques heures.

[**Stratégies d’appel : les**](teams-calling-policy.md) stratégies d’appel dans Teams contrôlent les fonctionnalités d’appel disponibles pour les utilisateurs. Teams inclut la stratégie d’appel **AllowCalling** intégrée, dans laquelle toutes les fonctionnalités d’appel sont activées. Pour activer toutes les fonctionnalités d’appel, affectez la stratégie **AllowCalling** . Vous pouvez également créer une stratégie d’appel personnalisée pour activer les fonctionnalités d’appel souhaitées et l’affecter aux utilisateurs.

[**Stratégies de réunion**](meeting-policies-overview.md) : les stratégies de réunion dans Teams contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles pour les participants aux réunions planifiées par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion **AllOn** intégrée, dans laquelle toutes les fonctionnalités de réunion sont activées. Pour activer toutes les fonctionnalités de réunion, affectez la stratégie **AllOn** . Vous pouvez également créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion souhaitées et lui affecter des utilisateurs.

#### <a name="assign-policies-using-the-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Teams

Pour affecter la stratégie **d’appel AllowCalling** et la stratégie de réunion **AllOn** à un utilisateur :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**.
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1. Sous **Stratégie d’appel**, cliquez sur **AutoriserCalling**.
    2. Sous **Stratégie de réunion**, cliquez sur **AllOn**.
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur le **&#x2713;** (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également effectuer les opérations suivantes :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à la stratégie que vous souhaitez attribuer. Par exemple :
    - Accédez à **Stratégies d’appel vocal** > , puis cliquez sur **AutoriserCalling**.
    - Accédez à **Stratégies de** > **réunion**, puis cliquez sur **AllOn**.
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

Lorsque les utilisateurs se connectent à partir d’un point de terminaison non pris en charge, les utilisateurs sont en mode de secours, dans lequel av n’est pas optimisé. Vous pouvez désactiver ou activer le mode de secours en définissant l’une des valeurs de Registre `DWORD` suivantes :

- `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback`
- `HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback`

Pour désactiver le mode de secours, définissez la valeur sur **1**. Pour activer l’audio uniquement, définissez la valeur sur **2**. Si la valeur n’est pas présente ou est définie sur **0** (zéro), le mode de secours est activé.

Cette fonctionnalité est disponible dans Teams version 1.3.00.13565 et ultérieure.

## <a name="disable-audio-and-video-settings-for-vdi"></a>Désactiver les paramètres audio et vidéo pour VDI

Les stratégies VDI Teams sont disponibles dans le module Teams. Ces stratégies sont actives et appliquées sur les environnements VDI non optimisés.

- `New-CsTeamsVdiPolicy`
- `Grant-CsTeamsVdiPolicy`
- `Remove-CsTeamsVdiPolicy`
- `Set-CsTeamsVdiPolicy`

> [!NOTE]
> Cela concerne uniquement les environnements non optimisés.

### <a name="connect-to-microsoft-teams-powershell"></a>Se connecter à Microsoft Teams PowerShell

Suivez les instructions fournies dans [Installer Microsoft module PowerShell Teams](/Teams/teams-powershell-install.md) pour vous connecter au module PowerShell Microsoft Teams. Exécutez ensuite la commande suivante pour vérifier que toutes les applets de commande VDI sont disponibles :

```PowerShell
Get-Command -Noun *VDI*
```

### <a name="set-policies-to-limit-calling-features"></a>Définir des stratégies pour limiter les fonctionnalités d’appel

Lorsque les utilisateurs dont la stratégie VDI `DisableCallsAndMeetings` est définie pour se connecter à `$true` Teams sur VDI, ils ne peuvent pas :

- Passer des appels.
- Participer à des réunions.
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

Lorsque les utilisateurs dont la stratégie VDI `DisableAudioVideoInCallsAndMeetings` est définie pour se connecter à `$true` Teams sur VDI, ils :

- Partage d’écran à partir d’une conversation.
- Peuvent participer à une réunion et partager un écran et déplacer leur audio sur un téléphone.
- Impossible de tenir des appels audio et vidéo de personne à personne à partir de VDI.

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

- Avec l’installation par machine, Teams sur VDI n’est pas automatiquement mis à jour de la même façon que les clients Teams non VDI. Vous devez mettre à jour l’image de machine virtuelle en installant un nouveau MSI, comme décrit dans la section [Installer ou mettre à jour l’application de bureau Teams sur VDI](#install-or-update-the-teams-desktop-app-on-vdi) . Vous devez désinstaller la version actuelle pour effectuer une mise à jour vers une version plus récente.
- Dans les environnements Citrix, si l’utilisateur se déconnecte de la machine virtuelle pendant que Teams est en cours d’exécution, les mises à jour de Teams peuvent faire en sorte que l’utilisateur soit dans un état non optimisé pour av lorsqu’il se reconnecte. Nous recommandons aux utilisateurs de quitter Teams avant de se déconnecter de Citrix Virtual Machine pour éviter ce scénario.
- Teams doit être déployé par utilisateur ou par machine. Le déploiement de Teams simultané par utilisateur et par machine n’est pas pris en charge. Pour effectuer une migration de par ordinateur ou par utilisateur vers l’un de ces modes, suivez la procédure de désinstallation et redéployez-la dans l’un ou l’autre des modes.
- Azure Virtual Desktop ne prend pas en charge les clients Linux pour l’instant.
- Le changement de locataire rapide peut entraîner des problèmes liés à l’appel sur VDI, comme le partage d’écran non disponible. Le redémarrage du client permet d’atténuer ces problèmes.

### <a name="notifications"></a>Notifications

- La notification et la présence du nombre de messages dans la barre des tâches Windows ne sont pas prises en charge sur un hôte Windows Server 2016.

### <a name="calling-and-meetings"></a>Appels et réunions

Les fonctionnalités d’appel et de réunion suivantes ne sont pas prises en charge :

- Boutons HID et contrôles LED entre l’application Teams et les appareils pour Citrix et VMware
- Flou d’arrière-plan et effets pour Citrix et VMware
- Rôles de producteur et de présentateur d’événements de diffusion et de diffusion en direct
- routage Location-Based (LBR)
- Tonalité de sonnerie d’appel PSTN
- Audio système/son d’ordinateur partagé
- Contournement de média pour le routage Direct
- Contrôle de zoom

> [!NOTE]
> Nous travaillons à l’ajout de fonctionnalités d’appel et de réunion qui ne sont actuellement disponibles que dans les environnements non VDI. Il peut s’agir d’un contrôle administrateur accru sur la qualité, de scénarios de partage d’écran supplémentaires et de fonctionnalités avancées récemment ajoutées à Teams. Contactez votre représentant Teams pour en savoir plus sur les fonctionnalités à venir.

Voici les problèmes connus et les limitations liés aux appels et aux réunions :

- L’interopérabilité avec Skype Entreprise est limitée aux appels audio ; il n’existe aucune modalité vidéo.
- La résolution des flux vidéo entrants et sortants est limitée à la résolution 720p.
- Teams ne bascule pas pour utiliser le dernier périphérique audio qu’un utilisateur a sélectionné, si l’appareil est déconnecté, puis reconnecté.
- Les événements en direct ne sont pas optimisés.
- Partage d’écran sortant :
  - Le partage d’applications n’est pas pris en charge pour VMware et AVD/W365.
- Donnez le contrôle et prenez le contrôle :
  - Non pris en charge pendant la session de partage d’application.

Pour les problèmes connus de Teams qui ne sont pas liés à VDI, consultez [Support Teams dans votre organisation](/MicrosoftTeams/troubleshoot/teams-welcome).

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes liés aux composants Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se bloque ou l’écran de connexion Teams est vide

Il s’agit d’un problème connu avec les versions 1906 et 1909 de Citrix VDA. Pour contourner ce problème, ajoutez la valeur de Registre `DWORD` suivante et définissez-la sur `204` (hexadécimal).

```console

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

```

Ensuite, redémarrez VDA. Pour plus d’informations, consultez cet article de support Citrix, [Résolution des problèmes d’optimisation HDX pour Microsoft Teams](https://support.citrix.com/article/CTX253754).

## <a name="related-topics"></a>Rubriques connexes

- [Installer Teams en bloc à l’aide de Windows Installer (MSI)](msi-deployment.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser Microsoft Teams sur Azure Virtual Desktop](/azure/virtual-desktop/teams-on-wvd)
