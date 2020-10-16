---
title: Configuration matérielle requise pour Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Dans cet article, vous allez découvrir la configuration matérielle requise pour l’installation et l’exécution de Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 472436eb4dd9f27d6e170ed723c243c002115d9b
ms.sourcegitcommit: d7e0406276def8bc731aa6dcbd49802441ec5138
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48476649"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Configuration matérielle requise pour Microsoft Teams

Toutes les conditions requises dans les sections suivantes s’appliquent à la fois à l’application de bureau Microsoft Teams et à l’application Web Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Configuration matérielle requise pour les équipes sur un PC Windows

| Composant | Condition requise |
|---------|---------|
|Ordinateur et processeur    | Minimum 1,6 GHz (ou plus), 2 cœurs        |
|Mémoire     |    4,0 GO DE MÉMOIRE VIVE (RAM)     |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Affichage    |   Résolution d’écran 1024 x 768 |
|Matériel graphique |  Système d’exploitation Windows : l’accélération graphique matérielle nécessite DirectX 9 ou version ultérieure, avec le WDDM 2,0 ou une version ultérieure pour Windows 10 (ou WDDM 1,3 ou version ultérieure pour Windows 10, mettre à jour les créateurs)
|Système d’exploitation  |    Windows 10, Windows 10 sur ARM, Windows 8,1, Windows Server 2019, Windows Server 2016|
|Version de .NET    |  Requiert .NET 4.5 CLR ou version ultérieure.       |
|Vidéo    |  Caméra vidéo USB 2.0       |
|Appareils    |   Caméra d’ordinateur portable standard, microphone et haut-parleurs    |
|Appels vidéo et réunions|<ul><li>Nécessite le processeur 2 cœur. Pour une résolution de partage et une fréquence d’images plus élevée, il est recommandé de disposer d’un processeur 4 cœurs ou d’une meilleure qualité.</li> <li>Les effets vidéo en arrière-plan requièrent Windows 10 ou un processeur avec l’instruction AVX2 définie.</li> <li>Voir [Recommandations relatives le pilote matériel décodeur et encodeur](hardware-decoders-and-encoders.md) pour consulter la liste des décodeurs et encodeurs matériels non pris en charge.</li><li>La participation à une réunion à l’aide d’une détection de proximité dans une salle Microsoft teams nécessite la technologie Bluetooth LE, qui nécessite l’activation de la technologie Bluetooth sur le périphérique client, et pour les clients Windows, le client teams 64 est également requis. Cette fonctionnalité n’est pas disponible pour les clients d’équipes 32 bits.</li></ul> |
|Événements en direct Teams | Si vous produisez un événement en direct Teams, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur i5 Kaby Lake, d’une RAM de 4,0 Go (ou d’une version ultérieure) et d’un codeur matériel. Voir recommandations en matière de périphériques d’encodage [et de décodage matériel](hardware-decoders-and-encoders.md) pour obtenir une liste de décodeurs et d’encodeurs **non pris en charge** . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Configuration matérielle requise pour Teams sur un Mac

| Composant | Condition requise |
|---------|---------|
|Ordinateur et processeur    | Processeur Intel Core Duo |
|Mémoire     |   4,0 GO DE MÉMOIRE VIVE (RAM)      |
|Disque dur    |   1,5 Go d’espace disque disponible      |
|Affichage    | 1280 x 800 ou résolution supérieure    |
|Système d’exploitation  |    L’une des trois versions les plus récentes de macOS. Vous trouverez des informations sur les versions les plus récentes de macOS et sur la mise à niveau de votre version de [MacOS.](https://support.apple.com/en-us/HT201260) Par exemple, lorsque vous relâchez une nouvelle version de macOS, la nouvelle version et les deux qui la précèdent immédiatement deviennent les versions prises en charge.      |
|Vidéo  |    Webcam compatible     |
|Voix    |  Microphone et haut-parleurs compatibles, casque avec microphone ou appareil équivalent       |
|Appels vidéo et réunions | <ul><li>Nécessite le processeur 2 cœur. Pour une résolution de partage et une fréquence d’images plus élevée, il est recommandé de disposer d’un processeur 4 cœurs ou d’une meilleure qualité. </li><li>La participation à une réunion à l’aide de la détection de proximité dans une salle Microsoft teams n’est pas disponible sur macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Configuration matérielle requise pour Teams sur Linux

| Composant | Condition requise |
|---------|---------|
|Ordinateur et processeur    | 1,6 GHz (ou plus) (32 bits ou 64 bits), 2 cœurs        |
|Mémoire     |    4,0 GO DE MÉMOIRE VIVE (RAM)     |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Affichage    |   Résolution d’écran 1024 x 768 |
|Matériel graphique |  128 Mo de mémoire graphique
|Système d’exploitation  | Distribution Linux capable d’installer les applications DEB ou RPM. |
|Vidéo    |  Caméra vidéo USB 2.0       |
|Appareils    |   Caméra d’ordinateur portable standard, microphone et haut-parleurs    |
|Voix    |  Microphone et haut-parleurs compatibles, casque avec microphone ou appareil équivalent       |
|Appels vidéo et réunions | <ul><li>Nécessite le processeur 2 cœur. Pour une résolution de partage et une fréquence d’images plus élevée, il est recommandé de disposer d’un processeur 4 cœurs ou d’une meilleure qualité.</li><li>Rejoindre une réunion à l’aide de la détection de proximité dans une salle Microsoft Teams n’est pas disponible sur Linux.</li></ul>
|Distributions Linux prises en charge | Ubuntu 16.04 LTS, 18.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Configuration matérielle requise pour Teams sur les appareils mobiles

Vous pouvez utiliser Teams sur ces plateformes mobiles :

- Android : compatible avec les téléphones et tablettes Android.

  La prise en charge est limitée aux **quatre dernières** versions d’Android. Par exemple, quand une nouvelle version majeure de Android est publiée, l’exigence Android correspond à la nouvelle version et aux trois versions les plus récentes qui la précèdent.

- iOS : compatible avec iPhone, iPad et iPod touch.

  La prise en charge est limitée aux **deux** dernières versions principales d’iOS. Par exemple, quand une nouvelle version majeure d’iOS est publiée, l’exigence d’iOS est la nouvelle version et les versions les plus récentes qui la précèdent. L’effet de **flou facultatif mon arrière-plan** sur iOS nécessite un système d’exploitation d’IOS 12 ou d’une version ultérieure compatible avec les appareils suivants : iPhone 7 ou version ultérieure, iPad 2018 (sixième génération) ou version ultérieure, et l’iPod effleure 2019 (7e génération).

> [!Note]
> Pour une expérience optimale de Teams, utilisez la dernière version de votre système d’exploitation iOS et Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Configuration matérielle requise pour Teams dans un environnement VDI (Virtual Desktop Infrastructure)

Voir [Teams pour une infrastructure bureau virtualisée(VDI)](teams-for-vdi.md) pour plus d’informations sur la configuration requise pour l’exécution d’équipes dans un environnement virtualisé.

### <a name="related-topics"></a>Sujets associés

- [Obtenir les applications Teams](get-clients.md)
- [Microsoft Teams sur les appareils mobiles](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installer l’application Microsoft Teams à l’aide d’un fichier MSI](msi-deployment.md)
- [Limites et spécifications de Microsoft Teams](limits-specifications-teams.md)
