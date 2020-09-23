---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Vous définissez un nouveau serveur Edge ou un pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Vous pouvez choisir parmi les options suivantes :'
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216595"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Ajouter des options de serveur Edge pour Lync Server 2010

Vous définissez un nouveau serveur Edge ou un pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Vous pouvez choisir parmi les options suivantes :

- **Utiliser un seul nom de domaine complet (FQDN) et une seule adresse IP** : activez cette case à cocher afin d’utiliser une seule adresse IPv4 ou IPv6 (si vous choisissez d’utiliser IPv4 et IPv6, vous devrez définir chacun des types d’adresse IP) et le nom de domaine complet (FQDN) des interfaces Edge externes.

    > [!IMPORTANT]
    > Si vous choisissez cette option, vous n’utiliserez qu’une adresse IP, ou une adresse IPv4 et une adresse IPv6, mais vous devez attribuer des numéros de port différents à chaque interface Edge.

- **Activer la fédération pour ce pool Edge (port 5061)**  : activez cette case à cocher si vous avez l’intention de fédérer avec d’autres fournisseurs, fédérations SIP ou offres hébergées utilisant le protocole SIP.

- **L’adresse IP externe de ce pool de serveurs Edge est traduite par nat**: activez cette case à cocher si vous utilisez des adresses IP privées pour les interfaces externes de serveur Edge et que vous fournirez un périphérique de traduction d’adresses réseau (NAT) pour placer le serveur Edge ou le pool de serveurs Edge de manière logique derrière.

## <a name="see-also"></a>Voir aussi

[Planification de l’accès des utilisateurs externes](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Déploiement de l’accès des utilisateurs externes](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
