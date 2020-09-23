---
title: Ajouter l’adresse IP NAT du serveur Edge
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
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est obligatoire car vous avez sélectionné l’option L’adresse IP externe de ce pool est traduite par NAT dans la page Sélectionner les fonctionnalités de cet Assistant.
ms.openlocfilehash: 12749d3bcaec2478481fc1a4bc5597fb9693c5c4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216545"
---
# <a name="add-edge-server-nat-ip"></a>Ajouter l’adresse IP NAT du serveur Edge

L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est obligatoire car vous avez sélectionné l’option **L’adresse IP externe de ce pool est traduite par NAT** dans la page **Sélectionner les fonctionnalités** de cet Assistant.

> [!NOTE]
> La traduction d’adresses réseau permet aux clients et aux serveurs d’un réseau privé (par exemple, la plage 192.168.0.0) de communiquer avec les systèmes sur des réseaux privés à travers des réseaux Internet publics. La traduction d’adresses réseau fonctionne en utilisant une adresse IP publique unique sur une interface externe et en associant les adresses IP internes avec l’adresse IP publique unique. La traduction d’adresses réseau mappe une adresse interne à l’adresse IP publique externe. Le système distant ne voit que l’adresse publique de la source. Le système distant répond à la source, et la source se rapporte au mappage NAT pour déterminer à quelle adresse IP interne envoyer la réponse.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou le faire ultérieurement. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, voir [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) dans la documentation de déploiement des serveurs Edge.


