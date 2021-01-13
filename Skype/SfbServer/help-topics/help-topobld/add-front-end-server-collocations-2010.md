---
title: Ajouter des colocalisations du serveur frontal 2010
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Pour un déploiement Enterprise Edition, vous pouvez colocaliser le service de conférence A/V ou le serveur de médiation, voire les deux sur le pool frontal, ou vous pouvez les déployer chacun comme serveur autonome. Pour le déploiement d’un serveur Standard Edition, le service de conférence A/V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: 1cd253c9415027eb36affe11dcd58832d6c07e8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824104"
---
# <a name="add-front-end-server-collocations-2010"></a>Ajouter des colocalisations du serveur frontal 2010

Pour un déploiement Enterprise Edition, vous pouvez colocaliser le service de conférence A/V ou le serveur de médiation, voire les deux sur le pool frontal, ou vous pouvez les déployer chacun comme serveur autonome. Pour le déploiement d’un serveur Standard Edition, le service de conférence A/V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence A/V est nécessaire si **Conférence** a été sélectionné sur la page **Sélectionner les fonctionnalités**. Un pool frontal Enterprise Edition peut utiliser un service de conférence A/V colocalisé ou un pool de conférence A/V autonome. Si Conférence n'était pas sélectionné, l’option Colocaliser le service de conférence A/V ne sera pas disponible.

Vous pouvez céquequer le rôle serveur de médiation sur un serveur frontal Standard Edition ou un pool frontal Enterprise Edition. Si vous déployez des connexions SIP directes sur une passerelle de réseau téléphonique commuté (PSTN) qualifiée qui prend en charge le contournement de média et l’équilibrage de charge DNS (Domain Name System), un pool de serveurs de médiation autonome n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool. Nous vous recommandons également de céqueifier le serveur de médiation sur un pool frontal lorsque vous avez déployé IP-PBXs ou de vous connecter au contrôleur SBC (Session Border Controller) d’un fournisseur de serveur de téléphonie Internet, à condition que l’une des conditions suivantes soit remplie :

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification Microsoft Lync Server 2013 pour évaluer si le pool frontal sur lequel vous souhaitez céqueriser le serveur de médiation peut gérer la charge. Si votre environnement ne remplit pas les conditions requises, vous devez alors déployer un pool de serveurs de médiation autonome.

En règle générale, la cocisation du serveur de conférence A/V ou du serveur de médiation n’est pas recommandée si votre organisation a des exigences de haute disponibilité et d’évolutivité. Pour plus d’informations sur la cinglisation de ces rôles serveur dans un pool frontal dans un déploiement Enterprise Edition, voir Définir et configurer un [pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) frontal dans la documentation de déploiement. Pour plus d’informations sur la fonction de conférence A/V et ses composants, voir [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de déploiement. Pour plus d’informations sur Voix Entreprise et les composants, y compris le serveur de médiation, voir [Plan for Voix Entreprise in Skype for Business Server 2015 in](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) the Planning documentation.


