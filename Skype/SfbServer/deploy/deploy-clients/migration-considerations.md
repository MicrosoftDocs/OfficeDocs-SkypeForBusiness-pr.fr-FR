---
title: Remarques sur la migration de Skype Room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Pour en savoir plus sur le déploiement de votre système de salle Skype dans un environnement doté de plusieurs versions de Skype entreprise Server et de Lync Server, reportez-vous à cette rubrique.
ms.openlocfilehash: a4856977931d459fba3b11a65b21e49a25cc418b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768837"
---
# <a name="skype-room-system-migration-considerations"></a>Remarques sur la migration de Skype Room System
 
Pour en savoir plus sur le déploiement de votre système de salle Skype dans un environnement doté de plusieurs versions de Skype entreprise Server et de Lync Server, reportez-vous à cette rubrique.
  
## <a name="migration-considerations"></a>Remarques sur la migration

Cette section fournit des recommandations si vous déployez le système de salle Skype dans un environnement multi-pool incluant différentes versions de Skype entreprise Server ou de Lync Server. 
  
Le composant réplicateur d’utilisateurs dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données SQL Server du serveur principal Lync Server. Seul le RÉPLICATEUR d’application de bureau dans Lync Server 2013 est consciente des objets système de salle Skype. Le réplicateur d’utilisateurs dans les versions précédentes de Lync Server et Office Communications Server ne détecte pas les attributs Active Directory qui désignent des objets LRS, et n’en avait, par conséquent, pas connaissance. 
  
Si un compte système de salle Skype tente de se connecter à Lync et effectue une découverte automatique en fonction de l’enregistrement SRV ou du système de recherche DNS A et si ces comptes pointent vers une version antérieure de Lync Server ou d’Office Communications Server, LRS recevra une réponse 404 introuvable de  le pool hérité. Le pool hérité ne sera pas en mesure de rediriger le système de salle Skype vers son pool d’hébergement 2013 Lync Server. 
  
Vous pouvez résoudre ce problème avec les options suivantes : 
  
- Pointez votre découverte automatique d’enregistrement SRV (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.
    
- Si la première option n’est pas possible, vous devez configurer manuellement LRS et fournir l’adresse du pool Lync Server 2013 en le configurant directement dans l’application console du système de salle Skype. 
    
- Si le système de salle Skype est déployé à l’extérieur du réseau d’entreprise, et qu’un serveur Edge Lync a été déployé et configuré de manière à pointer vers un pool ou un réalisateur hérité, un site serveur de bord secondaire est requis, qui pointe vers le pool Lync Server 2013. Reportez-vous à la documentation de déploiement des serveurs Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interopérabilité du système de salle Skype avec un pool Lync Server 2010

Lors de la migration, si un utilisateur qui est hébergé sur un pool Lync Server 2010 planifie une réunion et invite le compte système de salle Skype, le client de système de salle Skype dispose de fonctionnalités limitées tout en participant à la réunion. 
  
Lorsque le client système de salle Skype joint un appel de conférence planifiée qui a été organisé par un utilisateur hébergé sur Lync Server 2010, le système de salle Skype dispose des limitations suivantes : 
  
- Le système de salle Skype ne peut pas afficher la Galerie de vidéos multivues.
    
- Si le client système de salle Skype est le présentateur, la vidéo ne peut pas être appliquée aux participants.
    
- Le système de salle Skype ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence 2013 de Lync Server le permet, pour les raisons suivantes : 
    
  - Lync Server 2010 ne prend pas en charge la résolution 1080p.
    
  - Le système de salle Skype est toujours limité par la stratégie de conférence de l’organisateur en fonction de la résolution vidéo. Par conséquent, même si le pool 2010 de Lync prend en charge la résolution 720p, le système de salle Skype ne sera pas en mesure de profiter de la résolution 720p tant que la stratégie de l’organisateur ne la prend pas en charge. 
    
- Les clients Lync 2013 détectent la présence de LRS dans la salle de réunion, et désactivent leur micro afin d’éviter tout écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas pour des réunions hébergées sur Lync Server 2010.
    
- Les performances du partage de bureau sont limitées pour les réunions hébergées sur Lync Server 2010.
    
- Les utilisateurs ne seront pas en mesure de rejoindre des réunions privées hébergées sur Lync 2010 avec le système de salle Skype.
    

