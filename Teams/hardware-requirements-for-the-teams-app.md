---
title: Configuration matérielle requise pour Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.localizationpriority: high
search.appverid: MET150
description: Dans cet article, vous découvrirez la configuration matérielle requise pour installer et exécuter Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39025c0ccd9cb3b7bc02de85719f98f4ec7f3090
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860067"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Configuration matérielle requise pour Microsoft Teams

Toutes les conditions requises dans les sections suivantes s’appliquent à la fois à l’application de bureau Microsoft Teams et à l’application Web Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Configuration matérielle requise pour les équipes sur un PC Windows

| Composant | Configuration requise |
|---------|---------|
|Ordinateur et processeur    | Minimum 1,1 GHz ou plus rapide, 2 noyaux<br><br>Remarque : pour les processeurs Intel, la vitesse maximale obtenue à l’aide de la technologie Intel Turbo Boost (fréquence turbo max) doit être prise en compte.         |
|Mémoire     |  4.0 GB de RAM |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Affichage    |   Résolution d’écran 1024 x 768 |
|Matériel graphique |  Système d’exploitation Windows : l’accélération matérielle graphique nécessite DirectX 9 ou une version ultérieure, avec WDDM 2.0 ou une version ultérieure pour Windows 10 (ou WDDM 1.3 ou une version ultérieure pour Windows 10 Fall Creators Update)
|Système d’exploitation  |    Windows 11, Windows 10 (à l’exception de Windows 10 LTSC), Windows 10 sur ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. Remarque : nous vous recommandons d’utiliser la dernière version de Windows et les correctifs de sécurité disponibles.|
|Version de .NET    |  Requiert .NET 4.5 CLR ou version ultérieure.       |
|Vidéo    |  Caméra vidéo USB 2.0       |
|Appareils    |   Caméra d’ordinateur portable standard, microphone et haut-parleurs    |
|Appels vidéo et réunions|<ul><li>Nécessite un processeur à deux cœurs. Pour une résolution de partage vidéo/d’écran et une fréquence d’images plus élevées, il est recommandé d’utiliser un processeur à quatre cœurs ou mieux.</li> <li>Les effets vidéo d’arrière-plan nécessitent Windows 10 ou un processeur avec le jeu d’instructions AVX2.</li> <li>Consultez l’article [Recommandations relatives au pilote matériel décodeur et encodeur](hardware-decoders-and-encoders.md) pour consulter la liste des décodeurs et encodeurs non pris en charge.</li><li>Participer à une réunion à l’aide de la détection de proximité dans une salle Microsoft Teams nécessite le Bluetooth LE, qui nécessite l’activation du Bluetooth sur l’appareil client. Pour les clients Windows, le client Teams 64 bits est nécessaire. Cette fonctionnalité n’est pas disponible sur les clients Teams 32 bits.</li></ul> |
|Événements en direct Teams | Si vous générez des événements en direct Teams, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur Kaby Lake Core i5, d’une RAM de 4,0 Go (ou plus) et d’un codeur matériel. Consultez l’article [Recommandations relatives au pilote matériel décodeur et encodeur](hardware-decoders-and-encoders.md) pour consulter la liste des décodeurs et encodeurs **non pris en charge**. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Configuration matérielle requise pour Teams sur Mac

| Composant | Configuration requise |
|---------|---------|
|Ordinateur et processeur    | Processeur Intel Core Duo |
|Mémoire     |   4.0 GB de RAM|
|Disque dur    |   1,5 Go d’espace disque disponible      |
|Affichage    | 1280 x 800 ou résolution supérieure    |
|Système d’exploitation  |    L’une des trois versions les plus récentes de macOS. Vous trouverez des informations sur les dernières versions de macOS et comment mettre à jour votre version de macOS [ici](https://support.apple.com/en-us/HT201260). Par exemple, lorsqu’une nouvelle version de macOS est publiée, la nouvelle version et les deux versions qui la précèdent deviennent les versions prises en charge.      |
|Vidéo  |    Webcam compatible     |
|Voix    |  Microphone et haut-parleurs compatibles, casque avec microphone ou appareil équivalent       |
|Appels vidéo et réunions | <ul><li>Nécessite un processeur à deux cœurs. Pour une résolution de partage vidéo/d’écran et une fréquence d’images plus élevées, il est recommandé d’utiliser un processeur à quatre cœurs ou mieux. </li><li>Rejoindre une réunion à l’aide de la détection de proximité dans une salle Microsoft Teams n’est pas disponible sur Linux.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Configuration matérielle requise pour Teams sur Linux

| Composant | Configuration requise |
|---------|---------|
|Ordinateur et processeur    | 1,6 GHz (ou plus) (32 bits ou 64 bits), 2 cœurs        |
|Mémoire     |    4.0 GB de RAM |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Affichage    |   Résolution d’écran 1024 x 768 |
|Matériel graphique |  Mémoire graphique de 128 Mo
|Système d’exploitation  | Distribution Linux capable d’installer les applications DEB ou RPM. |
|Vidéo    |  Caméra vidéo USB 2.0       |
|Appareils    |   Caméra d’ordinateur portable standard, microphone et haut-parleurs    |
|Voix    |  Microphone et haut-parleurs compatibles, casque avec microphone ou appareil équivalent       |
|Appels vidéo et réunions | <ul><li>Nécessite un processeur à deux cœurs. Pour une résolution de partage vidéo/d’écran et une fréquence d’images plus élevées, il est recommandé d’utiliser un processeur à quatre cœurs ou mieux.</li><li>Rejoindre une réunion à l’aide de la détection de proximité dans une salle Microsoft Teams n’est pas disponible sur Linux.</li></ul>
|Distributions Linux prises en charge | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|Environnement de bureau pris en charge | GNOME, KDE       |
|Serveur d’affichage pris en charge | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Configuration matérielle requise pour Teams sur les appareils mobiles

Vous pouvez utiliser Teams sur ces plateformes mobiles :

- Android : compatible avec les téléphones et tablettes Android.

  La prise en charge est limitée aux **quatre dernières** versions majeures d’Android. Par exemple, lorsqu’une nouvelle version majeure d’Android est publiée, la configuration requise pour Android est la nouvelle version et les trois versions les plus récentes qui l’ont précédée.

- iOS : compatible avec iPhone, iPad et iPod touch.

  La prise en charge est limitée aux **deux** versions majeures d’iOS les plus récentes. Par exemple, lorsqu’une nouvelle version majeure d’iOS est publiée, la configuration requise pour iOS est la nouvelle version et les versions les plus récentes qui l’ont précédée. L’effet vidéo facultatif **Flouter mon arrière-plan** sur iOS nécessite un système d’exploitation iOS 12 ou une version ultérieure, compatible avec les appareils suivants : iPhone 7 ou une version ultérieure, iPad 2018 (6e génération) ou une version ultérieure et iPod touch 2019 (7e génération).

> [!Note]
> Pour une expérience optimale de Teams, utilisez la dernière version de votre système d’exploitation iOS et Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Configuration matérielle requise pour Teams dans un environnement VDI (Virtual Desktop Infrastructure)

Voir [Teams pour une infrastructure bureau virtualisée(VDI)](teams-for-vdi.md) pour plus d’informations sur la configuration requise pour l’exécution d’équipes dans un environnement virtualisé.

### <a name="related-topics"></a>Sujets associés

- [Obtenir les applications Teams](get-clients.md)
- [Microsoft Teams sur les appareils mobiles](https://support.microsoft.com/office/set-up-your-teams-mobile-apps-1ba8dce3-1122-47f4-8db6-00a4f93117e8)
- [Installer l’application Microsoft Teams à l’aide d’un fichier MSI](msi-deployment.md)
- [Limites et spécifications de Microsoft Teams](limits-specifications-teams.md)
