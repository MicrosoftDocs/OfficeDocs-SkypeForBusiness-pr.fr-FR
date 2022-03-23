---
title: Barrières de l’information et canaux partagés (prévisualisation)
description: Cet article explique comment les barrières de l’information au Microsoft Teams en charge les canaux partagés
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
ms.openlocfilehash: c65da8b9b04296a7377f29aead811e1efcfb4048
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712133"
---
# <a name="information-barriers-and-shared-channels-preview"></a>Barrières de l’information et canaux partagés (prévisualisation)

[Les canaux partagés](shared-channels.md) Microsoft Teams créent des espaces de collaboration dans lequel vous pouvez inviter des personnes qui ne font pas équipe. [Les barrières de l’information](/microsoft-365/compliance/information-barriers) sont des stratégies qui peuvent être implémentées pour restreindre et empêcher les utilisateurs et les groupes de communiquer entre eux, au sein et à l’extérieur de votre organisation.

Les canaux partagés sont activés par défaut dans Teams. Vous pouvez choisir si les personnes peuvent créer des canaux partagés, si elles peuvent les partager avec des personnes extérieures à votre organisation, et si elles peuvent participer à des canaux partagés externes en créant une stratégie de canal. Lorsque des stratégies de barrière de l’information sont configurées dans votre organisation, des vérifications sont effectuées lors de la configuration de canaux partagés pour vérifier qu’aucun des membres existants du canal et les nouveaux utilisateurs ajoutés au canal partagé ne respectent les conditions de la stratégie.

Utilisez le tableau suivant pour comprendre comment les stratégies de barrière des informations peuvent avoir un impact sur les communications et entraîner des comportements spécifiques lors de la configuration de canaux partagés :

|**Scénario**|**Comportement des barrières de l’information**|
|:-----------|:--------------------------------|
| **Partager un canal avec un utilisateur de votre organisation** | Si l’utilisateur n’est pas autorisé à communiquer avec les membres d’un canal partagé par une stratégie de barrière de l’information, l’utilisateur n’est pas affiché dans la recherche de l’utilisateur et le canal n’est pas partagé avec l’équipe. <br><br> Si l’utilisateur ne peut pas être ajouté par une stratégie de barrière de l’information, vous verrez le message suivant : Nous *n’avons trouvé aucune correspondance. Adressez-vous à votre administrateur informatique pour en savoir plus sur l’étendue de votre recherche.* |
| **Partager un canal de votre organisation avec une autre équipe dont vous êtes propriétaire** | Si l’autre équipe a des utilisateurs qui ne sont pas autorisés à communiquer avec les membres d’un canal partagé par une stratégie de barrière de l’information, le canal n’est pas partagé avec l’équipe. <br><br> Si les communications ne sont pas autorisées par une stratégie de barrière de l’information, le message suivant s’agit : Le canal ne peut pas être partagé *avec cette équipe. Sélectionnez une autre équipe ou contactez votre administrateur pour plus d’informations.* |
| **Partager un canal dans votre organisation avec une autre équipe qui ne vous appartient pas** | Si le propriétaire de l’équipe ou des utilisateurs de l’autre équipe ne sont pas autorisés à communiquer avec les membres d’un canal partagé selon une politique de barrière de l’information, le canal ne peut pas être partagé avec l’équipe. <br><br> Si les communications ne sont pas autorisées par une stratégie de barrière de l’information, le message suivant s’agit : Le canal ne peut pas être partagé *avec cette équipe. Sélectionnez une autre équipe ou contactez votre administrateur pour plus d’informations.* |
| **Ajouter un nouvel utilisateur à l’équipe lorsque l’équipe a partagé des canaux avec d’autres équipes** | Si le nouvel utilisateur n’est pas autorisé à communiquer avec les membres de l’équipe du canal partagé par une stratégie de barrière de l’information, l’utilisateur ne peut pas être ajouté à l’équipe. Lorsque vous ajoutez un utilisateur à une équipe avec six canaux partagés ou plus, l’utilisateur est ajouté immédiatement au canal et le partage est pris en charge. Le partage pour l’équipe et les canaux précédemment partagés peut être arrêté si le nouvel utilisateur est trouvé non conforme à une stratégie de protection des informations.<br><br> Si l’utilisateur ne peut pas être ajouté par une stratégie de barrière de l’information, vous verrez le message suivant : Impossible d’ajouter un utilisateur en raison d’une stratégie de barrière *de l’information.* |
| **Partager un canal avec une équipe externe** | Les stratégies de barrière de l’information sur les clients internes et externes ne limitent pas les communications entre les utilisateurs des différents clients. Les canaux partagés peuvent être partagés avec des utilisateurs externes. |
