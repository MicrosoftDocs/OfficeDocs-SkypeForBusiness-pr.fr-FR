---
title: Paramètres réseau pour les fonctionnalités voix Cloud
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez les paramètres réseau que vous devez configurer pour lLocation-Based routage pour le routage direct et les services d’urgence améliorés.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2165ea1e4e9732f0e840b4f0949b230f5243121d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769942"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Paramètres réseau pour les fonctionnalités vocales cloud dans Microsoft Teams

En savoir plus sur les régions réseau, les sites réseau, les sous-réseaux et les adresses IP fiables. Ces termes et concepts sont utilisés dans notre documentation vocale sur le cloud pour le routage basé sur l’emplacement pour le [routage direct](location-based-routing-plan.md) et les appels d’urgence [dynamiques.](configure-dynamic-emergency-calling.md) Si vous déployez ces fonctionnalités cloud dans votre organisation, vous devez configurer les paramètres réseau pour les utiliser avec ces fonctionnalités dans Microsoft Teams.

Cet article donne une vue d’ensemble des paramètres réseau courants pour les appels Location-Based d’urgence dynamiques et le routage dynamique. En fonction de la fonctionnalité voix cloud et des fonctionnalités que vous déployez, vous configurez tout ou partie de ces paramètres. Pour savoir comment configurer ces paramètres, voir Gérer votre topologie de réseau pour les fonctionnalités [cloud dans Teams.](manage-your-network-topology.md)

> [!NOTE]
> Les conditions requises spécifiques à une fonctionnalité pour les paramètres réseau sont consignées dans les rubriques de configuration relatives à cette fonctionnalité.

## <a name="network-region"></a>Région réseau

Une région réseau contient une collection de sites réseau. Il connecte différentes parties d’un réseau entre plusieurs zones géographiques. Par exemple, si votre organisation possède de nombreux sites situés en Inde, vous pouvez choisir de désigner « Inde » comme région réseau. Chaque site réseau doit être associé à une région réseau.

Les mêmes régions du réseau sont partagées par le Location-Based routage vers le routage direct et les services d’urgence améliorés. Si vous avez déjà créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin de créer de nouvelles régions réseau pour l’autre fonctionnalité.

## <a name="network-site"></a>Site réseau

Un site réseau représente un emplacement où votre organisation dispose d’un lieu physique, tel qu’un bureau, un ensemble de bâtiments ou un campus. Les sites réseau sont définis comme une collection de sous-réseaux IP. Chaque site réseau doit être associé à une région réseau.

Vous pouvez également utiliser des sites réseau pour activer et configurer les appels d’urgence.

## <a name="network-subnet"></a>Sous-réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau réseau et du site réseau associé. Vous pouvez associer plusieurs sous-réseaux au même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau.

Les informations de sous-réseau sont utilisées pour déterminer le site réseau sur lequel se trouve un point de terminaison lorsqu’une nouvelle session est lancée. Lorsque l’emplacement de chaque partie au cours d’une session est connu, la fonctionnalité voix cloud peut appliquer ces informations pour déterminer comment gérer la configuration ou le routage des appels.

Pour chaque site réseau, travaillez avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille généralement à New York, se déplace pour se former, allume son ordinateur et se connecte au réseau, son ordinateur reçoit une adresse IP dans l’une des quatre plages allouées à New York, par exemple, 172.29.80.103.

## <a name="trusted-ip-address"></a>Adresse IP fiable

Les adresses IP fiables sont les adresses IP externes Internet du réseau d’entreprise. Ils déterminent si le point de terminaison de l’utilisateur se trouve dans le réseau d’entreprise avant de vérifier la correspondance d’un site spécifique.

Si l’adresse IP externe de l’utilisateur correspond à une adresse IP qui se trouve dans la liste d’adresses IP fiables, la fonctionnalité voix cloud vérifie pour déterminer le sous-réseau interne où se trouve le point de terminaison de l’utilisateur. Une correspondance peut être faite par rapport aux adresses IP IPv4 ou IPv6 et dépend du format du paquet IP envoyé aux paramètres réseau. (Si une adresse IP publique possède le protocole IPv4 et IPv6, vous devez ajouter les deux en tant qu’adresses IP de confiance.)

Si l’adresse IP externe de l’utilisateur ne correspond pas à une adresse IP qui se trouve dans la liste d’adresses IP fiables, le point de terminaison est classé comme étant à un emplacement inconnu.

> [!Important]
> Les recherches de paramètres de configuration réseau ne sont pas pris en charge avec les déploiements de services proxy cloud qui modifient les adresses IP sources Teams clients.
