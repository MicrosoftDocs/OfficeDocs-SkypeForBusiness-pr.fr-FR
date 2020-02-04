---
title: Ajouter des colocalisations du serveur frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également collocate du serveur de médiation sur le pool frontal ou vous pouvez le déployer en tant que serveur autonome. Le service de conférence A/V est toujours localisé si la Conférence est activée.
ms.openlocfilehash: 0d246e91549f5ff27a2e3681aae4d73c064eb67c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698209"
---
# <a name="add-front-end-server-collocations"></a>Ajouter des colocalisations du serveur frontal

Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également collocate du serveur de médiation sur le pool frontal ou vous pouvez le déployer en tant que serveur autonome. Le service de conférence A/V est toujours localisé si la Conférence est activée.

> [!NOTE]
> Un service de conférence A/V est requis si la **Conférence** est sélectionnée dans la page **Sélectionner des fonctionnalités** . Un pool frontal Enterprise Edition utilise un service de conférence A/V colocalisé. Si l’option conférences n’a pas été sélectionnée, le service de conférence A/V Collocate ne sera pas disponible.

Vous pouvez collocate le rôle de serveur de médiation sur un pool frontal Standard Edition Server ou Enterprise Edition. Si vous déployez des connexions SIP directes vers une passerelle de réseau téléphonique commuté (PSTN) qui prend en charge la fonctionnalité de contournement du contenu multimédia et l’équilibrage de charge DNS (Domain Name System), il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonome. Il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonomes, car les passerelles qualifiées sont en mesure d’équilibrer la charge DNS vers un pool de serveurs de médiation et ils peuvent recevoir le trafic de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de collocate le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou de vous connecter à un contrôleur de bordure de session du fournisseur de téléphonie Internet (SBC), à condition que l’une des conditions suivantes soit remplie :

- Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

- Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si le pool frontal sur lequel vous souhaitez collocate le serveur de médiation peut gérer le chargement. Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.

En règle générale, la colocalisation du serveur de médiation n’est pas recommandée si votre organisation a des exigences de disponibilité élevée et de mise à l’échelle. Pour plus d’informations sur collocating ces rôles de serveur dans un pool frontal dans un déploiement Enterprise Edition, voir [définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur les composants et la fonctionnalité de conférence A/V, voir [planification des conférences](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités et les composants voix d’entreprise, notamment sur les serveurs de médiation, voir [plan pour Enterprise Voice dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.


