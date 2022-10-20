---
title: Obtenir des clients pour Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Apprenez à installer les différents clients disponibles pour Microsoft Teams sur les PC, les Mac et les appareils mobiles.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33175aecc41dbc631fe8ab16db225762969b5ad6
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614036"
---
# <a name="get-clients-for-microsoft-teams"></a>Obtenir des clients pour Microsoft Teams

> [!TIP]
> **Vous voulez installer Teams sur votre PC, Mac ou appareil mobile ?**  Consultez [installer le client Teams client.](https://go.microsoft.com/fwlink/?linkid=855754)

Microsoft Teams pouvez être installé sur des PC, des Mac et des appareils mobiles et vous pouvez également y accéder via un navigateur web. La plupart des utilisateurs finaux peuvent commencer à utiliser Teams en [installant simplement le client eux-mêmes](https://go.microsoft.com/fwlink/?linkid=855754). Une fois le client Teams installé, il leur suffit de se connecter avec leur nom d’utilisateur et mot de passe.

Si vous êtes un professionnel de l’informatique et que vous souhaitez en savoir plus sur l’expérience d’installation et les conditions requises pour Teams, sélectionnez un système d’exploitation client dans cet article pour plus d’informations.

Pour plus d’informations sur les fonctionnalités de chaque client sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-clients"></a>Clients de bureau

Le client de bureau Teams est disponible en tant qu’application autonome et dans le cadre de [Microsoft 365 Apps for enterprise](/deployoffice/teams-install) pour les systèmes d’exploitation suivants :

- Versions 32 bits et 64 bits de Windows (8.1 ou version ultérieure, à l’exception de Windows 10 LTSC) 
- ARM64 pour Windows 10 sur ARM 
- Windows Server (2012 R2 ou version ultérieure)
- macOS
- Linux (dans les formats `.deb` et `.rpm`)
- Système d’exploitation Chrome (pour plus d’informations, voir [Comment utiliser Microsoft Office sur un Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions. Admin permissions aren't required to install the Teams client on Windows PCs but are required on Macs.

Les professionnels de l’informatique peuvent choisir leur méthode préférée préfèrent pour distribuer les fichiers d’installation sur les ordinateurs de leur organisation. Certains exemples incluent Microsoft Endpoint Configuration Manager (Windows) ou JAMF Pro (macOS). Pour plus d’informations sur la distribution Teams, voir les informations suivantes.

- **Windows** [Installer Teams à l’aide de Endpoint Configuration Manager](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> La distribution du client via ces mécanismes s’effectue uniquement pour l’installation initiale des clients Teams et non pour les mises à jour futures. Pour plus d’informations sur le processus de mise à jour Teams, voir [Processus de mise à jour de Teams](teams-client-update.md).

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Regardez la session suivante pour en savoir plus sur les avantages du client bureau Windows, comment il le planifier et comment déployer : [Windows Teams Client de bureau](https://aka.ms/teams-clients)

Teams sur Windows met à disposition des programmes d’installation MSI téléchargeables dans les architectures [32 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true), [64 bits](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true) et [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true). L’architecture x86 (32 bits et 64 bits) de Teams est agnostique à l’architecture de Windows et d’Office installée. Nous vous recommandons la version 64 bits de Teams sur les systèmes 64 bits.

Teams nécessite .NET Framework 4,5 ou version ultérieure. Si .NET Framework ou version ultérieure n’est pas installée, le programme d’installation Teams proposera de l’installer à votre place.

The Windows client is deployed to the AppData folder located in the user’s profile. Deploying to the user’s local profile allows the client to be installed without requiring elevated permissions. The Windows client leverages the following locations:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- % LocalAppData%\\SquirrelTemp

When users initiate a call using the Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication. Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> La configuration du Pare-feu Windows sera modifiée. Deux règles de trafic entrant pour teams.exe pour les protocoles TCP et UDP seront créées avec 
> - Autorisez l’action si l’utilisateur est un administrateur local et clique sur « Autoriser l’accès » uniquement.
> - Bloquer l’action si l’utilisateur n’est pas un administrateur local et, dans tous les cas, lorsque l’invite est ignorée en sélectionnant « Annuler ».

Si vous souhaitez empêcher que Teams invite les utilisateurs à créer des règles de pare-feu lorsque les utilisateurs font leur premier appel à partir de Teams, utilisez le script PowerShell dans [Exemple de script – Script PowerShell de pare-feu Microsoft Teams](client-firewall-script.md).

### <a name="mac"></a>[Mac](#tab/Mac)

Les utilisateurs de Mac peuvent installer Teams à l’aide d’un fichier d’installation PKG pour ordinateurs macOS. L’accès administrateur est requis pour installer le client Mac. Le client macOS est installé dans le dossier /Applications.

1. À partir de la [page de téléchargement Teams](https://teams.microsoft.com/downloads), sous **Mac**, cliquez sur **Télécharger**.
2. Double-cliquez sur le fichier PKG.
3. Suivez les indications de l'Assistant Installation pour effectuer l'installation.
4. Teams sera installé dans le dossier /Applications. Il s’agit d’une installation à l’échelle de l’ordinateur.

> [!NOTE]
> Pendant l’installation, le PKG invite à entrer des informations d’identification d’administrateur. L’utilisateur doit entrer les informations d’identification d’administrateur, peu importe si l’utilisateur est un administrateur.

Si un utilisateur a une installation DMG de Teams et souhaite la remplacer par l’installation PKG, l’utilisateur doit :

1. Quitter l’application Teams.
2. Désinstaller l’application Teams.
3. Installez le fichier PKG.

Les professionnels de l’informatique peuvent utiliser une solution de déploiement gérée, telle que Jamf Pro, pour distribuer les fichiers d’installation Teams vers tous les Mac de leur organisation.

### <a name="linux"></a>[Linux](#tab/Linux)

Sur Linux, les responsables de package tels que `apt` et `yum` tentent d’installer les conditions requises pour vous. Toutefois, si ce n’est pas le cas, vous devez installer les conditions requises avant d’installer Teams sur Linux.

Les utilisateurs peuvent installer des packages Linux natifs au format `.deb` et `.rpm`. L’installation du package DEB ou RPM permet d’installer automatiquement le référentiel du package.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

La clé de signature permettant d’activer la mise à jour automatique à l’aide du gestionnaire de package du système est installée automatiquement. Toutefois, elle peut également se trouver dans : <https://packages.microsoft.com/keys/microsoft.asc>. Teams délivre tous les mois et, si le référentiel a été installé correctement, le gestionnaire de votre package système doit gérer la mise à jour automatique de la même façon que les autres packages sur le système.

#### <a name="install-teams-using-deb-package"></a>Installer Teams avec le package DEB

1. Téléchargez le package à partir de <https://aka.ms/getteams>.
2. Installez à l’aide de l'une des opérations suivantes :
    - Ouvrez l’outil de gestion des packages approprié et suivez le processus d’installation de l’application Linux auto-guidée.
    - Ou, si vous aimez Terminal, tapez : `sudo dpkg -i **teams download file**`

Vous pouvez lancer Teams via les activités ou via un Terminal en tapant `teams`.

#### <a name="install-teams-using-rpm-package"></a>Installer Teams avec le package RPM

1. Téléchargez le package à partir de <https://aka.ms/getteams>.
2. Installez à l’aide de l'une des opérations suivantes :
    - Ouvrez l’outil de gestion des packages approprié et suivez le processus d’installation de l’application Linux auto-guidée.
    - Ou, si vous aimez Terminal, tapez : `sudo yum install **teams download file**`

Vous pouvez lancer Teams via les activités ou via un Terminal en tapant `teams`.

#### <a name="install-manually-from-the-command-line"></a>Installez manuellement à partir de la ligne de commande

Installez manuellement sur des distributions Debian et Ubuntu :

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg

sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

Installez manuellement sur des distributions basées sur RHEL, Fedora et CentOS :

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

Vous pouvez également utiliser YUM au lieu de DNF :

```bash
yum check-update
sudo yum install teams
```

Installez manuellement sur des distributions basées sur openSUSE :

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>Clients mobiles

The Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls. For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.

Les plateformes mobiles prises en charge pour les applications mobiles Teams sont les suivantes :

- **Android** : la prise en charge est limitée aux quatre dernières versions principales d’Android. Lors de la publication d’une nouvelle version majeure d’Android, la nouvelle version et les trois versions précédentes sont officiellement prises en charge.

- **iOS** : la prise en charge est limitée aux deux versions principales d’iOS les plus récentes. Lors de la publication d’une nouvelle version majeure d’iOS, la nouvelle version of iOS et les versions précédentes sont officiellement prises en charge.

> [!NOTE]
> La version mobile doit être disponible au public pour que Teams fonctionne comme prévu.

Les applications mobiles sont distribuées et mises à jour via app store de la plateforme mobile respective uniquement. La distribution des applications mobiles via la gestion des périphériques mobiles ou le chargement de côte n’est pas prise en charge par Microsoft. Une fois l’application mobile installée sur une plateforme mobile prise en charge, l’application mobile Teams elle-même est prise en charge, sous réserve que la version se trouve dans un délai de trois mois après la publication actuelle.

Si vous êtes en Chine, vous pouvez installer Teams à partir des stores d’applications suivants :

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** : Recherchez « Teams » sur le store Oppo
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

> [!NOTE]
> Lorsque les utilisateurs installent Teams à partir de l’un des magasins d’applications Android basés en Chine et activent les notifications Push pour Teams, Microsoft fournit des notifications Push Teams via un service de notification Push basé sur la Chine.

## <a name="browser-client"></a>Client de navigateur

Le client de navigateur ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est un client fonctionnel complet qui peut être utilisé à partir de divers navigateurs. Le client de navigateur prend en charge les appels et les réunions en utilisant webRTC, de sorte qu’aucun plug-in ou téléchargement n’est requis pour exécuter Teams dans un navigateur. Le navigateur doit également être configuré de manière à autoriser les cookies tiers.

[!INCLUDE [browser-support](includes/browser-support.md)]

The browser client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753). If an unsupported browser version is detected, it will block access to the browser interface and recommend that the user download the desktop client or mobile app.
