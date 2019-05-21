---
title: Ajouter des options de serveur Edge pour Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Vous définissez un nouveau serveur Edge ou une nouvelle grappe de périphériques et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Les options disponibles sont les suivantes:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289993"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Ajouter des options de serveur Edge pour Lync Server 2010

Vous définissez un nouveau serveur Edge ou une nouvelle grappe de périphériques et vous avez la possibilité de définir des fonctionnalités pour le nouveau serveur ou pool. Les options disponibles sont les suivantes:

- **Utiliser un nom de domaine complet et une adresse IP uniques**: activez la case à cocher pour utiliser un seul protocole IPv4 ou IPv6 (si vous choisissez d’utiliser IPv4 et IPv6, vous devez définir une de chaque adresse IP type) et un nom de domaine complet (FQDN) pour les interfaces Edge externes.

    > [!IMPORTANT]
    > Si vous choisissez cette option, vous n’utiliserez qu’une seule adresse IP, une seule IPv4 et une autre, mais vous devez attribuer des numéros de port différents à chaque interface latérale.

- **Activer la Fédération (port 5061)**: activez cette case à cocher si vous êtes fédérer avec d’autres fédérations SIP, fournisseurs ou produits hébergés utilisant le protocole SIP (Session Initiation Protocol).

- **L’adresse IP externe de ce pool Edge est traduite par tar**: activez cette case à cocher si vous utilisez des adresses IP privées pour les interfaces externes latérales et que vous fournissez un appareil de traduction d’adresses réseau (NAT) pour placer le serveur de périphérie ou le pool de périphérie de manière logique. concepts.

## <a name="see-also"></a>Voir aussi

[Planification de l’accès des utilisateurs externes](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[Déploiement de l’accès des utilisateurs externes](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
