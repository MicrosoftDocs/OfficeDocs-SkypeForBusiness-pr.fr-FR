---
title: Ce qui est déconseillé dans Skype entreprise Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé: les fonctionnalités suivantes ont été supprimées de Skype entreprise Server 2019.'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418360"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>Ce qui est déconseillé dans Skype entreprise Server 2019

Découvrez les fonctionnalités déconseillées dans Skype entreprise Server 2019. Pour plus d’informations sur les nouvelles fonctionnalités de Skype entreprise Server 2019, voir [qu’est-ce que Skype entreprise server 2019](whats-new.md).

Certaines fonctions inversées sont incluses dans Skype entreprise Server 2019 à des fins de compatibilité avec les versions antérieures du produit.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Fonctionnalités déconseillées dans Skype entreprise Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Passerelles XMPP pour Skype entreprise Server

Skype entreprise Server 2015 et ses prédécesseurs vous permettaient de configurer un proxy de messagerie électronique et de présence sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Cette fonctionnalité n’est plus disponible dans Skype entreprise Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Conversation permanente pour Skype entreprise Server

Le serveur Chat permanent est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salles de conversation qui persistent dans le temps. La conversation permanente ne peut pas être déployée avec Skype entreprise Server 2019. Ce rôle de serveur est supprimé du générateur de topologie, ainsi que du code. 

La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here).

### <a name="sql-mirroring-for-skype-for-business-server"></a>Mise en miroir SQL pour Skype entreprise Server

La mise en miroir SQL ne peut pas être déployée avec Skype entreprise Server 2019. D’autres options de fourniture d’une haute disponibilité et de récupération d’urgence sont toujours prises en charge, et vous devez choisir entre elles. Pour plus d’informations, consultez l’offre [pour une haute disponibilité et une reprise après sinistre dans Skype entreprise Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .

### <a name="in-place-upgrades"></a>Mises à niveau sur place 

Les mises à niveau sur place étaient disponibles dans Skype entreprise Server 2015, mais ne sont plus prises en charge dans Skype entreprise Server 2019. La mise à niveau et la coexistence côte à côte sont prises en charge pour plus d’informations, reportez-vous à la rubrique [migration vers Skype entreprise Server 2019](migration/migration-to-skype-for-business-server-2019.md) .

### <a name="mobility-service-mcx"></a>Service de mobilité (MCX)

La prise en charge des services de mobilité par les anciens clients mobiles n’est plus disponible dans Skype entreprise Server 2019. Il s’est déjà annoncé dans Skype entreprise Server 2015.

Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.

Pour plus d’informations, reportez-vous à la rubrique [planification de la mobilité pour Skype entreprise Server](../SfbServer/plan-your-deployment/mobility.md) et [comparaison des fonctionnalités du client mobile pour Skype entreprise](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Utilitaires

Les outils suivants ne seront pas disponibles lors de la publication initiale de Skype entreprise Server 2019:

- Calculateur de planification de la capacité Skype Entreprise Server
- Outils de débogage de Skype entreprise Server
- Outils du kit de ressources Skype entreprise Server (certains outils seront supprimés)
    - Call Parkometer
    - Console utilisateur de recherche
    - Migration d’annonce de numéro non affectée

Les outils suivants ne sont pas pris en charge avec Skype entreprise Server 2019:

- Méthodologie de qualité d’appel (mais pas de tableau de bord de qualité d’appel)
- Carte de performance de méthodologie de qualité d’appel Microsoft, v 1.5
- Outil de planification de Skype Entreprise Server 2015
- Skype for Business Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Voir aussi

[Nouveautés de Skype entreprise Server 2019](whats-new.md)

[Migration de la fédération XMPP](migration/migrating-xmpp-federation.md)
