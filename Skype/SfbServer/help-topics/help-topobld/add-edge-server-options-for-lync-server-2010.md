---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Vous définissez un nouveau serveur Edge ou pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Vous pouvez choisir parmi les options suivantes :'
ms.openlocfilehash: c258f87ac3edb38ad72d536b8ccfb2f2870d5d9e09cda65b417e49ba2c87707f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320456"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Ajouter des options de serveur Edge pour Lync Server 2010

Vous définissez un nouveau serveur Edge ou pool de serveurs Edge et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Vous pouvez choisir parmi les options suivantes :

- **Utiliser un seul nom de domaine complet (FQDN) et une seule adresse IP** : activez cette case à cocher afin d’utiliser une seule adresse IPv4 ou IPv6 (si vous choisissez d’utiliser IPv4 et IPv6, vous devrez définir chacun des types d’adresse IP) et le nom de domaine complet (FQDN) des interfaces Edge externes.

    > [!IMPORTANT]
    > Si vous choisissez cette option, vous n’utiliserez qu’une adresse IP, ou une adresse IPv4 et une adresse IPv6, mais vous devez attribuer des numéros de port différents à chaque interface Edge.

- **Activer la fédération pour ce pool Edge (port 5061)**  : activez cette case à cocher si vous avez l’intention de fédérer avec d’autres fournisseurs, fédérations SIP ou offres hébergées utilisant le protocole SIP.

- L’adresse IP externe de ce **pool edge** est traduite par NAT : cochez cette case si vous utilisez des adresses IP privées pour les interfaces externes Edge et fournissez un périphérique de traduction d’adresses réseau (NAT) pour placer le serveur Edge ou le pool edge logiquement derrière.

## <a name="see-also"></a>Voir aussi

[Planification de l’accès des utilisateurs externes](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[Déploiement de l’accès des utilisateurs externes](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)