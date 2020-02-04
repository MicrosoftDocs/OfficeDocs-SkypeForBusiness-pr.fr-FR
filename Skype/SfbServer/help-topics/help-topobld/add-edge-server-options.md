---
title: Ajouter des options de serveur Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Sélectionnez chaque fonctionnalité à activer pour le pool de serveurs Edge. Par défaut, le pool de serveurs Edge prend en charge les utilisateurs distants dans votre organisation qui se connectent à l’extérieur du pare-feu en utilisant un réseau privé virtuel (VPN). Pour les fonctionnalités de pool de serveurs Edge, vous disposez également des options suivantes :'
ms.openlocfilehash: 7a2d844b90341a91a6532f743531b3237864830a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685217"
---
# <a name="add-edge-server-options"></a>Ajouter des options de serveur Edge

Sélectionnez chaque fonctionnalité à activer pour le pool de serveurs Edge. Par défaut, le pool de serveurs Edge prend en charge les utilisateurs distants dans votre organisation qui se connectent à l’extérieur du pare-feu en utilisant un réseau privé virtuel (VPN). Pour les fonctionnalités de pool de serveurs Edge, vous disposez également des options suivantes :

- Utilisez un nom de domaine complet (FQDN) et une adresse IP uniques pour tous les services Edge, dont le service Edge d’accès, le service Edge de conférence web et le service Edge A/V. Si vous ne sélectionnez pas l’option pour utiliser un nom de domaine complet et une adresse IP uniques, vous devrez spécifier un nom de domaine complet et une adresse IP distincts pour chacun de ces trois services Edge lors e la procédure de déploiement. Pour plus d’informations sur les services Edge, reportez-vous à la rubrique [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) de la documentation de planification.

    > [!NOTE]
    > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port par défaut recommandés : port 444 pour le service Edge d’accès, port 8057 pour le service Edge de conférence web et port 443 pour le service Edge A/V). Si vous sélectionnez cette option, vous pouvez éviter des problèmes de connectivité et simplifier la configuration, car vous pouvez taper un nom de domaine complet qui sera utilisé pour les trois services.

- Prise en charge des fédérations : sélectionnez cette option si vous voulez prendre en charge la communication entre les utilisateurs internes et les utilisateurs de domaines approuvés à l’extérieur de votre organisation, y compris tous les utilisateurs d’un fournisseur de service de messagerie instantanée publique pris en charge. Si vous sélectionnez cette option, vous devrez configurer la prise en charge de domaines fédérés spécifiques et les fournisseurs de service de connectivité PIC (Public IM Connectivity) à prendre en charge. Pour plus d’informations sur la configuration de la prise en charge des fédérations et d’autres types d’accès utilisateur externe, reportez-vous à la rubrique [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) de la documentation de déploiement des serveurs Edge.

    > [!NOTE]
    > Un seul pool frontal ou serveur Edge Standard dans votre organisation peut être publié de manière externe pour une fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs publics de messagerie instantanée, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

- Activer la fédération : sélectionnez cette option si vous voulez prendre en charge la communication entre les utilisateurs internes et les partenaires XMPP approuvés.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou par la suite. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, reportez-vous à la rubrique [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) de la documentation de déploiement des serveurs Edge.


