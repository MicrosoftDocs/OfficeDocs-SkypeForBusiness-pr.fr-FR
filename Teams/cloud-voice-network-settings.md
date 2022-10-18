---
title: Paramètres réseau pour les fonctionnalités voix Cloud
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez les paramètres réseau que vous devez configurer pour Location-Based routage pour le routage direct et les services d’urgence améliorés.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 327dbcef98e62d86f814f8e1fadc1c26673d0928
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584005"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a>Paramètres réseau pour les fonctionnalités de voix cloud dans Microsoft Teams

Découvrez les régions réseau, les sites réseau, les sous-réseaux réseau et les adresses IP approuvées. Ces termes et concepts sont utilisés dans notre documentation vocale cloud pour le [routage basé sur l’emplacement pour le routage direct](location-based-routing-plan.md) et les [appels d’urgence dynamiques](configure-dynamic-emergency-calling.md). Si vous déployez ces fonctionnalités cloud dans votre organisation, vous devez configurer les paramètres réseau à utiliser avec ces fonctionnalités dans Microsoft Teams.

Cet article vous donne une vue d’ensemble des paramètres réseau qui sont courants pour Location-Based le routage et les appels d’urgence dynamiques. En fonction de la fonctionnalité de voix cloud et de la fonctionnalité que vous déployez, vous configurez certains ou tous ces paramètres. Pour savoir comment configurer ces paramètres, consultez [Gérer la topologie de votre réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

> [!NOTE]
> Toutes les exigences spécifiques aux fonctionnalités pour les paramètres réseau sont documentées dans les rubriques de configuration de cette fonctionnalité.

## <a name="network-region"></a>Région réseau

Une région réseau contient une collection de sites réseau. Il interconnecte différentes parties d’un réseau dans plusieurs zones géographiques. Par exemple, si votre organisation possède de nombreux sites situés en Inde, vous pouvez choisir de désigner « Inde » comme région réseau. Chaque site réseau doit être associé à une région réseau.

Les mêmes régions réseau sont partagées par Location-Based routage pour le routage direct et les services d’urgence améliorés. Si vous avez déjà créé des régions réseau pour une fonctionnalité, vous n’avez pas à créer de régions réseau pour l’autre fonctionnalité.

## <a name="network-site"></a>Site réseau

Un site réseau représente un emplacement où votre organisation a un lieu physique, tel qu’un bureau, un ensemble de bâtiments ou un campus. Les sites réseau sont définis comme une collection de sous-réseaux IP. Chaque site réseau doit être associé à une région réseau.

Vous pouvez également utiliser des sites réseau pour activer et configurer les appels d’urgence.

## <a name="network-subnet"></a>Sous-réseau réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. L’emplacement d’un client est déterminé en fonction du sous-réseau réseau et du site réseau associé. Vous pouvez associer plusieurs sous-réseaux au même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau.

Les informations de sous-réseau sont utilisées pour déterminer le site réseau sur lequel se trouve un point de terminaison lorsqu’une nouvelle session est lancée. Lorsque l’emplacement de chaque partie d’une session est connu, la fonctionnalité de voix cloud peut appliquer ces informations pour déterminer comment gérer la configuration ou le routage des appels.

Pour chaque site réseau, collaborez avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Dans notre exemple, le site New York de la région Amérique du Nord peut se voir affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si Bob, qui travaille habituellement à Detroit, se rend au bureau de New York pour la formation, allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages allouées pour New York, par exemple, 172.29.80.103.

## <a name="trusted-ip-address"></a>Adresse IP approuvée

Les adresses IP approuvées sont les adresses IP externes Internet du réseau d’entreprise. Ils déterminent si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise avant de rechercher une correspondance de site spécifique.

Si l’adresse IP externe de l’utilisateur correspond à une adresse IP figurant dans la liste des adresses IP approuvées, la fonctionnalité de voix cloud vérifie pour déterminer le sous-réseau interne où se trouve le point de terminaison de l’utilisateur. Une correspondance peut être établie avec les adresses IP IPv4 ou IPv6 et dépend du format du paquet IP envoyé aux paramètres réseau. (Si une adresse IP publique a à la fois IPv4 et IPv6, vous devez ajouter les deux en tant qu’adresses IP approuvées.)

Si l’adresse IP externe de l’utilisateur ne correspond pas à une adresse IP figurant dans la liste d’adresses IP approuvées, le point de terminaison est classé comme se trouvant à un emplacement inconnu.

> [!Important]
> Les recherches de paramètres de configuration réseau ne sont pas prises en charge avec les déploiements de service proxy cloud qui modifient les adresses IP sources des clients Teams.
