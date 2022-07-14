---
title: Créer une carte de construction pour le tableau de bord de qualité des appels (CQD)
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment créer une carte de bâtiment que vous pouvez utiliser pour charger le locataire et générer des données dans le tableau de bord de qualité des appels (CQD).
ms.openlocfilehash: 71d1872bbd81769f9a49f4ca9f6ac9aae641252f
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789819"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Créer une carte de construction pour le tableau de bord de qualité des appels (CQD)

Dans un déploiement Microsoft Teams ou Skype Entreprise Online, tous les clients sont externes. Par conséquent, par défaut, tous les clients sont signalés comme externes dans le tableau de bord de qualité des appels (CQD), que le client soit connecté ou non à un réseau d’entreprise interne.

Lorsque vous travaillez avec CQD, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il a été connecté à un réseau que vous pouvez gérer ou à un réseau que vous ne pouvez pas gérer, l’hypothèse étant que vous pouvez uniquement améliorer les réseaux que vous pouvez gérer. En chargeant le sous-réseau et en créant des informations sur CQD, vous activez CQD pour déterminer si le point de terminaison a été connecté à un réseau interne (géré) ou à un réseau externe (non managé). C’est pourquoi il est important de créer une carte de construction pour votre organisation et de [la charger dans CQD](CQD-upload-tenant-building-data.md).

## <a name="building-mapping-tools"></a>Génération d’outils de mappage

Il existe de nombreuses façons de mapper les sous-réseaux de votre organisation. Si vous avez besoin d’aide, vous pouvez utiliser le module PowerShell CQDTools décrit dans ce [billet de blog](https://aka.ms/cqdtools). Ces outils sont basés sur PowerShell et utilisent des sites et services Active Directory (AD) et des services Microsoft DHCP pour vous aider à préremplir votre fichier de génération. Ces outils vous aideront dans les tâches suivantes :

1. Interrogez les sites et services AD, puis créez un fichier de construction basé sur les informations contenues dans ce fichier.
1. Interrogez un ou plusieurs serveurs Microsoft DHCP pour extraire des informations de sous-réseau et créer automatiquement un fichier de génération.
1. Validez un fichier de construction existant, en recherchant les doublons et les chevauchements.
1. Recherchez des sous-réseaux non mappés dans CQD.

## <a name="related-topics"></a>Sujets associés

[Charger le locataire et générer des données dans CQD](CQD-upload-tenant-building-data.md)