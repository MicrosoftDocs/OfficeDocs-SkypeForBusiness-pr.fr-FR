---
title: Remarques sur la migration de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lisez cette rubrique pour en savoir plus sur le déploiement du système de salle Skype dans un environnement comprenant plusieurs versions de Skype pour Business Server et Lync Server.
ms.openlocfilehash: fef5e3e0a64fd1d533a53586b470584421a165ea
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219429"
---
# <a name="skype-room-system-migration-considerations"></a>Remarques sur la migration de Skype Room System
 
Lisez cette rubrique pour en savoir plus sur le déploiement du système de salle Skype dans un environnement comprenant plusieurs versions de Skype pour Business Server et Lync Server.
  
## <a name="migration-considerations"></a>Remarques sur la migration

Cette section fournit des instructions si vous déployez Skype salle système dans un environnement multi-pool qui inclut des versions différentes de Skype pour Business Server ou Lync Server. 
  
Le composant réplicateur d’utilisateurs dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données SQL Server du serveur principal Lync Server. Le réplicateur d’utilisateurs uniquement dans Lync Server 2013 est informé des objets système de salle Skype. Le réplicateur d’utilisateurs dans les versions précédentes de Lync Server et Office Communications Server ne détecte pas les attributs Active Directory qui désignent des objets LRS, et n’en avait, par conséquent, pas connaissance. 
  
Si un compte système local de Skype essaie de se connecter à Lync et effectue la découverte automatique en fonction de l’enregistrement SRV ou rechercher enregistrement DNS A et si ces comptes pointent vers une version précédente de Lync Server ou Office Communications Server, kr reçoit une réponse 404 introuvable à partir de  le pool hérité. Le pool hérité ne pourront pas rediriger Skype salle système vers le pool d’accueil de Lync Server 2013. 
  
Vous pouvez résoudre ce problème avec les options suivantes : 
  
- Pointez votre découverte automatique d’enregistrement SRV (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.
    
- Si la première option n’est pas possible, vous devez manuellement configurer KR et fournir l’adresse de pool Lync Server 2013 en la configurant directement dans l’application de console Skype salle système. 
    
- Si le système de salle Skype est déployé en dehors du réseau d’entreprise et un serveur de périphérie Lync a été déployé et configuré pour pointer vers un pool hérité ou un directeur, un site de serveur de transport Edge secondaire est requis, qui pointe vers le pool Lync Server 2013. Reportez-vous à la documentation de déploiement des serveurs Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Interopérabilité de système de salle Skype avec un Pool Lync Server 2010

Pendant la migration, si un utilisateur hébergé sur un pool Lync Server 2010 permet de planifier une réunion et invite le compte système de salle Skype, le client du système de salle Skype système ont des fonctionnalités limitées lors de la participation à la réunion. 
  
Lorsque le client Skype salle système joint à une téléconférence planifiée qui a été organisée par un utilisateur hébergé sur Lync Server 2010, Skype salle système présente les limitations d’en réunion suivantes : 
  
- Impossible d’afficher la galerie de vidéos MULTIVUE Skype salle système.
    
- Si le client du système de salle Skype est le présentateur, il ne peuvent pas appliquer le verrouillage vidéo sur les participants.
    
- Système de salle Skype ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence Lync Server 2013 permet, pour les raisons suivantes : 
    
  - Lync Server 2010 ne prend pas en charge la résolution de 1080p.
    
  - Système de salle de Skype est toujours limité par la stratégie de l’organisateur de la conférence pour la résolution vidéo. Par conséquent, même si le pool Lync 2010 prend en charge la résolution 720 pixels, Skype salle système sera pas en mesure de tirer parti de résolution 720 pixels tant que la stratégie de l’organisateur ne prennent en charge. 
    
- Les clients Lync 2013 détectent la présence de LRS dans la salle de réunion, et désactivent leur micro afin d’éviter tout écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas pour des réunions hébergées sur Lync Server 2010.
    
- Les performances du partage de bureau sont limitées pour les réunions hébergées sur Lync Server 2010.
    
- Les utilisateurs ne pourront pas participer à des privée réunions (restricted) qui sont hébergées sur Lync 2010 avec le système de salle Skype.
    

