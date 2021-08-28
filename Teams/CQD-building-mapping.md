---
title: Créer une carte de bâtiments pour le tableau de bord de qualité des appels
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Découvrez comment créer une carte de bâtiment que vous pouvez utiliser pour charger des données client et bâtiment dans le tableau de bord de qualité des appels.
ms.openlocfilehash: a119324090d05b593eb1ed66f41efbb7a5bd7a0a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634098"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a>Créer une carte de bâtiments pour le tableau de bord de qualité des appels

Dans un déploiement Microsoft Teams ou Skype Entreprise Online, tous les clients sont externes. Par conséquent, par défaut, tous les clients sont signalés comme externes dans le tableau de bord de qualité des appels, que le client soit connecté ou non sur un réseau d’entreprise interne.

Lorsque vous travaillez avec le DQD, vous devez connaître l’emplacement d’un point de terminaison et savoir s’il était connecté à un réseau que vous pouvez gérer ou qu’il ne peut pas gérer, l’hypothèse étant que vous pouvez seulement améliorer les réseaux que vous pouvez gérer. En chargeant le sous-réseau et en insérant les informations sur le CQD, vous activez le point de terminaison pour déterminer si le point de terminaison était connecté à un réseau interne (géré) ou à un réseau externe (non géré). C’est pourquoi il est important de créer une carte de bâtiments pour votre organisation et [de la télécharger sur le CQD.](CQD-upload-tenant-building-data.md)

## <a name="building-mapping-tools"></a>Outils de mappage des bâtiments

Il existe plusieurs façons de ma carte des sous-réseaux de votre organisation. Si vous avez besoin d’aide, vous pouvez utiliser le module PowerShell CQDTools décrit dans ce [billet de blog.](https://aka.ms/cqdtools) Ces outils sont basés sur PowerShell et utilisent les sites et services Active Directory (AD) et les services DHCP Microsoft pour pré-remplir votre fichier de construction. Les outils suivants vous aideront dans les tâches suivantes :

1. recherchez des sites et services AD, puis créez un fichier de construction basé sur les informations contenues dans celui-ci.
1. Interrogez un ou plusieurs serveurs DHCP Microsoft pour obtenir des informations de sous-réseau et créer automatiquement un fichier de bâtiment.
1. Validez un fichier de construction existant, en vérifiant la recherche de doublons et de chevauchements.
1. Recherchez des sous-réseaux non mis en réseau dans le DQD.

## <a name="related-topics"></a>Rubriques connexes

[Télécharger données relatives au client et à la création dans le CQD](CQD-upload-tenant-building-data.md)