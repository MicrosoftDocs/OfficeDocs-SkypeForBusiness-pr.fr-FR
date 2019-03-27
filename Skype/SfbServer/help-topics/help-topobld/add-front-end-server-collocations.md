---
title: Ajouter des colocalisations du serveur frontal
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Pour un déploiement Enterprise Edition, A / service de conférence de V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou vous pouvez le déployer en tant que serveur autonome. A / service de conférence de V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: 98e42a36bd57d256b66e08b6a44cca1d8b492155
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884356"
---
# <a name="add-front-end-server-collocations"></a>Ajouter des colocalisations du serveur frontal

Pour un déploiement Enterprise Edition, A / service de conférence de V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou vous pouvez le déployer en tant que serveur autonome. A / service de conférence de V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence V est requis si la **conférence** a été sélectionnée dans la page **Sélectionner les fonctionnalités** . Un pool frontal Enterprise Edition utilise un colocalisé A / service de conférence V. Si la conférence n’a pas été sélectionnée, le colocaliser A / service de conférence V ne sera pas disponible.

Vous pouvez colocaliser le rôle de serveur de médiation sur un serveur Standard Edition serveur frontal ou un pool frontal Enterprise Edition. Si vous déployez des connexions SIP Direct vers une passerelle de réseau (PSTN) public commuté complet qui prend en charge le contournement de média et le nom de domaine DNS (Domain Name System) de l’équilibrage de charge, un pool de serveur de médiation autonome n’est pas nécessaire. Un pool de serveur de médiation autonome n’est pas nécessaire, car les passerelles qualifiées sont capables de charge DNS équilibrée à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de colocaliser le serveur de médiation sur un pool frontal lorsque vous avez déployé l’IP-PBX ou vous connecter à d’un serveur de fournisseur de téléphonie Internet contrôleur de Session bordure (SBC), dans la mesure où une des conditions suivantes sont remplie :

- L’IP-PBX ou SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer le trafic de manière uniforme sur tous les serveurs de médiation du pool.

- L’IP-PBX ou SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer le trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour déterminer si le pool frontal où vous voulez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne peut pas ces exigences, vous devez déployer un pool de serveur de médiation autonome.

En règle générale, la colocalisation de serveur de médiation n’est pas recommandée si votre organisation dispose de haute disponibilité et évolutivité. Pour plus d’informations sur la colocalisation de ces rôles de serveur dans un pool frontal dans un déploiement Enterprise Edition, voir [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur A / de la fonctionnalité de conférence V et des composants, consultez [planification de conférence](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités d’Enterprise Voice et des composants, y compris le serveur de médiation, voir [Plan pour Enterprise Voice sur Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.


