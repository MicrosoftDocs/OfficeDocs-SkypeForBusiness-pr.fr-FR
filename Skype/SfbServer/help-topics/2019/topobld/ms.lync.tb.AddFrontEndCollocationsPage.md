---
title: Ajouter des colocalisations du serveur frontal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou le déployer comme un serveur autonome. Le service de conférence A/V est toujours colocalisé si la conférence est activée.
ms.openlocfilehash: e8f3a5ac2e5b6cca244d4a396bf69f554ad4ff77
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832638"
---
# <a name="add-front-end-server-collocations"></a>Ajouter des colocalisations du serveur frontal

Dans le cas d’un déploiement Enterprise Edition, le service de conférence A/V est colocalisé sur le pool frontal. Vous pouvez également colocaliser le serveur de médiation sur le pool frontal, ou le déployer comme un serveur autonome. Le service de conférence A/V est toujours colocalisé si la conférence est activée.

> [!NOTE]
> Un service de conférence A/V est nécessaire si **Conférence** a été sélectionné dans la page **Sélectionner les fonctionnalités**. Un pool frontal Enterprise Edition utilise un service de conférence A/V colocalisé. Si Conférence n’était pas sélectionné, l’option Colocaliser le service de conférence A/V ne sera pas disponible.

Vous pouvez céquequer le rôle serveur de médiation sur Édition Standard serveur frontal ou Êdition Entreprise pool frontal. Si vous déployez des connexions SIP directes sur une passerelle de réseau téléphonique commuté (PSTN) qualifiée qui prend en charge le contournement de média et l’équilibrage de charge DNS (Domain Name System), un pool de serveurs de médiation autonome n’est pas nécessaire. Si vous déployez des connexions Direct SIP sur une passerelle multimédia PSTN qualifiée prenant en charge le contournement du média et l‘équilibrage de charge DNS, un pool de serveurs de médiation autonome n‘est pas nécessaire, car les passerelles qualifiées sont capables d‘effectuer l‘équilibrage de charge DNS sur un pool de serveurs de médiation et recevoir du trafic provenant d‘un des serveurs du pool. Nous vous recommandons également de céqueifier le serveur de médiation sur un pool frontal lorsque vous avez déployé IP-PBXs ou de vous connecter au contrôleur SBC (Session Border Controller) d’un fournisseur de serveur de téléphonie Internet, à condition que l’une des conditions suivantes soit remplie :

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

- Le système IP-PBX ou le contrôleur SBC est configuré pour recevoir du trafic de n’importe quel serveur de médiation du pool et peut acheminer les données de ce trafic de manière uniforme sur tous les serveurs de médiation du pool.

Vous pouvez utiliser l’outil de planification pour évaluer si le pool frontal sur lequel vous souhaitez céqueriser le serveur de médiation peut gérer la charge. Si votre environnement ne satisfait pas les conditions requises, vous devez déployer un pool de serveurs de médiation autonome.

En règle générale, la colocalisation du serveur de médiation n’est pas recommandée si votre organisation a des exigences élevées en matière de disponibilité et d’extensibilité. Pour plus d’informations sur la colocalisation de ces rôles serveur dans un pool frontal dans un déploiement Enterprise Edition, voir [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) dans la documentation de déploiement. Pour plus d’informations sur la fonction de conférence A/V et ses composants, voir [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) dans la documentation de déploiement. Pour plus d’informations Voix Entreprise fonctionnalités et composants, y compris le serveur de médiation, voir [Plan for Voix Entreprise in Skype Entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in the Planning documentation.