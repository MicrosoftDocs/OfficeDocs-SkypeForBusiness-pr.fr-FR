---
title: Ajouter des options de serveur Edge
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sélectionnez chaque fonctionnalité à activer pour le pool de serveurs Edge. Par défaut, le pool de serveurs Edge prend en charge les utilisateurs distants dans votre organisation qui se connectent à l’extérieur du pare-feu en utilisant un réseau privé virtuel (VPN). Pour les fonctionnalités de pool de serveurs Edge, vous disposez également des options suivantes :'
ms.openlocfilehash: ece46e3bfc3b399939197ac22429574a739d9761
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23256384"
---
# <a name="add-edge-server-options"></a>Ajouter des options de serveur Edge

Sélectionnez chaque fonctionnalité à activer pour le pool de serveurs Edge. Par défaut, le pool de serveurs Edge prend en charge les utilisateurs distants dans votre organisation qui se connectent à l’extérieur du pare-feu en utilisant un réseau privé virtuel (VPN). Pour les fonctionnalités de pool de serveurs Edge, vous disposez également des options suivantes :

- Utilisez un nom de domaine complet (FQDN) et une adresse IP uniques pour tous les services Edge, dont le service Edge d’accès, le service Edge de conférence web et le service Edge A/V. Si vous ne sélectionnez pas l’option pour utiliser un nom de domaine complet et une adresse IP uniques, vous devrez spécifier un nom de domaine complet et une adresse IP distincts pour chacun de ces trois services Edge lors e la procédure de déploiement. Pour plus d’informations sur les services Edge, voir [composants requis pour l’accès utilisateur externe](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) dans la documentation de planification.

    > [!NOTE]
    > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port par défaut recommandés : port 444 pour le service Edge d’accès, port 8057 pour le service Edge de conférence web et port 443 pour le service Edge A/V). Si vous sélectionnez cette option, vous pouvez éviter des problèmes de connectivité et simplifier la configuration, car vous pouvez taper un nom de domaine complet qui sera utilisé pour les trois services.

- Prise en charge pour la fédération. Sélectionnez cette option si vous souhaitez prendre en charge la communication entre les utilisateurs internes et dans les domaines approuvés en dehors de votre organisation, y compris tous les utilisateurs d’un fournisseur de prise en charge la messagerie instantanée publique (messagerie instantanée). Si vous sélectionnez cette option, vous devez configurer la prise en charge de messageries instantanées publiques connectivity que vous souhaitez prendre en charge les domaines fédérés spécifiques. Pour plus d’informations sur la configuration de la prise en charge pour la fédération et d’autres types d’accès des utilisateurs externes, voir [Configuration de la prise en charge pour l’accès utilisateur externe](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) dans la documentation de déploiement de serveur Edge.

    > [!NOTE]
    > Un seul pool frontal ou serveur Edge Standard dans votre organisation peut être publié de manière externe pour une fédération. Tout accès par des utilisateurs fédérés, y compris des utilisateurs publics de messagerie instantanée, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou sur le serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou par le serveur Edge unique de New York. Cela s’applique également aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

- Activer la fédération : sélectionnez cette option si vous voulez prendre en charge la communication entre les utilisateurs internes et les partenaires XMPP approuvés.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou par la suite. Pour plus d’informations sur l’ajout de serveurs de périphérie à une topologie existante, voir [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) dans la documentation de déploiement de serveur Edge.


