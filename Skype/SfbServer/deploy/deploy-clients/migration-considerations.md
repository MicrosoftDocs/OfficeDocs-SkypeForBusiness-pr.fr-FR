---
title: Remarques sur la migration de Skype Room System
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Lisez cette rubrique pour en savoir plus sur le déploiement de système d’espace Skype dans un environnement comportant plusieurs versions de Skype pour Business Server et Lync Server.
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a>Remarques sur la migration de Skype Room System
 
Lisez cette rubrique pour en savoir plus sur le déploiement de système d’espace Skype dans un environnement comportant plusieurs versions de Skype pour Business Server et Lync Server.
  
## <a name="migration-considerations"></a>Remarques sur la migration

Cette section fournit des conseils si vous déployez un système de salle de Skype dans un environnement multi-pool qui inclut des versions différentes de Skype pour Business Server, Lync Server ou Office Communications Server 2007 R2. 
  
Le composant réplicateur d’utilisateurs dans Lync Server obtient des objets utilisateur d’Active Directory et les place dans la base de données SQL Server du serveur principal Lync Server. Le réplicateur d’utilisateurs uniquement dans Lync Server 2013 est conscient des objets système de salle de Skype. Le réplicateur d’utilisateurs dans les versions précédentes de Lync Server et Office Communications Server ne détecte pas les attributs Active Directory qui désignent des objets LRS, et n’en avait, par conséquent, pas connaissance. 
  
Si un compte système local de Skype essaie de se connecter à Lync et effectue la découverte automatique basée sur l’enregistrement SRV ou rechercher enregistrement A DNS, et si ces comptes pointent vers une version antérieure de Lync Server ou Office Communications Server, LRS recevront une réponse de 404 introuvable à partir de  le pool d’ancienne génération. Le pool hérité ne pourront pas rediriger le système de salle Skype pour son pool de domicile de Lync Server 2013. 
  
Vous pouvez résoudre ce problème avec les options suivantes : 
  
- Pointez votre découverte automatique d’enregistrement SRV (_sipinternaltls._tcp.contoso.com) vers le pool Lync Server 2013.
    
- Si la première option n’est pas possible, vous devez manuellement configurer LRS et fournir l’adresse de pool Lync Server 2013 en le configurant directement dans l’application de la console système de salle de Skype. 
    
- Si le système de salle de Skype est déployé en dehors du réseau d’entreprise et de Lync Edge Server a été déployé et configuré pour pointer vers un pool hérité ou d’un directeur, un site de serveur de transport Edge secondaire est requis, qui pointe vers le pool Lync Server 2013. Reportez-vous à la documentation de déploiement des serveurs Edge pour plus d’informations sur le déploiement d’un serveur Edge secondaire. 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Salle de Skype l’interopérabilité du système avec un Pool de Lync Server 2010

Lors de la migration, si un utilisateur qui est hébergé sur un pool Lync Server 2010 permet de planifier une réunion et invite le compte système local de Skype, le client Skype espace système sera ont des fonctionnalités limitées lors de la participation à la réunion. 
  
Lorsque le client Skype espace système joint un appel de conférence planifié qui a été organisé par un utilisateur hébergé dans Lync Server 2010, Skype espace système a les limitations suivantes en réunion : 
  
- Système de chambre de Skype ne peut pas afficher la Galerie vidéo multivue.
    
- Si le client du système de salle de Skype est le présentateur, il ne peut pas appliquer verrouillage vidéo sur les participants.
    
- Système de salle Skype ne peut pas afficher la résolution vidéo 1080p (entrante ou sortante), même si la stratégie de conférence Lync Server 2013, autorise les raisons suivantes : 
    
  - Lync Server 2010 ne prend pas en charge la résolution de 1080p.
    
  - Système de chambre de Skype est toujours limitée par la stratégie de conférence de l’organisateur pour la résolution vidéo. Par conséquent, même si le pool Lync 2010 prend en charge la résolution 720p, Skype espace système pas pourra bénéficier de la résolution 720p tant qu’il ne gère pas la stratégie de l’organisateur. 
    
- Les clients Lync 2013 détectent la présence de LRS dans la salle de réunion, et désactivent leur micro afin d’éviter tout écho dans la salle de réunion physique. Cette fonctionnalité ne fonctionne pas pour des réunions hébergées sur Lync Server 2010.
    
- Les performances du partage de bureau sont limitées pour les réunions hébergées sur Lync Server 2010.
    
- Les utilisateurs ne pourront pas joindre (limitées) les conférences privées qui sont hébergés dans Lync 2010 avec système de salle de Skype.
    

