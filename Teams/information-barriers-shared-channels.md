---
title: Obstacles à l’information et canaux partagés (préversion)
description: Cet article explique comment les obstacles à l’information dans Microsoft Teams prennent en charge les canaux partagés
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: information-barriers
ms.openlocfilehash: 6ee178252c00ec4c73dfaa036f17377cef401d30
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922835"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Obstacles à l’information et canaux partagés (préversion)

[Les canaux partagés](shared-channels.md) dans Microsoft Teams créent des espaces de collaboration dans lesquels vous pouvez inviter des personnes qui ne sont pas dans l’équipe. [Les barrières à l’information Microsoft Purview](/microsoft-365/compliance/information-barriers) sont des stratégies qui peuvent être implémentées pour restreindre et empêcher les utilisateurs et les groupes de communiquer entre eux au sein et à l’extérieur de votre organisation.

Les canaux partagés sont activés par défaut dans Teams. Vous pouvez choisir si les gens peuvent créer des canaux partagés, s'ils peuvent les partager avec des personnes extérieures à votre organisation, et s'ils peuvent participer à des canaux partagés externes en créant une politique de canal. Lorsque des stratégies d’obstacle à l’information sont configurées dans votre organisation, des vérifications sont effectuées lors de la configuration des canaux partagés pour vérifier qu’aucun des membres de canal existants et les nouveaux utilisateurs ajoutés au canal partagé ne violent les conditions de stratégie d’obstacles à l’information.

Utilisez le tableau suivant pour comprendre comment les stratégies d’obstacles à l’information peuvent avoir un impact sur les communications et entraîner des comportements spécifiques lors de la configuration de canaux partagés :

|**Scénario**|**Comportement des obstacles à l’information**|
|:-----------|:--------------------------------|
| **Partager un canal avec un utilisateur de votre organisation** | Si l’utilisateur n’est pas autorisé à communiquer avec les membres de canal partagés en fonction d’une stratégie d’obstacles à l’information, l’utilisateur n’est pas affiché dans la recherche utilisateur et le canal n’est pas partagé avec l’équipe. <br><br> Si l’utilisateur ne peut pas être ajouté conformément à une stratégie d’obstacles à l’information, le message suivant s’affiche : *Nous n’avons trouvé aucune correspondance. Demandez à votre administrateur informatique d’étendre l’étendue de votre recherche.* |
| **Partager un canal dans votre organisation avec une autre équipe que vous possédez** | Si l’autre équipe a des utilisateurs qui ne sont pas autorisés à communiquer avec les membres de canal partagés selon une stratégie d’obstacles à l’information, le canal n’est pas partagé avec l’équipe. <br><br> Si les communications ne sont pas autorisées conformément à une stratégie d’obstacles à l’information, le message suivant s’affiche : *le canal ne peut pas être partagé avec cette équipe. Choisissez une autre équipe ou contactez votre administrateur pour plus d’informations.* |
| **Partager un canal dans votre organisation avec une autre équipe que vous ne possédez pas** | Si le propriétaire de l’équipe ou les utilisateurs de l’autre équipe ne sont pas autorisés à communiquer avec les membres du canal partagé conformément à une stratégie d’obstacles à l’information, le canal ne peut pas être partagé avec l’équipe. <br><br> Si les communications ne sont pas autorisées conformément à une stratégie d’obstacles à l’information, le message suivant s’affiche : *le canal ne peut pas être partagé avec cette équipe. Choisissez une autre équipe ou contactez votre administrateur pour plus d’informations.* |
| **Ajouter un nouvel utilisateur à l’équipe lorsque l’équipe a partagé des canaux avec d’autres équipes** | Si le nouvel utilisateur n’est pas autorisé à communiquer avec les membres de l’équipe de canal partagé conformément à une stratégie d’obstacles à l’information, il ne peut pas être ajouté à l’équipe. Lorsque vous ajoutez un utilisateur à une équipe avec six canaux partagés ou plus, l’utilisateur est immédiatement ajouté au canal et le partage est pris en charge. Le partage pour l’équipe et les canaux précédemment partagés peut être arrêté si le nouvel utilisateur n’est pas conforme à une stratégie d’obstacles à l’information.<br><br> Si l’utilisateur ne peut pas être ajouté conformément à une stratégie d’obstacles à l’information, le message suivant s’affiche : *Impossible d’ajouter un utilisateur en raison d’une stratégie d’obstacles à l’information.* |
| **Partager un canal avec une équipe externe** | Les stratégies d’obstacles à l’information sur les locataires internes et externes ne limitent pas les communications entre les utilisateurs des différents locataires. Les canaux partagés peuvent être partagés avec des utilisateurs externes. |
