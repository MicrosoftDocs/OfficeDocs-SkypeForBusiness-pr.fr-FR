---
title: Ajouter l’adresse IP NAT du serveur Edge
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est obligatoire car vous avez sélectionné l’option L’adresse IP externe de ce pool est traduite par NAT dans la page Sélectionner les fonctionnalités de cet Assistant.
ms.openlocfilehash: 6e35d384fbc416ee27583adfbde47f5348df8b5d68d419f0da723e3b5b79ed7d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295441"
---
# <a name="add-edge-server-nat-ip"></a>Ajouter l’adresse IP NAT du serveur Edge

L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est obligatoire car vous avez sélectionné l’option **L’adresse IP externe de ce pool est traduite par NAT** dans la page **Sélectionner les fonctionnalités** de cet Assistant.

> [!NOTE]
> La traduction d’adresses réseau permet aux clients et aux serveurs d’un réseau privé (par exemple, la plage 192.168.0.0) de communiquer avec les systèmes sur des réseaux privés à travers des réseaux Internet publics. La traduction d’adresses réseau fonctionne en utilisant une adresse IP publique unique sur une interface externe et en associant les adresses IP internes avec l’adresse IP publique unique. La traduction d’adresses réseau mappe une adresse interne à l’adresse IP publique externe. Le système distant ne voit que l’adresse publique de la source. Le système distant répond à la source, et la source se rapporte au mappage NAT pour déterminer à quelle adresse IP interne envoyer la réponse.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou le faire ultérieurement. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, voir [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) dans la documentation de déploiement des serveurs Edge.