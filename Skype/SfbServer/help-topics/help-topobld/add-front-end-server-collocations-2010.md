---
title: Ajouter le Front-End Server Collocations 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Pour un déploiement Enterprise Edition, vous pouvez colocaliser l’A / V Conferencing service, le serveur de médiation ou les deux sur le pool frontal, ou vous peuvent déployer chaque en tant que serveurs autonomes. Pour un déploiement de serveurs Standard Edition, A / V Conferencing service se trouve toujours si la conférence est activée.
ms.openlocfilehash: f8a1abf168447af7f45ed8f222ef80f029aff2bc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations-2010"></a>Ajouter le Front-End Server Collocations 2010
 
Pour un déploiement Enterprise Edition, vous pouvez colocaliser l’A / V Conferencing service, le serveur de médiation ou les deux sur le pool frontal, ou vous peuvent déployer chaque en tant que serveurs autonomes. Pour un déploiement de serveurs Standard Edition, A / V Conferencing service se trouve toujours si la conférence est activée.
  
> [!NOTE]
> Un A / V Conferencing service est nécessaire si la **conférence** a été sélectionné dans la page **Sélectionner les fonctionnalités** . Un pool Enterprise Edition Front-End peut-être utiliser un colocalisé A / V Conferencing service ou un autonome / pool de conférence V. Si la conférence n’a pas été sélectionné, la Collocate A / V Conferencing service ne sera pas disponible.
  
Vous pouvez colocaliser du rôle de serveur de médiation sur un Standard Edition serveur frontal ou d’un pool d’entreprise Edition Front-End. Si vous déployez des connexions de SIP Direct à une passerelle téléphonique commuté qualifié network (PSTN) qui prend en charge le contournement de média et de l’équilibrage de la charge système de nom de domaine (DNS), un pool de serveur de médiation autonome n’est pas nécessaire. Un pool de serveur de médiation autonome n’est pas nécessaire car les passerelles qualifiés sont en mesure de DNS d’équilibrage de charge à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic à partir de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de colocaliser sur un pool frontal, le serveur de médiation lorsque vous avez déployé l’IP-PBX ou se connectez à un Internet serveur fournisseur de téléphonie Session contrôleur périphérie (SBC), tant qu’une des conditions suivantes sont remplie :
  
- L’IP-PBX ou SBC est configuré pour recevoir le trafic provenant de n’importe quel serveur de médiation dans le pool et peut router le trafic uniformément à tous les serveurs de médiation dans le pool.
    
- L’IP-PBX ou SBC est configuré pour recevoir le trafic provenant de n’importe quel serveur de médiation dans le pool et peut router le trafic uniformément à tous les serveurs de médiation dans le pool.
    
Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
Dans générale, colocalisation a / V Conferencing Server ou serveur de médiation n’est pas recommandé si votre organisation a hautes disponibilité et l’évolutivité requirementsFor plus d’informations sur COLLOCATION ces rôles de serveur dans un pool frontal dans l’édition entreprise déploiement, voir [définir et configurer un Pool fin avant](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur les fonctionnalités de conférences de V et de composants, consultez [planification de conférence](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités de Voix Entreprise et les composants, y compris le serveur de médiation, voir [planification de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.
  

