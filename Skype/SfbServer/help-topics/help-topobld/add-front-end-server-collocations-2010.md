---
title: Ajouter des colocalisations du serveur frontal 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Pour un déploiement Enterprise Edition, vous pouvez colocaliser le service de conférence A/V ou le serveur de médiation, voire les deux sur le pool frontal, ou vous pouvez les déployer chacun comme serveur autonome. Pour le déploiement d’un serveur Standard Edition, le service de conférence A/V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: 4abf3d4a762ed14d95b7e9f1a4964b50c77a2884
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744245"
---
# <a name="add-front-end-server-collocations-2010"></a>Ajouter des colocalisations du serveur frontal 2010

Pour un déploiement Enterprise Edition, vous pouvez colocaliser le service de conférence A/V ou le serveur de médiation, voire les deux sur le pool frontal, ou vous pouvez les déployer chacun comme serveur autonome. Pour le déploiement d’un serveur Standard Edition, le service de conférence A/V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence A/V est nécessaire si **Conférence** a été sélectionné sur la page **Sélectionner les fonctionnalités**. Un pool frontal Enterprise Edition peut utiliser un service de conférence A/V colocalisé ou un pool de conférence A/V autonome. Si Conférence n'était pas sélectionné, l’option Colocaliser le service de conférence A/V ne sera pas disponible.

Vous pouvez céquequer le rôle serveur de médiation sur Édition Standard serveur frontal ou Êdition Entreprise pool frontal. Si vous déployez des connexions SIP directes sur une passerelle de réseau téléphonique commuté (PSTN) qualifiée qui prend en charge le contournement de média et l’équilibrage de charge DNS (Domain Name System), un pool de serveurs de médiation autonome n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool. Nous vous recommandons également de céqueifier le serveur de médiation sur un pool frontal lorsque vous avez déployé IP-PBXs ou de vous connecter au contrôleur SBC (Session Border Controller) d’un fournisseur de serveur de téléphonie Internet, à condition que l’une des conditions suivantes soit remplie :

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification Microsoft Lync Server 2013 pour évaluer si le pool frontal sur lequel vous souhaitez céqueriser le serveur de médiation peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

En règle générale, la cocisation du serveur de conférence A/V ou du serveur de médiation n’est pas recommandée si votre organisation a des exigences de haute disponibilité et d’évolutivité. Pour plus d’informations sur la cinglisation de ces rôles serveur dans un pool frontal dans un déploiement Êdition Entreprise, voir Définir et configurer un [pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) frontal dans la documentation de déploiement. Pour plus d’informations sur la fonction de conférence A/V et ses composants, voir [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) dans la documentation de déploiement. Pour plus d’informations sur Voix Entreprise et les composants, y compris le serveur de médiation, voir [Plan for Voix Entreprise in Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.