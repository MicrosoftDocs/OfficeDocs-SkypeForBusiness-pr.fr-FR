---
title: 'Lync Server 2013 : Gestion de fédération et accès externe à Skype pour Business Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous activez et configurez l’accès utilisateur externe au contrôle si pris en charge des utilisateurs externes peuvent collaborer avec Skype interne pour les utilisateurs Business Server.
ms.openlocfilehash: c48914ca6dc7faf03fea1a3877bd2e349e39e290
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197596"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestion de la fédération et accès externe aux Skype pour Business Server

Déploiement d’un serveur Edge ou pool de serveurs Edge est la première étape de la prise en charge des utilisateurs externes. Pour plus d’informations sur le déploiement des serveurs de périphérie, voir [Déployer un serveur Edge dans Skype pour Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Après l’installation et configuration de votre déploiement interne de Skype pour Business Server, les utilisateurs internes de votre organisation peuvent collaborer avec d’autres utilisateurs internes qui disposent de comptes SIP dans vos Services de domaine Active Directory (AD DS). Collaboration peut inclure l’envoi et réception de messages instantanés et mettre à jour de statut de présence et participer aux conférences (également appelé « réunions »). Vous activez et configurez l’accès utilisateur externe au contrôle si pris en charge des utilisateurs externes peuvent collaborer avec Skype interne pour les utilisateurs Business Server. Les utilisateurs externes peuvent inclure des utilisateurs distants de votre déploiement, les utilisateurs fédérés (y compris les utilisateurs pris en charge de public (IM) service fournisseurs de messagerie instantanée) et des participants anonymes à des conférences.

Si votre déploiement inclus l’installation d’un Skype pour Business Server Edge Server ou un pool de serveurs Edge, l’étendue des types de communication possibles est considérablement développé avec un nombre d’options pour l’accès des utilisateurs externes, la communication avec les membres d’autres fédérés SIP SIP et les domaines fédérés de fournisseurs. Après avoir configuré le serveur Edge ou le pool de serveurs Edge, vous activez les types d’accès des utilisateurs externes que vous souhaitez fournir et configurez les stratégies de contrôle pour l’accès externe. Dans Skype pour Business Server, vous activez et configurez l’accès des utilisateurs externes et les stratégies à l’aide de la Skype pour le panneau de configuration serveur Business, le [Skype pour Business Server Management Shell](../management-shell.md), ou les deux, selon la configuration requise. 



> [!IMPORTANT]  
> Lorsque vous concevez votre configuration et les stratégies d’accès des utilisateurs externes, vous devez comprendre la priorité des stratégies et la façon dont les stratégies sont appliquées. Skype pour les paramètres de stratégie Business Server qui sont appliqués à un niveau de stratégie permettre remplacer les paramètres qui sont appliqués au niveau de stratégie d’une autre. Skype pour la priorité de la stratégie Business Server est : stratégie utilisateur (influencent la plupart) substitue à une stratégie de Site, puis une stratégie de Site substitue à une stratégie globale (influence moins). Cela signifie que le paramètre de stratégie est proche de l’objet qui affecte la stratégie, la plus grande influence sur l’objet.


Par défaut, aucune stratégie sont configurées pour prendre en charge l’accès des utilisateurs externes, y compris l’accès des utilisateurs distants, fédérés l’accès des utilisateurs, même si vous avez déjà activé la prise en charge de l’accès utilisateur externe pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies, spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Cela inclut les stratégies d’accès externes suivants :

  - **Stratégie globale**   la stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activées dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous configurez la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateur externe. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et utilisateur remplacer la stratégie globale. Si vous supprimez la stratégie globale, vous ne le supprimez pas. Au lieu de cela, vous le réinitialiser les paramètres par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge pour l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez attribuer une stratégie utilisateur à un utilisateur de remplacer le paramètre de stratégie de site.

  - **Stratégie utilisateur**   vous pouvez créer et configurer une ou plusieurs stratégies d’utilisateur pour limiter la prise en charge pour l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration dans la stratégie de site et de remplacements de la stratégie utilisateur global, mais uniquement pour les utilisateurs auxquels la stratégie utilisateur est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale et stratégie de site, vous spécifiez une stratégie utilisateur désactive l’accès des utilisateurs distants et ensuite affecter cette stratégie utilisateur à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant de prendre effet.

Pour déterminer quels paramètres de configuration et les stratégies, vous devez créer ou modifier, consultez les points de décision suivant :

**Vous souhaitez autoriser les utilisateurs internes et externes de votre domaine être en mesure de collaborer à l’aide de la messagerie instantanée, conférence Web et Audio/vidéo**

Configurez les paramètres comme indiqué dans les rubriques de [la configuration des stratégies pour contrôler l’accès des utilisateurs distants](external-access-policies/configure-policies-to-control-remote-user-access.md)et [Activer ou désactiver la fédération et la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Vous souhaitez autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par les utilisateurs de votre déploiement**

Configurez les paramètres comme indiqué dans la rubrique [affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) et les [stratégies de conférence créer](../conferencing/create-policies.md).

**Vous souhaitez autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [configurer les stratégies de contrôle des accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), [Activer ou désactiver la fédération et la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)et [Manage SIP federated domaines pour votre organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Si vous avez activé la communication avec les domaines fédérés SIP, voulez-vous activer la découverte automatique de la fédération SIP ?**

Configurez les paramètres comme indiqué dans la rubrique [Activer ou désactiver la découverte des partenaires de fédération](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous permettre l’envoi d’une notification d’exclusion pour les contacts fédérés notifiant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme indiqué dans la rubrique [Activer ou désactiver l’envoi d’une notification d’exclusion d’archivage aux partenaires fédérés](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Vous souhaitez autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui permettent la communication avec les fournisseurs publics ?**

Configurer les paramètres comme indiqués dans les rubriques [d’accéder à la configuration des stratégies pour le contrôle des utilisateurs publics](external-access-policies/configure-policies-to-control-public-user-access.md), [Activer ou désactiver la fédération et la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)et [créer ou modifier public de fournisseurs fédérés SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**Vous souhaitez autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft Office 365 et Skype pour Business Online ?**

Configurez les paramètres comme indiqué dans les rubriques [Activer ou désactiver la fédération et la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) et [créer ou modifier hébergé de fournisseurs fédérés SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Votre déploiement est configuré dans un domaine fractionné (également appelé un hybride), où certains utilisateurs ont leur serveur central dans un déploiement sur site et autres utilisateurs sont configurées avec un serveur central dans un environnement en ligne ?**

Configurer les paramètres comme indiqués dans les rubriques de [la configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), [Activer ou désactiver la fédération et la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)et [créer ou modifier hébergé de fournisseurs fédérés SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Vous pouvez configurer les paramètres d’accès utilisateur externe, y compris toutes les stratégies que vous souhaitez utiliser pour contrôler l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et autres paramètres que vous configurez sont en vigueur uniquement lorsque vous avez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation lors de l’accès des utilisateurs externes est désactivé ou si aucune des stratégies d’accès utilisateur externe ne sont configurés pour prendre en charge.

Votre déploiement edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes sont authentifiés par l’ID de conférence et une clé d’accès est envoyée au participant anonyme lors de la création des conférence et inviter des participants) et des contrôles accès en fonction de la configuration de la prise en charge de votre serveur edge. Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et configurer les paramètres qui définissent la façon dont les utilisateurs internes et externes à votre déploiement communiquent entre eux. Les stratégies et paramètres incluent la stratégie globale par défaut pour l’accès des utilisateurs externes, en plus des stratégies de site et d’utilisateur que vous pouvez créer et configurer pour activer un ou plusieurs types d’accès des utilisateurs externes pour les sites ou utilisateurs spécifiques.

