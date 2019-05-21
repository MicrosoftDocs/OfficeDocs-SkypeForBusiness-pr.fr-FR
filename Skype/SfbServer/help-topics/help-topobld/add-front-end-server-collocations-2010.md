---
title: Ajouter des colocalisations du serveur frontal 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Dans le cadre d’un déploiement Enterprise Edition, vous pouvez collocate le service de conférence A/V, le serveur de médiation, ou les deux sur le pool frontal, ou vous pouvez déployer chaque serveur en tant que serveur autonome. Pour le déploiement d’un serveur Standard Edition Server, le service de conférence A/V est toujours localisé si la Conférence est activée.
ms.openlocfilehash: 8a8191f29a30052fec837ee9136203eb5db1ee0d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275352"
---
# <a name="add-front-end-server-collocations-2010"></a>Ajouter des colocalisations du serveur frontal 2010

Dans le cadre d’un déploiement Enterprise Edition, vous pouvez collocate le service de conférence A/V, le serveur de médiation, ou les deux sur le pool frontal, ou vous pouvez déployer chaque serveur en tant que serveur autonome. Pour le déploiement d’un serveur Standard Edition Server, le service de conférence A/V est toujours localisé si la Conférence est activée.

> [!NOTE]
> Un service de conférence A/V est requis si la **Conférence** est sélectionnée dans la page **Sélectionner des fonctionnalités** . Un pool frontal Enterprise Edition pourrait utiliser un service de conférence A/V colocalisé ou un pool de conférence A/V autonome. Si l’option conférences n’a pas été sélectionnée, le service de conférence A/V Collocate ne sera pas disponible.

Vous pouvez collocate le rôle de serveur de médiation sur un pool frontal Standard Edition Server ou Enterprise Edition. Si vous déployez des connexions SIP directes vers une passerelle de réseau téléphonique commuté (PSTN) qui prend en charge la fonctionnalité de contournement du contenu multimédia et l’équilibrage de charge DNS (Domain Name System), il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonome. Il n’est pas nécessaire de disposer d’un pool de serveurs de médiation autonomes, car les passerelles qualifiées sont en mesure d’équilibrer la charge DNS vers un pool de serveurs de médiation et ils peuvent recevoir le trafic de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de collocate le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou de vous connecter à un contrôleur de bordure de session du fournisseur de téléphonie Internet (SBC), à condition que l’une des conditions suivantes soit remplie:

- Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

- Le PBX IP ou le SBC est configuré pour recevoir le trafic de n’importe quel serveur de médiation dans le pool et peut acheminer le trafic uniformément vers tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour déterminer si le pool frontal sur lequel vous souhaitez collocate le serveur de médiation peut gérer le chargement. Si votre environnement ne peut pas répondre à ces exigences, vous devez déployer un pool de serveurs de médiation autonome.

En règle générale, la coexistence du serveur de conférence A/V ou du serveur de médiation n’est pas recommandée si votre organisation dispose d’une disponibilité et d’une extensibilité requirementsFor détaillées sur collocating ces rôles de serveur dans un pool frontal d’une édition entreprise pour le déploiement, voir [définir et configurer un pool frontal](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur les composants et la fonctionnalité de conférence A/V, voir [planification des conférences](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités et les composants voix d’entreprise, notamment sur les serveurs de médiation, voir [plan pour Enterprise Voice dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.


