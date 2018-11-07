---
title: Ce qui est déconseillé de Skype pour Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/10/2018
ms.audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités ont été supprimées de Skype pour Business Server 2019.'
ms.openlocfilehash: 66366c2272db8d6f605fde6dc066f730543883b6
ms.sourcegitcommit: 27cd6d540485d5a1557a6131612894ca2f3516ee
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2018
ms.locfileid: "26025079"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Ce qui est déconseillé de Skype pour Business Server 2019 

Découvrez les fonctionnalités qui sont déconseillées dans Skype pour Business Server 2019. Pour plus d’informations sur les nouvelles fonctionnalités dans Skype pour Business Server 2019, voir [Nouveautés de Skype pour Business Server 2019](whats-new.md).

Certaines fonctionnalités de retrait emphasised sont incluses dans Skype pour Business Server 2019 pour la compatibilité avec les versions antérieures du produit. 

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Fonctionnalités déconseillées dans Skype pour Business Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Passerelles XMPP pour Skype pour Business Server

Skype pour Business Server 2015 et ses prédécesseurs autorisés vous permet de configurer un proxy XMPP et de présence Protocol (XMPP) sur le serveur de périphérie et une passerelle XMPP sur le pool frontal ou serveur frontal. Cette fonctionnalité n’est plus disponible dans Skype pour Business Server 2019.


### <a name="persistent-chat-for-skype-for-business-server"></a>Conversation permanente pour Skype pour Business Server

Serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs dans votre organisation participer à des conversations de salle de conversation persistant. Conversation permanente ne peuvent pas être déployée avec Skype pour Business Server 2019. Ce rôle de serveur est supprimé du Générateur de topologie, ainsi que du code. 

La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).   

### <a name="sql-mirroring-for-skype-for-business-server"></a>Mise en miroir de SQL pour Skype pour Business Server

La mise en miroir SQL ne peut pas être déployé avec Skype pour Business Server 2019. Autres options pour fournir une haute disponibilité et récupération d’urgence sont toujours supportées et vous devez choisir parmi les. Voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) pour passer en revue les options.

### <a name="in-place-upgrades"></a>Mises à niveau sur place 

Mises à niveau sur place étaient disponibles dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. Côte à côte mise à niveau et la coexistence, consultez [Migration vers Skype pour Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.

###  <a name="mobility-service-mcx"></a>Service de mobilité (Mcx)

Prise en charge du Service Mobility utilisé par les clients hérités mobiles n’est plus disponible dans Skype pour Business Server 2019. Il a été précédemment annoncé dans Skype pour Business Server 2015.

Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités Mcx doivent mettre à niveau vers un client actuel.

Pour plus d’informations, voir [planifier la mobilité Skype pour Business Server](../SfbServer/plan-your-deployment/mobility.md) et [comparaison des fonctionnalités de client Mobile pour Skype pour les entreprises](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Outils

Les outils suivants ne sera pas disponibles pour la version initiale de Skype pour Business Server 2019 :

- Skype pour calculateur de planification de la capacité de serveur Business
- Skype pour Business Server Outils de débogage
- Skype pour les outils du Kit de ressources Business Server (certains outils seront supprimés)
    - Call Parkometer
    - Console utilisateur de recherche
    - Numéro non attribué Migration annonce

Les outils suivants ne sont pas pris en charge avec Skype pour Business Server 2019 :

- Méthodologie de la qualité des appels (mais pas appeler de tableau de bord qualité)
- Carte de performance Microsoft appel qualité méthodologie, v1.5
- Skype for Business Server 2015 Planning Tool
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Voir aussi

[Quelles sont les nouveautés dans Skype pour Business Server 2019](whats-new.md)

[Migration de la fédération XMPP](migration/migrating-xmpp-federation.md)