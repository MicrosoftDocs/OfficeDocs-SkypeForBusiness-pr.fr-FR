---
title: Paramètres réseau pour les fonctionnalités vocales de Microsoft teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Apprenez-en davantage sur les paramètres réseau que vous devez configurer pour le routage en fonction de l’emplacement pour le routage direct et pour les services d’urgence améliorés.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c24444e9beb38aa1d0888e415d9dca3a46e249a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824952"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Paramètres réseau pour les fonctionnalités vocales de Microsoft teams

En savoir plus sur les régions, les sites réseau, les sous-réseaux réseau et les adresses IP de confiance. Les présentes conditions générales et ces concepts sont utilisés dans notre documentation vocale Cloud pour [le routage direct](location-based-routing-plan.md) et les [appels d’urgence dynamiques](configure-dynamic-emergency-calling.md). Si vous déployez ces fonctionnalités de Cloud au sein de votre organisation, vous devez configurer des paramètres réseau pour utiliser ces fonctionnalités dans Microsoft Teams.

Cet article vous donne une vue d’ensemble des paramètres réseau communs au routage par emplacement et aux appels d’urgence dynamiques. En fonction de la fonctionnalité voix sur le Cloud et des fonctionnalités que vous déployez, vous configurez l’ensemble ou une partie de ces paramètres. Pour plus d’informations sur la configuration de ces paramètres, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).

> [!NOTE]
> Les exigences en matière de fonctionnalités relatives aux paramètres réseau sont décrites dans les rubriques de configuration de cette fonctionnalité.

## <a name="network-region"></a>Région du réseau

Une région réseau contient une collection de sites réseau. Il relie diverses parties d’un réseau à plusieurs zones géographiques. Par exemple, si votre organisation comporte de nombreux sites situés en Inde, vous pouvez choisir de définir « Inde » en tant que région réseau. Chaque site réseau doit être associé à une région réseau.

Les mêmes régions réseau sont partagées par le routage par emplacement pour le routage direct et les services d’urgence améliorés. Si vous avez déjà créé des régions réseau pour une fonctionnalité, vous n’avez pas besoin de créer de nouvelles régions réseau pour l’autre fonctionnalité.

## <a name="network-site"></a>Site réseau

Un site réseau correspond à un emplacement où votre organisation a une place physique, par exemple un bureau, un ensemble de bâtiments ou un campus. Les sites réseau sont définis comme une collection de sous-réseaux IP. Chaque site réseau doit être associé à une région réseau.

Vous pouvez également utiliser les sites réseau pour activer et configurer les appels d’urgence.

## <a name="network-subnet"></a>Sous-réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau du réseau et du site du réseau associé. Vous pouvez associer plusieurs sous-réseaux avec le même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau.

Les informations de sous-réseau permettent de déterminer le site réseau sur lequel se trouve un point de terminaison lors du lancement d’une nouvelle session. Lorsque l’emplacement de chaque partie d’une session est connu, la fonctionnalité voix sur le Cloud peut appliquer ces informations pour déterminer le mode de gestion de l’appel ou du routage.

Pour chaque site réseau, travaillez avec votre administrateur réseau pour déterminer les sous-réseaux IP qui sont attribués à chaque site réseau. Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille habituellement à Détroit, voyage à la nouvelle-Saint-Patrick pour la formation, tourne sur son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages qui sont allouées à New York (par exemple, 172.29.80.103.

## <a name="trusted-ip-address"></a>Adresse IP de confiance

Adresses IP approuvées correspondent aux adresses IP externes Internet du réseau d’entreprise. Ils déterminent si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise avant de rechercher une correspondance de site spécifique.

Si l’adresse IP externe de l’utilisateur correspond à une adresse IP figurant dans la liste d’adresses IP autorisées, la fonctionnalité voix sur le Cloud vérifie pour déterminer le sous-réseau interne sur lequel se trouve le point de terminaison de l’utilisateur. Une correspondance peut être établie avec des adresses IP IPv4 ou IPv6 et dépend du format des paquets IP envoyés aux paramètres du réseau. (Si une adresse IP publique comporte à la fois IPv4 et IPv6, vous devez ajouter ces deux éléments en tant qu’adresses IP approuvées.)

Si l’adresse IP de l’utilisateur ne correspond pas à une adresse IP figurant dans la liste d’adresses IP autorisées, le point de terminaison est considéré comme qui se trouve à un emplacement inconnu.
