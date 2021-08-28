---
title: What’s deprecated from Skype Entreprise Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités ont été supprimées de Skype Entreprise Server 2019.'
ms.openlocfilehash: cdc7b54f815c324707ee657d8365aa842f28293d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595028"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>What’s deprecated from Skype Entreprise Server 2019

Découvrez les fonctionnalités qui sont Skype Entreprise Server 2019. Pour plus d’informations sur les nouvelles fonctionnalités Skype Entreprise Server 2019, voir [Nouveautés Skype Entreprise Server 2019.](whats-new.md)

Certaines fonctionnalités de mise en avant sont incluses dans Skype Entreprise Server 2019 pour des raisons de compatibilité avec les versions précédentes du produit.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Fonctionnalités Skype Entreprise Server 2019 

Les fonctionnalités suivantes ont été Skype Entreprise Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Passerelles XMPP pour Skype Entreprise Server

Skype Entreprise Server 2015 et ses prédécesseurs vous ont permis de configurer un proxy XMPP (Extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Cette fonctionnalité n’est plus disponible Skype Entreprise Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Conversation permanente pour Skype Entreprise Server

Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation persistantes au fil du temps. La conversation permanente ne peut pas être déployée avec Skype Entreprise Server 2019. Ce rôle serveur est supprimé du Générateur de topologie et du code. 

La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL Mise en miroir pour Skype Entreprise Server

SQL La mise en miroir ne peut pas être déployée avec Skype Entreprise Server 2019. D’autres options de haute disponibilité et de récupération d’urgence sont toujours pris en charge et vous devez choisir parmi celles-ci. Pour [consulter les options, voir Planifier la](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) haute disponibilité et la récupération d’urgence Skype Entreprise Server les options.

### <a name="in-place-upgrades"></a>Mises à niveau sur place 

Les mises à niveau sur place étaient disponibles Skype Entreprise Server 2015, mais ne sont plus Skype Entreprise Server 2019. La mise à niveau et la coexistence côte à côte sont pris en charge. Pour plus d’informations, [voir Migration to Skype Entreprise Server 2019](migration/migration-to-skype-for-business-server-2019.md).

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant Mcx devront mettre à niveau vers un client actuel.

Pour plus d’informations, voir [la comparaison des](../SfbServer/plan-your-deployment/mobility.md) fonctionnalités de client Skype Entreprise Server mobile et de la mobilité pour [Skype Entreprise](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).

## <a name="tools"></a>Outils

Les outils suivants ne seront pas disponibles à la version initiale de Skype Entreprise Server 2019 :

- Calculateur de planification de la capacité Skype Entreprise Server
- Skype Entreprise Server Outils de débogage
- Skype Entreprise Server Outils du Kit de ressources (certains outils seront supprimés)
    - Call Parkometer
    - Console utilisateur de recherche
    - Migration d’annonces de numéro non signé

Les outils suivants ne sont pas pris en charge Skype Entreprise Server 2019 :

- Méthodologie de qualité des appels (mais pas tableau de bord de qualité des appels)
- Carte de performance de méthodologie de qualité des appels Microsoft, v1.5
- outil de planification Skype Entreprise Server 2015
- Skype Entreprise Server 2015 Stress and Performance Tool

### <a name="see-also"></a>Voir aussi

[Nouveautés de Skype Entreprise Server 2019](whats-new.md)

[Migration de la fédération XMPP](migration/migrating-xmpp-federation.md)
