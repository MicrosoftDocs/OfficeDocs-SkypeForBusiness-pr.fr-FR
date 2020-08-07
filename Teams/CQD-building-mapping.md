---
title: Créer une carte de bâtiment pour le tableau de bord de qualité des appels (bord)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment créer une carte de bâtiment que vous pouvez utiliser pour charger un client et générer des données dans le tableau de bord de qualité des appels (bord).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584033"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Créer une carte de bâtiment pour le tableau de bord de qualité des appels (bord)

Dans le cas d’un déploiement de Microsoft teams ou de Skype entreprise Online, tous les clients sont externes. Par défaut, tous les clients sont signalés comme extérieurs dans le tableau de bord de qualité des appels (bord), que le client soit connecté ou non au réseau d’entreprise interne.

Lorsque vous utilisez bord, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il est connecté à un réseau que vous pouvez gérer ou un réseau que vous ne pouvez pas gérer, en partant du principe que vous pouvez uniquement améliorer les réseaux que vous pouvez gérer. En chargeant les informations de sous-réseau et en bâtiment des informations dans bord, vous activez bord pour déterminer si le point de terminaison a été connecté à un réseau interne (géré) ou à un réseau externe (non géré). C’est pourquoi il est important de créer une carte de bâtiment pour votre organisation et de la [Télécharger sur bord](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Outils de mappage de construction

Il existe de nombreuses façons de mapper les sous-réseaux de votre organisation. Si vous avez besoin d’aide, vous pouvez utiliser le module PowerShell d’CQDTools décrit dans ce [billet de blog](https://aka.ms/cqdtools). Ces outils sont basés sur PowerShell et utilisent des sites et services Active Directory (AD) et des services Microsoft DHCP pour vous aider à préremplir votre fichier de construction. Ces outils peuvent vous aider à effectuer les tâches suivantes :

1. Interrogez les sites et services d’annonces et créez un fichier d’immeuble en fonction des informations contenues dans.
1. Interrogez un serveur ou un serveur DHCP Microsoft pour extraire des informations de sous-réseau et créer automatiquement un fichier de bâtiment.
1. Validez un fichier de construction existant, en recherchant les doublons et les chevauchements.
1. Recherchez les sous-réseaux non mappés dans bord.

## <a name="related-topics"></a>Voir aussi

[Télécharger le client et générer des données dans bord](CQD-upload-tenant-building-data.md)