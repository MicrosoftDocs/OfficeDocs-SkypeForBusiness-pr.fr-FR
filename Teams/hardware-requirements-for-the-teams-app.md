---
title: Configuration matérielle requise pour l’application Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/04/2019
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: En savoir plus sur la configuration matérielle requise pour l’installation et l’exécution de Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c33a0ed8bf88469e6e9ab41a049a1d566cc686b
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/13/2019
ms.locfileid: "40019958"
---
# <a name="hardware-requirements-for-the-microsoft-teams-app"></a>Configuration matérielle requise pour l’application Microsoft Teams

Toutes les exigences des sections suivantes s’appliquent à l’application de bureau teams et à l’application Web Teams.

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-windows-pc"></a>Configuration matérielle requise pour l’application de bureau teams sur un PC Windows

|**Composant**|**Condition requise**  |
|---------|---------|
|Ordinateur et processeur    | Minimum 1,6 GHz (ou plus) (32 bits ou 64 bits).        |
|Mémoire     |    2,0 GO DE MÉMOIRE VIVE (RAM)     |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Display    |   résolution d’écran 1024 x 768 |
|Matériel vidéo |  Minimum de 128 Mo de mémoire graphique
|Système d’exploitation  |    Windows 10, Windows 8,1 ou Windows 7 Service Pack 1 en 32 bits et 64 bits. Pour une utilisation optimale, utilisez la version la plus récente de tout système d’exploitation.|
|Version .NET    |  Nécessite .NET 4,5 CLR ou version ultérieure       |
|Vidéo    |  Caméra vidéo USB 2,0       |
|Appareils    |   Caméra, micro et haut-parleurs pour ordinateur portable standard    | 
|Appels et réunions vidéo | <ul><li>Pour une meilleure expérience des appels vidéo et des réunions en ligne, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur cadencé à 2,0 GHz et d’une RAM 4,0 Go (ou une version ultérieure). </li><li>L’effet de **brouillage facultatif mon arrière-plan** exige un processeur doté d’une prise en charge de la fonction AVX2 (Advanced Vector Extensions 2). Voir recommandations en matière de périphériques d’encodage [et de décodage matériel](hardware-decoders-and-encoders.md) pour obtenir une liste de décodeurs et d’encodeurs non pris en charge.</li><li>La participation à une réunion à l’aide d’une détection de proximité dans une salle Microsoft teams nécessite le Bluetooth LE, qui nécessite l’activation de la technologie Bluetooth sur le périphérique client, et pour les clients Windows, le client teams 64 est requis. Elle n’est pas disponible pour les clients d’équipes 32 bits.</li></ul> |
|Événements en direct Teams | Si vous générez des événements en direct Teams, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur i5 Kaby Lake Core, d’une RAM de 4,0 Go (ou d’une version ultérieure) et d’un codeur matériel. Voir recommandations en matière de périphériques d’encodage [et de décodage matériel](hardware-decoders-and-encoders.md) pour obtenir une liste de décodeurs et d’encodeurs non pris en charge. |

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-mac"></a>Configuration matérielle requise pour l’application de bureau teams sur un Mac

|**Composant**|**Condition requise**  |
|---------|---------|
|Processeur    | Processeur Intel minimum, cœur 2 Duo ou version ultérieure |
|Mémoire     |   2,0 GO DE MÉMOIRE VIVE (RAM)      |
|Disque dur    |   1,5 Go d’espace disque disponible      |
|Display    | 1280 x 800 ou résolution supérieure    |
|Système d’exploitation  |    Mac OS X 10,11 El Capitan ou version ultérieure     |
|Vidéo  |    Webcam compatible     |
|Audio    |  Micro et haut-parleurs compatibles, casque avec micro ou appareil équivalent       |
|Appels et réunions vidéo | Pour une meilleure expérience des appels vidéo et des réunions en ligne, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur cadencé à 2,0 GHz et d’une RAM 4,0 Go (ou une version ultérieure).  <ul><li>L’effet de **brouillage facultatif mon arrière-plan** nécessite un processeur doté d’une prise en 2013 charge de la version 2 de AVX2 Voir recommandations en matière de périphériques d’encodage [et de décodage matériel](hardware-decoders-and-encoders.md) pour obtenir une liste de décodeurs et d’encodeurs non pris en charge.</li><li>La participation à une réunion à l’aide de la détection de proximité dans une salle Microsoft teams n’est pas disponible sur Mac OS.</li></ul> |

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-linux"></a>Configuration matérielle requise pour l’application de bureau teams sur un Linux

|**Composant**|**Condition requise**  |
|---------|---------|
|Ordinateur et processeur    | Minimum 1,6 GHz (ou plus) (32 bits ou 64 bits).        |
|Mémoire     |    2,0 GO DE MÉMOIRE VIVE (RAM)     |
|Disque dur    | 3,0 Go d’espace disque disponible        |
|Display    |   résolution d’écran 1024 x 768 |
|Matériel vidéo |  Minimum de 128 Mo de mémoire graphique
|Système d’exploitation  | Distribution Linux capable d’installer une DEB ou RPM. |
|Vidéo    |  Caméra vidéo USB 2,0       |
|Appareils    |   Caméra, micro et haut-parleurs pour ordinateur portable standard    | 
|Audio    |  Micro et haut-parleurs compatibles, casque avec micro ou appareil équivalent       |
|Appels et réunions vidéo | <ul><li>Pour une meilleure expérience des appels vidéo et des réunions en ligne, nous vous recommandons d’utiliser un ordinateur équipé d’un processeur cadencé à 2,0 GHz et d’une RAM 4,0 Go (ou une version ultérieure). </li><li>L’effet de brouillage facultatif mon arrière-plan nécessite un processeur doté d’une prise en 2013 charge de la version 2 de AVX2 Voir recommandations en matière de périphériques d’encodage [et de décodage matériel](hardware-decoders-and-encoders.md) pour obtenir une liste de décodeurs et d’encodeurs non pris en charge.</li><li>La participation à une réunion à l’aide de la détection de proximité dans une salle Microsoft teams n’est pas disponible dans Linux.</li></ul>
|Distributions Linux prises en charge | Ubuntu 16,04 LTS, 18,04 LTS, Fedora 30 Workstation, RHEL 8 Workstation CentOS 8


## <a name="hardware-requirements-for-the-teams-app-on-mobile-devices"></a>Configuration matérielle requise pour l’application teams sur les appareils mobiles

Vous pouvez utiliser teams sur les plateformes mobiles suivantes :

- Android-nécessite Android 5,0 ou une version ultérieure. Compatible avec les téléphones et tablettes Android.

  La prise en charge est limitée aux quatre dernières versions d’Android. Lorsqu’une nouvelle version majeure d’Android est publiée, la nouvelle version et les trois versions précédentes sont officiellement prises en charge.

- iOS : nécessite iOS 10,0 ou une version ultérieure. Compatible avec les iPhone, iPad et iPod effleure. 

  La prise en charge est limitée aux deux dernières versions principales d’iOS. Lorsqu’une nouvelle version majeure d’iOS est publiée, la nouvelle version d’iOS et la version précédente sont officiellement prises en charge.

Pour une utilisation optimale de Microsoft Teams, utilisez la dernière version d’iOS et Android.

## <a name="hardware-requirements-for-the-teams-app-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Configuration matérielle requise pour l’application teams dans un environnement VDI (Virtual Desktop Infrastructure)

Pour plus d’attentes concernant l’exécution d’équipes dans un environnement virtualisé, voir [teams pour l’infrastructure de bureau virtualisé](teams-for-vdi.md) . 

### <a name="related-topics"></a>Sujets associés
- [Obtenir des applications teams](get-clients.md)
- [Microsoft teams sur les appareils mobiles](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installation de l’application Microsoft teams à l’aide d’un fichier MSI](msi-deployment.md)
