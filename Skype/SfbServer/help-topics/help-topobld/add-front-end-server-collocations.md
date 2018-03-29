---
title: Ajouter les Collocations du serveur frontal
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Pour un déploiement Enterprise Edition, A / V Conferencing service se trouve sur le pool frontal. Vous pouvez également colocaliser sur le pool frontal, le serveur de médiation, ou vous pouvez le déployer comme un serveur autonome. A / V Conferencing service se trouve toujours si la conférence est activée.
ms.openlocfilehash: c68ed9e05252d72739f2912f109951d0be723699
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-server-collocations"></a>Ajouter les Collocations du serveur frontal
 
Pour un déploiement Enterprise Edition, A / V Conferencing service se trouve sur le pool frontal. Vous pouvez également colocaliser sur le pool frontal, le serveur de médiation, ou vous pouvez le déployer comme un serveur autonome. A / V Conferencing service se trouve toujours si la conférence est activée.
  
> [!NOTE]
> Un A / V Conferencing service est nécessaire si la **conférence** a été sélectionné dans la page **Sélectionner les fonctionnalités** . Un pool Enterprise Edition Front-End utilise un colocalisé A / V Conferencing service. Si la conférence n’a pas été sélectionné, la Collocate A / V Conferencing service ne sera pas disponible.
  
Vous pouvez colocaliser du rôle de serveur de médiation sur un Standard Edition serveur frontal ou d’un pool d’entreprise Edition Front-End. Si vous déployez des connexions de SIP Direct à une passerelle téléphonique commuté qualifié network (PSTN) qui prend en charge le contournement de média et de l’équilibrage de la charge système de nom de domaine (DNS), un pool de serveur de médiation autonome n’est pas nécessaire. Un pool de serveur de médiation autonome n’est pas nécessaire car les passerelles qualifiés sont en mesure de DNS d’équilibrage de charge à un pool de serveurs de médiation et qu’ils peuvent recevoir du trafic à partir de n’importe quel serveur de médiation dans un pool. Nous vous recommandons également de colocaliser sur un pool frontal, le serveur de médiation lorsque vous avez déployé l’IP-PBX ou se connectez à un Internet serveur fournisseur de téléphonie Session contrôleur périphérie (SBC), tant qu’une des conditions suivantes sont remplie :
  
- L’IP-PBX ou SBC est configuré pour recevoir le trafic provenant de n’importe quel serveur de médiation dans le pool et peut router le trafic uniformément à tous les serveurs de médiation dans le pool.
    
- L’IP-PBX ou SBC est configuré pour recevoir le trafic provenant de n’importe quel serveur de médiation dans le pool et peut router le trafic uniformément à tous les serveurs de médiation dans le pool.
    
Vous pouvez utiliser Microsoft Lync Server 2013, outil de planification pour évaluer si le pool frontal où vous souhaitez colocaliser le serveur de médiation peut gérer la charge. Si votre environnement ne répond pas à ces exigences, vous devez déployer un pool de serveur de médiation autonome.
  
En général, colocalisation de serveur de médiation n’est pas recommandée si votre organisation a des exigences d’évolutivité et de disponibilité. Pour plus d’informations sur la COLLOCATION ces rôles de serveur dans un pool frontal dans un déploiement Enterprise Edition, consultez [définir et configurer un Pool fin avant](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) dans la documentation de déploiement. Pour plus d’informations sur les fonctionnalités de conférences de V et de composants, consultez [planification de conférence](http://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) dans la documentation de planification. Pour plus d’informations sur les fonctionnalités de Voix Entreprise et les composants, y compris le serveur de médiation, voir [planification de Voix Entreprise dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) dans la documentation de planification.
  

