---
title: 'Lync Server 2013: gestion de la Fédération et accès externe à Skype entreprise Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous pouvez activer et configurer l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs de Skype entreprise Server internes.
ms.openlocfilehash: 555fa5ca08a707f09c9e33d8b98294b7bb584046
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280102"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestion de la Fédération et de l’accès externe à Skype entreprise Server

Le déploiement d’un serveur de périphérie ou d’un pool de périphérie est la première étape de la prise en charge des utilisateurs externes. Pour plus d’informations sur le déploiement de serveurs Edge, voir [déployer Edge Server dans Skype entreprise Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Après l’installation et la configuration de votre déploiement interne de Skype entreprise Server, les utilisateurs internes au sein de votre organisation peuvent collaborer avec d’autres utilisateurs internes disposant de comptes SIP dans les services de domaine Active Directory (AD DS). La collaboration peut inclure la possibilité d’envoyer et de recevoir des messages instantanés et de mettre à jour le statut de présence et participer à des conférences (également appelées «réunions»). Vous pouvez activer et configurer l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs de Skype entreprise Server internes. Les utilisateurs externes peuvent inclure des utilisateurs distants de votre déploiement, des utilisateurs fédérés (y compris les utilisateurs pris en charge de fournisseurs de services de messagerie instantanée publique) et des participants anonymes aux conférences.

Si votre déploiement incluait l’installation d’un serveur Edge Skype entreprise Server ou d’un pool Edge, l’étendue des types de communication possibles est largement améliorée grâce à un certain nombre d’options pour l’accès des utilisateurs externes, la communication avec les membres d’un autre domaine fédéré domaines et fournisseurs fédérés SIP. Après avoir configuré le serveur de périphérie ou le pool de bords, vous activez les types d’accès des utilisateurs externes que vous souhaitez fournir et configurez les stratégies pour contrôler l’accès externe. Dans Skype entreprise Server, vous activez et configurez l’accès et les stratégies des utilisateurs externes à l’aide du panneau de configuration Skype entreprise Server, de [Skype entreprise Server Management Shell](../management-shell.md), ou les deux, en fonction de la configuration requise pour la tâche. 



> [!IMPORTANT]  
> Lorsque vous concevez votre configuration et vos stratégies pour l’accès des utilisateurs externes, vous devez comprendre la priorité des stratégies et la façon dont elles sont appliquées. Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de Skype entreprise Server est le suivant: la stratégie de l’utilisateur (la plus influence) remplace une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.


Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, y compris l’accès des utilisateurs distants, l’accès des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes pour votre organisation. Pour contrôler l’utilisation de l’accès des utilisateurs externes, vous devez configurer une ou plusieurs stratégies en spécifiant le type d’accès des utilisateurs externes pris en charge pour chaque stratégie. Cela inclut les stratégies d’accès externe suivantes:

  - **Politique globale la**   stratégie globale est créée lors du déploiement de votre serveur Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous pouvez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateurs externes. La politique globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous rétablissez la valeur par défaut.

  - **Stratégie de site**   vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès des utilisateurs distants pour un site spécifique. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur à un utilisateur pour remplacer le paramètre de stratégie de site.

  - **Stratégie**   de l’utilisateur vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration de la stratégie utilisateur remplace la stratégie globale et la stratégie de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée. Par exemple, si vous autorisez l’accès des utilisateurs distants dans la stratégie globale et la stratégie de site, vous pouvez spécifier une stratégie d’utilisateur qui désactive l’accès des utilisateurs distants, puis affecter cette stratégie à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle ne soit appliquée.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants:

**Souhaitez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, de la conférence Web et de l’audio et de la vidéo?**

Configurez les paramètres comme décrit dans les rubriques [Configuration des stratégies pour contrôler les accès des utilisateurs](external-access-policies/configure-policies-to-control-remote-user-access.md)distants, et [activez ou désactivez la connectivité de Fédération et de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Souhaitez-vous autoriser les utilisateurs anonymes à participer à des conférences hébergées par des utilisateurs dans votre déploiement?**

Configurez les paramètres comme décrit dans la rubrique [affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) et [créer des stratégies de conférence](../conferencing/create-policies.md).

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des contacts de domaine fédéré SIP?**

Configurez les paramètres comme décrit plus en détail dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), l’activation ou la désactivation de la [connectivité de Fédération et de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et [la gestion des domaines fédérés SIP pour votre organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Si vous avez activé la communication avec des domaines fédérés SIP, voulez-vous activer la découverte automatique de la Fédération SIP?**

Configurez les paramètres comme décrit dans la rubrique [activer ou désactiver la découverte des partenaires de Fédération](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de Fédération SIP, voulez-vous autoriser l’envoi d’une exclusion de responsabilité à des contacts fédérés pour les informer que vous utilisez l’archivage et que ces communications peuvent être archivées?**

Configurez les paramètres comme décrit dans la rubrique [activer ou désactiver l’envoi d’une exclusion d’autorisation d’archivage aux partenaires fédérés dans](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui autorisent la communication avec les fournisseurs publics?**

Configurez les paramètres comme décrit dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs publics](external-access-policies/configure-policies-to-control-public-user-access.md), l’activation ou la désactivation de la [connectivité de Fédération et de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et la [création ou la modification des fournisseurs fédérés SIP publics](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) .


**Souhaitez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft Office 365 et Skype entreprise Online?**

Configurez les paramètres comme décrit dans les rubriques [activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) et [création ou modification des fournisseurs fédérés SIP hébergés](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Votre déploiement est-il configuré dans un domaine fractionné (également connu sous le nom de domaine hybride) dans lequel certains utilisateurs disposent du serveur principal dans le cadre d’un déploiement local et d’autres utilisateurs sont configurés avec un serveur domestique dans un environnement en ligne?**

Configurez les paramètres comme décrit dans les rubriques [Configuration des stratégies pour contrôler l’accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), l’activation ou la désactivation de la [connectivité de Fédération et de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et la [création ou la modification des fournisseurs fédérés SIP hébergés](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies que vous souhaitez utiliser pour contrôler l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et autres paramètres que vous configurez ne s’appliquent que si l’accès utilisateur externe est activé pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation lorsque l’accès des utilisateurs externes est désactivé ou s’il n’y a pas de stratégie d’accès des utilisateurs externes pour la prise en charge.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et d’une clé d’authentification envoyée au participant anonyme lors de la création de la Conférence et d’invitations aux participants) et de contrôles. Access en fonction de la configuration de votre support Edge. Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et configurer des paramètres définissant le mode de communication des utilisateurs internes et externes à votre déploiement. Les stratégies et paramètres incluent la stratégie globale par défaut de l’accès des utilisateurs externes, en plus des stratégies de site et d’utilisateur que vous pouvez créer et configurer pour activer un ou plusieurs types d’accès utilisateur externe pour des sites ou des utilisateurs spécifiques.

