---
title: Ajouter l’adresse IP NAT du serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
description: L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est nécessaire parce que vous avez sélectionné l’adresse IP externe de ce pool est traduit par option NAT dans la page Sélectionner les fonctionnalités de cet Assistant de bord.
ms.openlocfilehash: 7074a4f138b04be5f368891af2547bcbff700b3f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886310"
---
# <a name="add-edge-server-nat-ip"></a>Ajouter l’adresse IP NAT du serveur Edge

L’adresse IP publique est l’adresse IP utilisée par la traduction d’adresses réseau (NAT). L’adresse IP doit être publiquement routable. Cela est nécessaire parce que vous avez sélectionné l’option de **l’adresse IP externe de ce pool Edge est traduit par NAT** dans la page **Sélectionner les fonctionnalités** de cet Assistant.

> [!NOTE]
> Traduction d’adresses réseau (NAT) permet de clients ou serveurs sur un réseau privé (par exemple, le 192.168.0.0 plage) pour communiquer avec des systèmes sur des réseaux à distance sur les réseaux Internet publics. NAT fonctionne en utilisant une seule adresse IP publique sur une interface externe et associer des adresses IP internes avec une adresse IP publique. Mappage NAT mappe une adresse interne à l’adresse IP publique externe. Le système distant voit uniquement l’adresse publique de la source. Le système distant répond à la source et la source fait référence à la réponse doit être renvoyée à la carte de NAT pour déterminer l’adresse IP interne.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou par la suite. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, reportez-vous à la rubrique [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) de la documentation de déploiement des serveurs Edge.


