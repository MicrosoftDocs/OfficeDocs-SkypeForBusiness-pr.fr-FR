---
title: Considérations sur la migration de Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lisez cette rubrique pour en savoir plus sur le déploiement de Skype Room System dans un environnement qui dispose de plusieurs versions de Skype Entreprise Server et de Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805784"
---
# <a name="skype-room-system-migration-considerations"></a>Considérations sur la migration de Skype Room System
 
Lisez cette rubrique pour en savoir plus sur le déploiement de Skype Room System dans un environnement qui dispose de plusieurs versions de Skype Entreprise Server et de Lync Server.
  
## <a name="migration-considerations"></a>Considérations relatives à la migration

Cette section fournit des conseils si vous déployez Skype Room System dans un environnement multi-pool qui inclut différentes versions de Skype Entreprise Server ou de Lync Server. 
  
Le composant réplicateur d’utilisateurs (UR) dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données principale Lync Server SQL Server données. Seule l’URL dans Lync Server 2013 connaît les objets Skype Room System. L’UR dans les versions précédentes de Lync Server et d’Office Communications Server ne détecte pas les attributs Active Directory qui désignent les objets LRS et n’en était donc pas informé. 
  
Si un compte Skype Room System tente de se connecter à Lync et effectue une découverte automatique basée sur l’enregistrement SRV ou la recherche d’enregistrement DNS A, et si ces comptes pointent vers une version antérieure de Lync Server ou d’Office Communications Server, LRS reçoit une réponse 404 In trouvé du pool hérité. Le pool hérité ne pourra pas rediriger Skype Room System vers son pool d’accueil Lync Server 2013. 
  
Vous pouvez résoudre ce problème avec les options suivantes : 
  
- Pointez votre enregistrement SRV de découverte automatique (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.
    
- Si la première option n’est pas possible, vous devez configurer manuellement LRS et fournir l’adresse du pool Lync Server 2013 en la configurant directement dans l’application console Skype Room System. 
    
- Si Skype Room System est déployé en dehors du réseau d’entreprise et qu’un serveur Edge Lync a été déployé et configuré pour pointer vers un pool ou un directeur hérité, un site serveur Edge secondaire est requis, qui pointe vers le pool Lync Server 2013. Reportez-vous à la documentation de déploiement du serveur Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interopérabilité de Skype Room System avec un pool Lync Server 2010

Lors de la migration, si un utilisateur qui est homed sur un pool Lync Server 2010 planifiera une réunion et invite le compte Skype Room System, le client Skype Room System aura des fonctionnalités limitées lors de la participation à la réunion. 
  
Lorsque le client Skype Room System rejoint une conférence téléphonique programmée organisée par un utilisateur sur Lync Server 2010, Skype Room System présente les limitations de réunion suivantes : 
  
- Skype Room System ne peut pas afficher la galerie de vidéos multi-vues.
    
- Si le client Skype Room System est le présentateur, il ne peut pas appliquer de verrouillage vidéo aux participants.
    
- Skype Room System ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence Lync Server 2013 l’autorise, pour les raisons suivantes : 
    
  - Lync Server 2010 ne prend pas en charge la résolution 1080p.
    
  - Skype Room System est toujours limité par la stratégie de conférence de l’organisateur pour la résolution vidéo. Par conséquent, même si le pool Lync 2010 prend en charge la résolution 720p, Skype Room System ne sera pas en mesure de tirer parti de la résolution 720p tant que la stratégie de l’organisateur ne la prend pas en charge. 
    
- Les clients Lync 2013 détectent la présence LRS dans la salle de réunion et se mutent automatiquement pour éviter l’écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas dans les réunions hébergées sur Lync Server 2010.
    
- Il existe des limites sur les performances de partage de bureau pour les réunions hébergées sur Lync Server 2010.
    
- Les utilisateurs ne pourront pas participer à des réunions privées (restreintes) hébergées sur Lync 2010 avec Skype Room System.
    

