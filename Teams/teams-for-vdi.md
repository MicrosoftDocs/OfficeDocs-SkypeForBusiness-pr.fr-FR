---
title: Teams pour l’Infrastructure de bureau virtualisée (VDI)
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Découvrez comment exécuter Microsoft Teams dans un environnement VDI (Virtualized Desktop Infrastructure).
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 687726febc81a727c4f6da4824487672c602809e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820984"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Teams pour l’Infrastructure de bureau virtualisée (VDI)

Cet article décrit les exigences et les limitations relatives à l’utilisation de Microsoft Teams dans un environnement virtualisé.

## <a name="what-is-vdi"></a>Qu’est-ce que VDI ?

L’infrastructure VDI (Virtual Desktop Infrastructure) est une technologie de virtualisation qui héberge un système d’exploitation de bureau et des applications sur un serveur centralisé dans un centre de données. Cela permet aux utilisateurs d’une source centralisée pleinement sécurisée et conforme d’obtenir une expérience de bureau entièrement personnalisée.

Microsoft Teams dans un environnement virtualisé prend en charge la conversation et la collaboration. Par ailleurs, grâce aux plateformes Windows Virtual Desktop, Citrix et VMware, les fonctionnalités d’appel et de réunion sont également pris en charge.

Teams dans un environnement virtualisé prend en charge plusieurs configurations. Il s’agit notamment des modes VDI, dédiés, partagés, persistants et non persistants. Les fonctionnalités sont en développement continu et sont régulièrement ajoutées, et elles seront étendues dans les mois et les années à venir.

L’utilisation de Teams dans un environnement virtualisé peut être quelque peu différente de l’utilisation de Teams dans un environnement non virtualisé. Par exemple, certaines fonctionnalités avancées peuvent ne pas être disponibles dans un environnement virtualisé, et la résolution vidéo peut différer.

Pour garantir une expérience utilisateur optimale, suivez les instructions de cet article.

> [!Note]
> Pour plus d’informations sur les VDI Teams sur différentes plateformes, consultez [les fonctionnalités de Teams par plateforme.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams sur les composants VDI

L’utilisation de Teams dans un environnement virtualisé nécessite les composants suivants.

- **Courtier en virtualisation**: gestionnaire de ressources et de connexions du fournisseur de virtualisation, tel qu’Azure
- **Bureau virtuel**: pile de machines virtuelles qui exécute Microsoft Teams
- **Client fin**: point de terminaison que l’utilisateur interface physiquement avec
- **Application de bureau Teams**: Application de bureau Teams

## <a name="teams-on-vdi-requirements"></a>Teams sur la requise VDI

### <a name="virtualization-provider-requirements"></a>Exigences du fournisseur de virtualisation

L’application de bureau Teams a été validée avec les principaux fournisseurs de solutions de virtualisation. Avec plusieurs fournisseurs de marché, nous vous recommandons de consulter votre fournisseur de solutions de virtualisation pour vous assurer que vous répondez aux conditions minimales requises.
  
Actuellement, Teams sur VDI avec l’optimisation audio/vidéo (AV) est certifié avec Windows Virtual Desktop, Citrix et VMware. Examinez les informations de cette section pour vous assurer que vous respectez toutes les conditions requises pour utiliser les fonctionnalités adéquates.

### <a name="platforms-certified-for-teams"></a>Plateformes certifiées pour Teams

Les plateformes suivantes ont des solutions d’infrastructure de bureau virtuel pour Teams.

|Plateforme|Solution|
|----|---|
|![Logo représentant Microsoft](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Bureau virtuel Windows</a> |
|![Logo représentant Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Applications et bureaux virtuels Citrix</a> |
|![Logo représentant VMware](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Bureau virtuel Windows

Windows Virtual Desktop fournit l’optimisation AV pour Teams sur VDI. Pour en savoir plus sur la exigences et l’installation, [voir Utiliser Teams sur Windows Virtual Desktop.](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Citrix Virtual Apps and Desktops requirements

Citrix Virtual Apps and Desktops (anciennement XenApp et XenDesktop) fournit l’optimisation AV pour Teams sur VDI. Avec Citrix Virtual Apps et Desktops, Teams sur VDI prend en charge les fonctionnalités d’appel et de réunion en plus de la conversation et de la collaboration.

Vous pouvez télécharger la dernière version des applications et bureaux virtuels Citrix sur le site de [téléchargements de Citrix.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Vous devez tout d’abord vous connectez.) Les composants nécessaires sont regroupés dans l’application [Citrix Workspace (CWA)](https://www.citrix.com/downloads/workspace-app/) et l’agent de remise virtuelle (VDA) par défaut. Vous n’avez pas besoin d’installer d’autres composants ou plug-ins sur CWA ou VDA.

Pour obtenir les dernières exigences en matière de serveur et de client, [consultez ce site web Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace and Desktop requirements

VMware Horizon est une plateforme moderne qui permet d’assurer la livraison sécurisée des bureaux et applications virtuels dans le cloud hybride. Pour offrir une expérience excellente aux utilisateurs finaux, VMware Horizon offre l’optimisation des médias pour Teams. Cette optimisation améliore la productivité globale sur les bureaux virtuels et les applications, et améliore l’expérience utilisateur lors des appels et des réunions à l’aide de Teams.

Vous pouvez télécharger la dernière version de VMware Horizon à partir de la page [Téléchargements de VMware.](https://my.vmware.com/web/vmware/downloads/#all_products) Les composants d’optimisation multimédia requis font partie de l’agent Horizon et du client Horizon par défaut et il n’est pas nécessaire d’installer de plug-in supplémentaire pour utiliser la fonctionnalité d’optimisation de Teams.

Pour obtenir les dernières exigences et instructions sur la configuration de l’optimisation des médias pour Teams, consultez ce [site web VMware.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installer ou mettre à jour l’application de bureau Teams sur VDI

Vous pouvez déployer l’application de bureau Teams pour VDI à l’aide d’une installation par ordinateur ou par utilisateur à l’aide du package MSI. Le choix de l’approche à utiliser dépend de l’utilisation d’une configuration permanente ou non permanente et des besoins en fonctionnalités associées de votre organisation.

Pour une configuration permanente dédiée, l’une ou l’autre approche fonctionnerait. Toutefois, pour une configuration non permanente, Teams nécessite une installation par ordinateur afin d’être efficace. Consultez la section [configuration non](#non-persistent-setup) permanente.

Avec l’installation par ordinateur, les mises à jour automatiques sont désactivées. Cela signifie que pour mettre à jour l’application Teams, vous devez désinstaller la version actuelle pour la mettre à jour vers une version plus récente. Avec l’installation par utilisateur, les mises à jour automatiques sont activées. Pour la plupart des déploiements VDI, nous vous recommandons de déployer Teams via une installation par ordinateur.

Pour mettre à jour vers la dernière version de Teams, commencez par la procédure de désinstallation suivie du déploiement de la dernière version de Teams.

Pour que l’optimisation Teams AV dans les environnements VDI fonctionne correctement, le point de terminaison fin du client doit avoir accès à Internet. Si l’accès Internet n’est pas disponible au point de terminaison fin du client, l’optimisation du démarrage ne réussira pas. Cela signifie que l’utilisateur se trouve dans un état multimédia non optimisé.

#### <a name="dedicated-persistent-setup"></a>Configuration permanente dédiée

Dans une installation permanente dédiée, les modifications apportées au système d’exploitation local des utilisateurs sont conservées une fois que les utilisateurs se déconnectent. Pour la configuration permanente, Teams prend en charge l’installation par utilisateur et par ordinateur.

Voici la configuration VM minimale recommandée.

|Paramètre  |Système d’exploitation de station de travail  |Système d’exploitation serveur  |
|---------|---------|---------|
|vCPU   |    2 cœurs     |  4,6 ou 8<br>Il est important de comprendre la configuration sous-jacente de l’accès mémoire non uniforme (NUMA) et de configurer vos VM en conséquence.     |
|Mémoire RAM     |   4 Go      | 512 à 1 024 Mo par utilisateur        |
|Stockage    | 8 Go        | 40 à 60 Go        |

#### <a name="non-persistent-setup"></a>Configuration non permanente

Dans une configuration non permanente, les modifications apportées au système d’exploitation local des utilisateurs ne sont pas conservées une fois que les utilisateurs se déconnectent. De telles configurations sont généralement partagées entre utilisateurs. La configuration de la VM varie en fonction du nombre d’utilisateurs et des ressources physiques disponibles.

Dans le cas d’une configuration non permanente, l’application de bureau Teams doit être installée par ordinateur pour obtenir l’image d’or. (Pour en savoir plus, consultez la section Installer ou mettre à jour [l’application de bureau Teams sur VDI.)](#install-or-update-the-teams-desktop-app-on-vdi) Cela garantit un lancement efficace de l’application Teams pendant une session utilisateur.

L’utilisation de Teams avec une configuration non permanente nécessite également un gestionnaire de mise en cache de profils pour une synchronisation efficace des données pendant l’runtime de Teams. Cela garantit que les informations spécifiques à l’utilisateur appropriées (par exemple, les données de l’utilisateur, le profil et les paramètres) sont mises en cache pendant la session de l’utilisateur. Assurez-vous que les données de ces deux dossiers sont synchronisées.  

- C:\Utilisateurs\nom d’utilisateur\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Utilisateurs\nom d’utilisateur\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

Différentes solutions de gestionnaire de mise en cache sont disponibles. Par exemple, [FSLogix.](https://docs.microsoft.com/fslogix/overview) Pour obtenir des instructions de configuration spécifiques, consultez le fournisseur du Gestionnaire de mise en cache.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste d’exclusion de contenu mis en cache dans Teams pour la configuration non permanente

Excluez ce qui suit du dossier de mise en cache Teams, %appdata%/Microsoft/Teams. En excluant ces éléments, vous réduisez la taille de la mise en cache des utilisateurs pour optimiser votre configuration non permanente.

- Fichiers .txt
- Dossier de pile de médias
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Applications Microsoft 365 pour considérations pour les entreprises

Prenons l’exemple suivant lorsque vous déployez Teams avec les applications Microsoft 365 Entreprise sur VDI.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Nouveaux déploiements de Teams via les applications Microsoft 365 pour les entreprises

Avant de déployer Teams via les applications Microsoft 365 pour les entreprises, vous devez d’abord désinstaller les applications Teams existantes si elles ont été déployées via une installation par ordinateur.

Teams via les applications Microsoft 365 Pour les entreprises est installé par utilisateur. Pour en savoir plus, consultez la section Installer ou [mettre à jour l’application de bureau Teams sur VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Déploiements teams via les applications Microsoft 365 pour les mises à jour pour les entreprises

Teams est également ajouté aux installations existantes des applications Microsoft 365 pour les entreprises. Étant donné que Microsoft 365 Applications pour les entreprises installe Teams par utilisateur uniquement, consultez la section Installer ou mettre à jour l’application de bureau Teams sur [VDI.](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Utilisation de Teams avec l’installation par ordinateur et les applications Microsoft 365 pour les entreprises

Microsoft 365 Apps pour les entreprises ne prend pas en charge les installations par ordinateur de Teams. Pour utiliser l’installation par ordinateur, vous devez exclure Teams des applications Microsoft 365 pour les entreprises. Consultez [l’application de bureau Déployer l’application](#deploy-the-teams-desktop-app-to-the-vm) de bureau Teams sur la messagerie automatique et comment exclure le déploiement de Teams via les sections Applications Microsoft [365](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise) pour les entreprises.

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Comment exclure le déploiement de Teams via les applications Microsoft 365 pour les entreprises

Pour en savoir plus sur Teams et les applications Microsoft 365 pour les entreprises, voir Comment exclure Teams des nouvelles installations des applications [Microsoft 365](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) Pour les entreprises et Utiliser une stratégie de groupe pour contrôler l’installation de [Teams.](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Déployer l’application de bureau Teams sur la VM

1. Téléchargez le package MSI Teams qui correspond à votre système d’exploitation VDI VDI en utilisant l’un des liens suivants :

    - [Version 32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [version 64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Pour les cloud du gouvernement, [consultez Installer Microsoft Teams à l’aide](msi-deployment.md) de Microsoft Endpoint Configuration Manager pour obtenir les liens de téléchargement vers les fichiers MSI.

    La version minimale de l’application de bureau Teams requise est la version 1.3.00.4461. (La prise en charge PSTN n’est pas prise en charge dans les versions antérieures.)

2. Installez le MSI sur la VDI VM en exécutant l’une des commandes suivantes :

    - Installation par utilisateur (par défaut)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Ce processus est l’installation par défaut, qui installe Teams dans le dossier utilisateur %AppData%. À ce stade, la configuration de l’image dorée est terminée. Teams ne fonctionne pas correctement avec l’installation par utilisateur sur une configuration non permanente.

    - Installation par ordinateur

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Ce processus installe Teams dans le dossier Fichiers programmes (x86) sur un système d’exploitation 64 bits et dans le dossier Fichiers programmes sur un système d’exploitation 32 bits. À ce stade, la configuration de l’image dorée est terminée. L’installation de Teams par ordinateur est requise pour les configurations sans permanente.

        La prochaine session d’ouverture de session interactive démarre Teams et vous demande des informations d’identification.

        > [!NOTE]
        > Ces exemples utilisent également **le paramètre ALLUSERS=1.** Lorsque vous définissez ce paramètre, Teams Machine-Wide Installer apparaît dans Programmes et fonctionnalités dans le Panneau de configuration et dans Applications et fonctionnalités dans les paramètres Windows pour tous les utilisateurs de l’ordinateur. Tous les utilisateurs peuvent ensuite désinstaller Teams s’ils ont des informations d’identification d’administrateur.
        Il est important de comprendre la différence entre **ALLUSERS=1** et **ALLUSER=1.** Le paramètre **ALLUSERS=1** peut être utilisé dans des environnements non VDI et VDI, tandis que le paramètre **ALLUSER=1** est utilisé uniquement dans les environnements VDI pour spécifier une installation par ordinateur.

3. Désinstallez le MSI de la VDI VDI VM. Il existe deux façons de désinstaller Teams.

    - Script PowerShell : vous pouvez utiliser [ce script PowerShell pour](scripts/powershell-script-deployment-cleanup.md) désinstaller Teams et supprimer le dossier Teams d’un utilisateur. Exécutez le script pour chaque profil utilisateur dans lequel Teams a été installé sur l’ordinateur.
    - Ligne de commande : exécutez la commande suivante.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Ce processus désinstalle Teams du dossier Fichiers programmes (x86) ou Fichiers programmes, selon l’environnement du système d’exploitation.

## <a name="teams-on-vdi-performance-considerations"></a>Teams sur les considérations en cas de performances VDI

Il existe plusieurs configurations de configuration virtualisées, avec une attention différente pour l’optimisation. Par exemple, une configuration peut se concentrer sur la densité d’utilisateurs. Lors de la planification, envisagez les opérations suivantes pour optimiser votre configuration en fonction des besoins de charge de travail de votre organisation.

- Configuration minimale requise : certaines charges de travail peuvent nécessiter une configuration à l’aide de ressources qui dépassent la configuration minimale requise. Par exemple, les charges de travail des développeurs qui utilisent des applications qui demandent plus de ressources informatiques.
- Dépendances : il peut s’agir de dépendances en relation avec l’infrastructure, la charge de travail et d’autres considérations environnementales en dehors de l’application de bureau Teams.
- Fonctionnalités désactivées sur VDI : Teams désactive les fonctionnalités intensives de l’UC pour une utilisation VDI, ce qui peut contribuer à l’utilisation optimale de l’UC. Les fonctionnalités suivantes sont désactivées :
    - Animation CSS Teams
    - Démarrage automatique de Giphy

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams sur VDI avec appels et réunions

Outre la conversation et la collaboration, Teams sur VDI avec appels et réunions est disponible avec les plateformes de fournisseurs de virtualisation pris en charge. Les fonctionnalités prise en charge sont basées sur la pile de médias WebRTC et l’implémentation du fournisseur de virtualisation. Le diagramme suivant fournit une vue d’ensemble de l’architecture.

![Diagramme montrant Teams sur une architecture VDI](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Si vous exécutez actuellement Teams sans optimisation AV dans VDI et que vous utilisez des fonctionnalités qui ne sont pas encore pris en charge pour l’optimisation (telles que Donner et prendre le contrôle du partage d’application), vous devez définir des stratégies de fournisseur de virtualisation pour désactiver la redirection dans Teams. Cela signifie que les sessions multimédias teams ne seront pas optimisées. Pour savoir comment définir des stratégies pour désactiver la redirection de Teams, contactez votre fournisseur de virtualisation.

### <a name="network-requirements"></a>Conditions de réseau requises

Nous vous recommandons d’évaluer votre environnement afin d’identifier les risques et les exigences qui peuvent influencer votre déploiement voix et vidéo dans le cloud dans son ensemble. Utilisez [l’outil d’évaluation du réseau Skype](https://www.microsoft.com/download/details.aspx?id=53885) Entreprise pour tester si votre réseau est prêt pour Teams.

Pour en savoir plus sur la préparation de votre réseau pour Teams, voir Préparer le réseau [de votre organisation pour Teams.](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrer de Skype Entreprise sur un plan VDI vers Teams sur VDI

Si vous migrez de Skype Entreprise sur VDI vers Teams sur VDI, outre les différences entre les deux applications, il existe quelques différences lorsque VDI est également implémenté. Certaines fonctionnalités actuellement non prise en charge dans les VDI Teams disponibles dans Skype Entreprise VDI sont les suivantes :

- Stratégie par plate-forme pour la désactivation de certaines fonctionnalités AV dans VDI
- Donner et prendre le contrôle lors du partage d’application
- Partage d’écran à partir d’une conversation sans son
- Envoi et réception simultanés de vidéos et de partages d’écran

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams dans le navigateur Chrome et l’application de bureau Teams pour VDI

Teams sur le navigateur Chrome ne remplace pas l’application de bureau Teams pour VDI avec l’optimisation AV. L’expérience de conversation et de collaboration fonctionne comme prévu. Lorsque des médias sont nécessaires, certaines expériences peuvent ne pas répondre aux attentes des utilisateurs sur le navigateur Chrome :

- L’expérience de diffusion en continu audio et vidéo n’est peut-être pas optimale. Les utilisateurs peuvent avoir des retards ou une qualité réduite.
- Les paramètres de l’appareil ne sont pas disponibles dans les paramètres du navigateur.
- La gestion des périphériques est gérée via le navigateur et nécessite plusieurs paramètres dans les paramètres du site du navigateur.
- Il est possible que les paramètres des appareils doivent également être réglés dans la gestion des appareils Windows.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams sur VDI avec la conversation et la collaboration

Si votre organisation souhaite utiliser uniquement les fonctionnalités de conversation et de collaboration dans Teams, vous pouvez définir des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion dans Teams. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Définir des stratégies pour désactiver les fonctionnalités d’appel et de réunion

Vous pouvez définir des stratégies à l’aide du Centre d’administration Microsoft Teams ou de PowerShell. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau dans quelques heures.

[**Polices d’appel**](teams-calling-policy.md): Teams inclut la stratégie d’appel DisallowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Affectez la stratégie DisallowCalling à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

[**Stratégies de**](meeting-policies-in-teams.md)réunion : Teams inclut la stratégie de réunion AllOff intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Affectez la stratégie AllOff à tous les utilisateurs de votre organisation qui utilisent Teams dans un environnement virtualisé.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Microsoft Teams

Pour affecter la stratégie d’appel DisallowCalling et la stratégie de réunion AllOff à un utilisateur :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **Utilisateurs.**
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **Stratégie d’appel,** cliquez **sur DisallowCalling.**
    2.  Sous **Stratégie de réunion,** cliquez **sur AllOff.**
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur &#x2713; (coche) en haut du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à la stratégie que vous voulez attribuer. Par exemple :
    - Consultez **les**  >  **stratégies d’appel** vocal, puis cliquez sur **DisallowCalling.**
    - Consultez **les stratégies de**  >  **réunion,** puis cliquez sur **AllOff.**
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer.**

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel DisallowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

L’exemple suivant montre comment utiliser la stratégie de réunion [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOff à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrer Teams sur un VDI avec la conversation et la collaboration pour optimiser Teams avec les appels et les réunions

Si vous avez déjà mis en œuvre Teams sur VDI avec la conversation et la collaboration dans le but de définir des stratégies au niveau utilisateur pour désactiver les fonctionnalités d’appel et de réunion, et que vous migrez vers Teams avec l’optimisation AV, vous devez définir des stratégies pour activer les fonctionnalités d’appel et de réunion pour ces équipes sur les utilisateurs VDI.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Définir des stratégies pour activer les fonctionnalités d’appel et de réunion

Vous pouvez utiliser le Centre d’administration Microsoft Teams ou PowerShell pour définir et attribuer des stratégies d’appel et de réunion à vos utilisateurs. La propagation des modifications de stratégie peut prendre un certain temps (quelques heures). Si vous ne voyez pas immédiatement de modifications pour un compte donné, essayez à nouveau après quelques heures.

[**Polices d’appel**](teams-calling-policy.md): les stratégies d’appel dans Teams contrôlent les fonctionnalités d’appel disponibles pour les utilisateurs. Teams inclut la stratégie d’appel AllowCalling intégrée, dans laquelle toutes les fonctionnalités d’appel sont désactivées. Pour activer toutes les fonctionnalités d’appel, affectez la stratégie AllowCalling. Vous pouvez également créer une stratégie d’appel personnalisée pour activer les fonctionnalités d’appel de votre souhaitez et les affecter aux utilisateurs. 

[**Stratégies de**](meeting-policies-in-teams.md)réunion : Les stratégies de réunion dans Teams contrôlent les types de réunions que les utilisateurs peuvent créer et les fonctionnalités disponibles pour les participants à la réunion qui sont prévues par les utilisateurs de votre organisation. Teams inclut la stratégie de réunion AllOn intégrée, dans laquelle toutes les fonctionnalités de réunion sont désactivées. Pour activer toutes les fonctionnalités de réunion, affectez la stratégie AllOn. Vous pouvez également créer une stratégie de réunion personnalisée pour activer les fonctionnalités de réunion que vous souhaitez et affecter aux utilisateurs.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Attribuer des stratégies à l’aide du Centre d’administration Microsoft Teams

Pour affecter la stratégie d’appel AllowCalling et la stratégie de réunion AllOn à un utilisateur :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **Utilisateurs.**
2. Sélectionnez l’utilisateur en cliquant à gauche du nom de celui-ci, puis cliquez sur **Modifier les paramètres**.
3. Procédez comme suit :
    1.  Sous **Stratégie d’appel,** **cliquez sur AllowCalling.**
    2.  Sous **Stratégie de réunion,** cliquez **sur AllOn.**
4. Cliquez sur **Appliquer**.

Pour affecter une stratégie à plusieurs utilisateurs à la fois :

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à **Utilisateurs**, puis recherchez les utilisateurs ou filtrez l’affichage pour afficher les utilisateurs souhaités.
2. Dans la colonne **&#x2713;** (coche), sélectionnez les utilisateurs. Pour sélectionner tous les utilisateurs, cliquez sur **&#x2713;** (coche) dans la partie supérieure du tableau.
3. Cliquez sur **Modifier les paramètres**, apportez les modifications souhaitées, puis cliquez sur **Appliquer**.

Vous pouvez également :

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à la stratégie que vous voulez attribuer. Par exemple :
    - Consultez **les**  >  **stratégies d’appel** vocal, puis cliquez **sur AllowCalling.**
    - Allez dans **stratégies**  >  **de réunion Réunions,** puis cliquez sur **AllOn.**
2. Sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs**, recherchez l’utilisateur par son nom complet ou son nom d’utilisateur, sélectionnez le nom, puis cliquez sur **Ajouter**. Répétez cette étape pour chaque utilisateur que vous souhaitez ajouter.
4. Lorsque vous avez terminé d’ajouter des utilisateurs, cliquez sur **Enregistrer.**

#### <a name="assign-policies-using-powershell"></a>Attribuer des stratégies à l’aide de PowerShell

L’exemple suivant montre comment utiliser [grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) pour affecter la stratégie d’appel AllowCalling à un utilisateur.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies d’appel, voir [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

L’exemple suivant montre comment utiliser la politique de réunion [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) pour affecter la stratégie de réunion AllOn à un utilisateur.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Pour en savoir plus sur l’utilisation de PowerShell pour gérer les stratégies de réunion, voir [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>Contrôler le mode de secours dans Teams

Lorsque les utilisateurs se connectent à partir d’un point de terminaison non pris en compte, ils sont en mode de récupération, dans lequel AV n’est pas optimisé. Vous pouvez désactiver ou activer le mode de récupération en settingant l’une des valeurs DWORD de Registre suivantes :

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Pour désactiver le mode de récupération, définissez la valeur **1.** Pour activer l’audio uniquement, définissez la valeur **sur 2.** Si la valeur n’est pas présente ou est définie sur **0** (zéro), le mode de récupération est activé.

Cette fonctionnalité est disponible dans Teams version 1.3.00.13565 et ultérieures.

## <a name="known-issues-and-limitations"></a>Problèmes et limitations connus

### <a name="client-deployment-installation-and-setup"></a>Déploiement, installation et configuration de clients

- Avec l’installation par ordinateur, Teams sur VDI n’est pas automatiquement mis à jour comme le sont les clients Teams autres que VDI. Vous devez mettre à jour l’image VM en installant un nouveau MSI comme décrit dans la section Installer ou mettre à jour l’application de bureau [Teams sur VDI.](#install-or-update-the-teams-desktop-app-on-vdi) Vous devez désinstaller la version actuelle pour mettre à jour vers une version plus récente.
- Les équipes doivent être déployées par utilisateur ou par ordinateur. Le déploiement de Teams pour les utilisateurs simultanés et par ordinateur n’est pas pris en charge. Pour migrer d’un mode par ordinateur ou par utilisateur vers l’un de ces modes, suivez la procédure de désinstallation et redéployer l’un ou l’autre.
- Pour le moment, les logiciels de bureau virtuels Windows et VMware ne peuvent pas prise en charge les clients MacOS et Linux.
- Citrix ne prend pas en charge les clients MacOs pour le moment.
- Citrix ne prend pas en charge l’utilisation de proxies HTTP explicites définis sur un point de terminaison.

### <a name="calling-and-meetings"></a>Appels et réunions

Les fonctionnalités d’appel et de réunion suivantes ne sont pas pris en charge :

- Services d’urgence améliorés
- Boutons HID et contrôles LED entre l’application Teams et les appareils
- Flou et effets d’arrière-plan
- Rôles de producteur et de présentateur de diffusion et d’événement en direct
- Location-Based routage des biens (LBR)
- Parcage d'appel
- File d’attente d’appels
- Son système/ordinateur partagé
- Contournement de média pour le routage Direct

> [!NOTE]
> Nous travaillons à l’ajout de fonctionnalités d’appel et de réunion qui sont actuellement disponibles uniquement dans les environnements non VDI. Ceux-ci peuvent inclure un contrôle plus administratif sur la qualité, des scénarios de partage d’écran supplémentaires et des fonctionnalités avancées récemment ajoutées à Teams. Contactez votre représentant Teams pour en savoir plus sur les fonctionnalités à venir.

Voici des problèmes connus et des limitations pour les appels et les réunions :

- L’interopérabilité avec Skype Entreprise est limitée aux appels audio. il n’existe pas de modalité vidéo.
- Seul un seul flux vidéo entrant est pris en charge dans les réunions ou les appels de groupe. Lorsque plusieurs personnes envoient de la vidéo, seule la vidéo du principal orateur s’affiche à un moment donné.
- La résolution des flux vidéo entrants et sortants est limitée à la résolution 720p. Il s’agit d’une limitation WebRTC.
- Un seul flux vidéo d’une caméra ou d’un flux de partage d’écran entrant est pris en charge. Lorsqu’un partage d’écran entrant est partagé, ce partage d’écran s’affiche à la place de la vidéo du principal orateur.
- Teams ne bascule pas pour utiliser le dernier périphérique audio qu’un utilisateur a sélectionné, si l’appareil est déconnecté, puis reconnecté.
- Partage d’écran sortant :
    - Le partage d’applications n’est pas pris en charge.
- Prenez le contrôle :
    - Non pris en charge lors d’une session de partage d’écran ou d’application.
    - Prise en charge pendant une session de partage PowerPoint.
- Limitations citrix-only
    - Lors du partage d’écran dans une configuration multi-écran, seul le moniteur principal est partagé.
    - La mise à l’échelle DPI élevée sur CWA n’est pas prise en charge.

Pour les problèmes connus de Teams qui ne sont pas liés à VDI, consultez Équipes [de support dans votre organisation.](Known-issues.md)

## <a name="troubleshooting"></a>Résolution des problèmes

### <a name="troubleshoot-citrix-components"></a>Résoudre les problèmes des composants Citrix

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams se crashe ou l’écran de sign in Teams est vide

Il s’agit d’un problème connu avec Citrix VDA versions 1906 et 1909. Pour contourner ce problème, ajoutez la valeur DWORD de Registre suivante et définissez-la sur 204 (hexadécimal).

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Redémarrez ensuite VDA. Pour en savoir plus, consultez cet article de support citrix, qui décrit l’optimisation [HDX pour Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Sujets associés

- [Installer Microsoft Teams à l’aide de MSI](msi-deployment.md)
- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Utiliser Microsoft Teams sur un ordinateur de bureau Virtuel Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
