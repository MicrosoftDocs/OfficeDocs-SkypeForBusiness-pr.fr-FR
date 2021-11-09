---
title: Ajouter des options de serveur Edge
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Sélectionnez chaque fonctionnalité que vous souhaitez activer pour le pool de serveurs Edge. Par défaut, le pool edge prend en charge les utilisateurs distants de votre organisation qui se connectent depuis l’extérieur du pare-feu à l’aide d’un réseau privé virtuel (VPN). Vous disposez également des options suivantes de fonctionnalités des pools de serveurs Edge :'
ms.openlocfilehash: e9da9c45335cf023dc7da99656fe8a266164efc9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862621"
---
# <a name="add-edge-server-options"></a>Ajouter des options de serveur Edge

Sélectionnez chaque fonctionnalité que vous souhaitez activer pour le pool de serveurs Edge. Par défaut, le pool edge prend en charge les utilisateurs distants de votre organisation qui se connectent depuis l’extérieur du pare-feu à l’aide d’un réseau privé virtuel (VPN). Vous disposez également des options suivantes de fonctionnalités des pools de serveurs Edge :

- Utilisation d'un nom de domaine complet (FQDN) et adresse IP uniques pour tous les services Edge, notamment le service Edge d'accès, le service Edge de conférence Web et le service Edge A/V. Si vous ne sélectionnez pas l'option d'utiliser un nom de domaine complet et une adresse IP uniques, il vous faudra spécifier un nom de domaine complet et une adresse IP séparés pour chacun de ces trois services Edge dans le processus de déploiement. Pour plus d'informations sur les services Edge, voir [Composants requis pour l'accès des utilisateurs externes](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access) dans la documentation de planification.

    > [!NOTE]
    > Si vous sélectionnez cette option, vous devez spécifier un numéro de port différent pour chacun des services Edge (paramètres de port par défaut recommandés : 444 pour le service Edge d’accès, 8057 pour le service Edge de conférence Web et 443 pour le service Edge A/V). La sélection de cette option peut éviter des problèmes de connectivité, et peut simplifier la configuration car vous pouvez taper un nom de domaine complet qui sera utilisé pour les trois services.

- Prise en charge des fédérations. Sélectionnez cette option si vous souhaitez prendre en charge la communication entre les utilisateurs internes et les utilisateurs de domaines approuvés à l'extérieur de votre organisation, notamment les utilisateurs d'un fournisseur d'un service de messagerie instantanée public pris en charge. Si vous sélectionnez cette option, il vous faudra configurer la prise en charge de domaines fédérés spécifiques et de fournisseurs d'un service de messagerie instantanée public. Pour plus d'informations sur la configuration de la prise en charge des fédérations et d'autres types d'accès utilisateur externe, voir [Configuration de la prise en charge de l’accès des utilisateurs externe](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access) dans la documentation de déploiement des serveurs Edge.

    > [!NOTE]
    > Un seul pool frontal ou serveur Edge Standard dans votre organisation peut être publié de manière externe pour une fédération. Tout accès par des utilisateurs fédérés, y compris les utilisateurs publics de messagerie instantanée, passe par le même pool de serveurs Edge ou serveur Edge unique. Par exemple, si votre déploiement comprend un pool de serveurs Edge ou un serveur Edge unique déployé à New York, et un autre déployé à Londres, et que vous activez la prise en charge de fédération sur le pool de serveurs Edge ou serveur Edge unique de New York, le trafic de signalisation pour les utilisateurs fédérés passera par le pool de serveurs Edge ou serveur Edge unique de New York. Ceci s’applique aussi aux communications avec les utilisateurs de Londres, même si un utilisateur interne de Londres qui appelle un utilisateur fédéré de Londres utilise le pool de serveurs ou le serveur Edge de Londres pour le trafic A/V.

- Activez la fédération. Sélectionnez cette option si vous voulez prendre en charge la communication entre les utilisateurs internes et les partenaires XMPP approuvés.

Vous pouvez ajouter la prise en charge de l’accès des utilisateurs externes lors du déploiement initial de la topologie ou le faire ultérieurement. Pour plus d’informations sur l’ajout de serveurs Edge à une topologie existante, voir [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) dans la documentation de déploiement des serveurs Edge.