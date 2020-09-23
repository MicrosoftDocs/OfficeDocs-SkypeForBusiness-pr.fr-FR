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
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou le déployer comme un serveur autonome. Le service de conférence A/V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: 015570d42482b0e4f34e6679bab27aa2c40f2f88
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216505"
---
# <a name="add-front-end-server-collocations"></a>Ajouter des colocalisations du serveur frontal

Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou le déployer comme un serveur autonome. Le service de conférence A/V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence A/V est nécessaire si **Conférence** a été sélectionné dans la page **Sélectionner les fonctionnalités**. Un pool frontal Enterprise Edition utilise un service de conférence A/V colocalisé. Si Conférence n’était pas sélectionné, l’option Colocaliser le service de conférence A/V ne sera pas disponible.

Vous pouvez colocaliser le rôle de serveur de médiation sur un serveur frontal Standard Edition ou un pool frontal Enterprise Edition. Si vous déployez des connexions SIP directes vers une passerelle de réseau téléphonique commuté (PSTN) qui prend en charge la déviation du trafic multimédia et l’équilibrage de la charge DNS (Domain Name System), un pool de serveurs de médiation autonomes n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool. Nous vous recommandons également de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé des PBX IP ou que vous vous connectez à un contrôleur de frontière de session (SBC) d’un fournisseur de serveur de téléphonie Internet, à condition que l’une des conditions suivantes soit remplie :

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification de Microsoft Lync Server 2013 pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne satisfait pas les conditions requises, vous devez déployer un pool de serveurs de médiation autonome.

En règle générale, la colocalisation du serveur de médiation n’est pas recommandée si votre organisation a des exigences élevées en matière de disponibilité et d’extensibilité. Pour plus d’informations sur la colocalisation de ces rôles serveur dans un pool frontal dans un déploiement Enterprise Edition, voir [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur la fonction de conférence A/V et ses composants, voir [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de déploiement. Pour plus d’informations sur les composants et les fonctionnalités voix entreprise, y compris sur le serveur de médiation, voir [plan for Enterprise Voice in Skype for Business server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.


