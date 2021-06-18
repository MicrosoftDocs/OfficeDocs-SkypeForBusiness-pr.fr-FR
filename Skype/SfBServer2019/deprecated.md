---
title: What’s deprecated from Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Résumé : Ces fonctionnalités ont été supprimées de Skype Entreprise Server 2019.'
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808724"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a>What’s deprecated from Skype for Business Server 2019

Découvrez les fonctionnalités qui sont dépréciées dans Skype Entreprise Server 2019. Pour plus d’informations sur les nouvelles fonctionnalités de Skype Entreprise Server 2019, voir [What’s in Skype for Business Server 2019](whats-new.md).

Certaines fonctionnalités de mise en avant sont incluses dans Skype Entreprise Server 2019 pour des raisons de compatibilité avec les versions précédentes du produit.

## <a name="features-deprecated-in-skype-for-business-server-2019"></a>Fonctionnalités dépréciées dans Skype Entreprise Server 2019 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a>Passerelles XMPP pour Skype Entreprise Server

Skype Entreprise Server 2015 et ses prédécesseurs vous ont permis de configurer un proxy XMPP (Extensible Messaging and Presence Protocol) sur le serveur Edge et une passerelle XMPP sur le serveur frontal ou le pool frontal. Cette fonctionnalité n’est plus disponible dans Skype Entreprise Server 2019.

### <a name="persistent-chat-for-skype-for-business-server"></a>Conversation permanente pour Skype Entreprise Server

Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation persistantes au fil du temps. La conversation permanente ne peut pas être déployée avec Skype Entreprise Server 2019. Ce rôle serveur est supprimé du Générateur de topologie, ainsi que du code. 

La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)

### <a name="sql-mirroring-for-skype-for-business-server"></a>SQL miroir pour Skype Entreprise Server

SQL la mise en miroir ne peut pas être déployée avec Skype Entreprise Server 2019. D’autres options de haute disponibilité et de récupération d’urgence sont toujours pris en charge et vous devez choisir parmi celles-ci. Pour consulter les options, voir [Planifier la haute disponibilité et la récupération d’urgence](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) dans Skype Entreprise Server.

### <a name="in-place-upgrades"></a>Mises à niveau sur place 

Les mises à niveau sur place étaient disponibles dans Skype Entreprise Server 2015, mais ne sont plus pris en charge dans Skype Entreprise Server 2019. La mise à niveau et la coexistence côte à côte sont pris en charge. Pour plus d’informations, voir Migration vers Skype Entreprise [Server 2019.](migration/migration-to-skype-for-business-server-2019.md)

### <a name="mobility-service-mcx"></a>Mobility Service (Mcx)

La prise en charge du service de mobilité utilisée par les clients mobiles hérités n’est plus disponible dans Skype Entreprise Server 2019. Cela a été annoncé précédemment dans Skype Entreprise Server 2015.

Tous les clients mobiles Skype Entreprise actuels utilisent déjà l’API web de communications unifiées (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant Mcx devront mettre à niveau vers un client actuel.

Pour plus d’informations, consultez la comparaison des fonctionnalités de client mobile et de plan de mobilité pour Skype [Entreprise](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) [Server.](../SfbServer/plan-your-deployment/mobility.md)

## <a name="tools"></a>Outils

Les outils suivants ne pourront pas être utilisés lors de la version initiale de Skype Entreprise Server 2019 :

- Calculateur de planification de la capacité Skype Entreprise Server
- Outils de débogage Skype Entreprise Server
- Outils du Kit de ressources Skype Entreprise Server (certains outils seront supprimés)
    - Call Parkometer
    - Console utilisateur de recherche
    - Migration d’annonces de numéro non signé

Les outils suivants ne sont pas pris en charge avec Skype Entreprise Server 2019 :

- Méthodologie de qualité des appels (mais pas tableau de bord de qualité des appels)
- Carte de performance de méthodologie de qualité des appels Microsoft, v1.5
- Outil de planification Skype Entreprise Server 2015
- Outil Stress and Performance de Skype Entreprise Server 2015

### <a name="see-also"></a>Voir aussi

[Nouveautés de Skype Entreprise Server 2019](whats-new.md)

[Migration de la fédération XMPP](migration/migrating-xmpp-federation.md)
