---
title: Fonctionnalités déconseillées de Skype entreprise Server 2019
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : ces fonctionnalités ont été supprimées de Skype entreprise Server 2019.'
ms.openlocfilehash: 40a202f802ec8ac1a0f880f92ad9cf59ce68a627
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42125217"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Fonctionnalités déconseillées de Skype entreprise Server 2019

Découvrez les fonctionnalités qui sont déconseillées dans Skype entreprise Server 2019. Pour plus d’informations sur les nouvelles fonctionnalités de Skype entreprise Server 2019, consultez [la rubrique what’s in Skype for Business server 2019](whats-new.md).

Certaines fonctionnalités de mise en évidence sont incluses dans Skype entreprise Server 2019 pour la compatibilité avec les versions antérieures du produit.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Fonctionnalités déconseillées dans Skype entreprise Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Passerelles XMPP pour Skype entreprise Server

Skype entreprise Server 2015 et ses prédécesseurs vous permettaient de configurer un proxy XMPP (extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Cette fonctionnalité n’est plus disponible dans Skype entreprise Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Conversation permanente pour Skype entreprise Server

Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation qui persistent dans le temps. La conversation permanente ne peut pas être déployée avec Skype entreprise Server 2019. Ce rôle serveur est supprimé du générateur de topologies, ainsi que du code. 

Les mêmes fonctionnalités sont disponibles dans Teams. Pour plus d’informations, consultez [la rubrique prise en main de la mise à niveau de Microsoft teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Mise en miroir SQL pour Skype entreprise Server

La mise en miroir SQL ne peut pas être déployée avec Skype entreprise Server 2019. D’autres options de fourniture de haute disponibilité et de récupération d’urgence sont toujours prises en charge et vous devez choisir parmi celles-ci. Reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) pour consulter les options.

### <a name="in-place-upgrades"></a>Mises à niveau sur place 

Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019. La mise à niveau et la coexistence côte à côte sont prises en charge, reportez-vous [à migration vers Skype entreprise Server 2019](migration/migration-to-skype-for-business-server-2019.md) pour plus d’informations.

### <a name="mobility-service-mcx"></a>Service de mobilité (MCX)

La prise en charge du service de mobilité utilisée par les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Il a été précédemment annoncé dans Skype entreprise Server 2015.

Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.

Pour plus d’informations, reportez-vous à la rubrique [plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) et [mobile client Feature Comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Outils

Les outils suivants ne peuvent pas être utilisés lors de la publication initiale de Skype entreprise Server 2019 :

- Calculatrice de planification de la capacité de Skype entreprise Server
- Outils de débogage Skype entreprise Server
- Outils du kit de ressources Skype entreprise Server (certains outils seront supprimés)
    - Appeler Parkometer
    - Console utilisateur de recherche
    - Migration des annonces de numéros non attribués

Les outils suivants ne sont pas pris en charge avec Skype entreprise Server 2019 :

- Méthodologie de qualité des appels (mais pas tableau de bord de qualité des appels)
- Carte de performance de méthodologie de qualité des appels Microsoft, v 1.5
- Outil de planification de Skype entreprise Server 2015
- Outil de contrainte et de performances de Skype entreprise Server 2015

### <a name="see-also"></a>Voir aussi

[Nouveautés de Skype entreprise Server 2019](whats-new.md)

[Migration de la Fédération XMPP](migration/migrating-xmpp-federation.md)
