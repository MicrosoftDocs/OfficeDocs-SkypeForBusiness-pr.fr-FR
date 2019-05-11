---
title: Ajouter des colocalisations du serveur frontal 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Pour un déploiement Enterprise Edition, vous pouvez colocaliser soit A / V Conferencing service, le serveur de médiation ou les deux sur le pool frontal, ou vous pouvant déployer chaque en tant que serveurs autonomes. Pour un déploiement Standard Edition server, A / service de conférence de V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: 1c2aab2f32a81724b8da649956e10e9a9ee5ae12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903809"
---
# <a name="add-front-end-server-collocations-2010"></a>Ajouter des colocalisations du serveur frontal 2010

Pour un déploiement Enterprise Edition, vous pouvez colocaliser soit A / V Conferencing service, le serveur de médiation ou les deux sur le pool frontal, ou vous pouvant déployer chaque en tant que serveurs autonomes. Pour un déploiement Standard Edition server, A / service de conférence de V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence V est requis si la **conférence** a été sélectionnée dans la page **Sélectionner les fonctionnalités** . Un pool frontal Enterprise Edition peut utiliser un colocalisé A / service de conférence V ou un Stand-Alone A / pool de conférence V. Si la conférence n’a pas été sélectionnée, le colocaliser A / service de conférence V ne sera pas disponible.

Vous pouvez colocaliser le rôle de serveur de médiation sur un serveur Standard Edition serveur frontal ou un pool frontal Enterprise Edition. Si vous déployez des connexions SIP Direct vers une passerelle de réseau (PSTN) public commuté complet qui prend en charge le contournement de média et le nom de domaine DNS (Domain Name System) de l’équilibrage de charge, un pool de serveur de médiation autonome n’est pas nécessaire. Un pool de serveur de médiation autonome n’est pas nécessaire, car les passerelles qualifiées sont capables de charge DNS équilibrée à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé l’IP-PBX ou vous connecter à d’un serveur de fournisseur de téléphonie Internet contrôleur de Session bordure (SBC), dans la mesure où une des conditions suivantes sont remplie :

- L’IP-PBX ou SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer le trafic de manière uniforme sur tous les serveurs de médiation du pool.

- L’IP-PBX ou SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer le trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour déterminer si le pool frontal où vous voulez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne peut pas ces exigences, vous devez déployer un pool de serveur de médiation autonome.

En générale, colocalisation des / V Conferencing Server ou le serveur de médiation est déconseillé si votre organisation dispose de haute disponibilité et évolutivité requirementsFor plus d’informations sur la colocalisation de ces rôles de serveur dans un pool frontal Enterprise Edition dans une déploiement, voir [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur A / de la fonctionnalité de conférence V et des composants, consultez [planification de conférence](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités d’Enterprise Voice et des composants, y compris le serveur de médiation, voir [Plan pour Enterprise Voice sur Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.


