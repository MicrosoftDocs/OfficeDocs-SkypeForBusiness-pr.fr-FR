---
title: 'Lync Server 2013 : Gestion de la fédération et de l’accès externe à Skype Entreprise Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs Skype Entreprise Server internes.
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676216"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestion de la fédération et de l’accès externe aux Skype Entreprise Server

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool Edge. Pour plus d’informations sur le déploiement de serveurs Edge, consultez [Déployer le serveur Edge dans Skype Entreprise Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Après avoir installé et configuré votre déploiement interne de Skype Entreprise Server, les utilisateurs internes de votre organisation peuvent collaborer avec d’autres utilisateurs internes qui ont des comptes SIP dans votre services de domaine Active Directory (AD DS). La collaboration peut prendre la forme d’envoi et réception de messages instantanés et de mise à jour du statut de présence ainsi que la participation à des conférences (ou réunions). Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs Skype Entreprise Server internes. Les utilisateurs externes peuvent inclure des utilisateurs distants de votre déploiement, des utilisateurs fédérés (y compris les utilisateurs pris en charge des fournisseurs de services de messagerie instantanée publiques) et des participants anonymes aux conférences.

Si votre déploiement inclut un serveur Skype Entreprise Server Edge ou un pool Edge, l’étendue des types de communication possibles est considérablement étendue. Il existe de nombreuses options pour l’accès des utilisateurs externes, la communication avec les membres d’autres domaines fédérés SIP et les fournisseurs fédérés SIP. Après avoir configuré le serveur Edge ou le pool Edge, vous activez les types d’accès utilisateur externe et configurez les stratégies pour contrôler l’accès externe. Dans Skype Entreprise Server, vous activez et configurez les stratégies et l’accès des utilisateurs externes à l’aide de la Skype Entreprise Server Panneau de configuration, de [l’interpréteur de commandes Skype Entreprise Server Management Shell](../management-shell.md) ou des deux.

> [!IMPORTANT]
> Vous devez bien saisir la priorité des stratégies et la façon dont elles sont appliquées avant de concevoir votre configuration et vos stratégies pour l’accès des utilisateurs externes. Skype Entreprise Server paramètres de stratégie appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Par défaut, aucune stratégie ne prend en charge l’accès des utilisateurs externes (y compris l’accès utilisateur distant et l’accès utilisateur fédéré), même si vous avez déjà activé la prise en charge de l’accès utilisateur externe pour votre organisation. Pour contrôler l’utilisation de l’accès utilisateur externe, vous devez configurer une ou plusieurs stratégies. Dans les stratégies suivantes, vous spécifiez le type d’accès utilisateur externe pris en charge :

- **Stratégie globale** : la stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous configurez la stratégie globale pour prendre en charge un ou plusieurs types d’accès utilisateur externe. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous la réinitialisez au paramètre par défaut.

- **Stratégie de site** : vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie de site remplace la stratégie globale, mais uniquement pour le site spécifique couvert par la stratégie de site. Par défaut, une stratégie de site est appliquée à tous les utilisateurs de ce site, mais des stratégies utilisateur pour remplacer les paramètres de stratégie de site.

- **Stratégie utilisateur** : vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès utilisateur distant à des utilisateurs spécifiques. La configuration de la stratégie utilisateur remplace la stratégie globale et la stratégie de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie est affectée. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle n’entre en vigueur.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants :

**Voulez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, des conférences web et de l’audio/vidéo ?**

Configurez les paramètres comme indiqué dans les rubriques [Configurer les stratégies pour contrôler les accès des utilisateurs distants](external-access-policies/configure-policies-to-control-remote-user-access.md), et [activer ou désactiver la fédération et la connectivité de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Voulez-vous autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par des utilisateurs au sein de votre déploiement ?**

Configurez les paramètres comme indiqué dans la rubrique [Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) et [créer des stratégies de conférence](../conferencing/create-policies.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [Configurer les stratégies pour contrôler l’accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), [activer ou désactiver la fédération et la connectivité de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et [gérer les domaines fédérés SIP pour votre organisation](sip-domains/manage-sip-federated-domains-for-your-organization.md).

**Si vous avez activé la communication avec les domaines fédérés SIP, voulez-vous activer la découverte automatique de fédération SIP ?**

Configurez les paramètres comme détaillé dans la rubrique [Activer ou désactiver la découverte des partenaires de fédération](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer l’envoi d’un dédit de responsabilité aux contacts fédérés leur indiquant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme détaillé dans la rubrique [Activer ou désactiver l’envoi d’une exclusion de responsabilité d’archivage aux partenaires fédérés](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui permettent la communication avec les fournisseurs publics ?**

Configurer les paramètres comme indiqué dans les rubriques [Configurer des stratégies pour contrôler l’accès des utilisateurs publics](external-access-policies/configure-policies-to-control-public-user-access.md), [activer ou désactiver la fédération et la connectivité de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et [créer ou modifier des fournisseurs fédérés SIP publics](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)

**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft 365 ou Office 365 et Skype Entreprise Online ?**

Configurez les paramètres comme indiqué dans les rubriques [Activer ou désactiver la fédération et la connectivité de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) et [créer ou modifier des fournisseurs fédérés SIP hébergés](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Votre déploiement est-il configuré dans un domaine séparé (ou domaine hybride), dans lequel certains utilisateurs possèdent leur serveur central dans un déploiement local et d’autres dans un environnement en ligne ?**

Configurez les paramètres comme indiqué dans les rubriques [Configurer les stratégies pour contrôler l’accès des utilisateurs fédérés](external-access-policies/configure-policies-to-control-federated-user-access.md), [activer ou désactiver la fédération et la connectivité de messagerie instantanée publique](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et [créer ou modifier des fournisseurs fédérés SIP hébergés](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

Vous pouvez configurer les paramètres d’accès utilisateur externe même si vous n’avez pas activé l’accès utilisateur externe pour votre organisation. Toutefois, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec vos utilisateurs lorsque l’accès utilisateur externe est désactivé ou si aucune stratégie d’accès utilisateur externe n’est configurée pour le prendre en charge.

Votre déploiement edge authentifie les types d’utilisateurs externes et contrôle l’accès en fonction de la façon dont vous configurez votre prise en charge de la périphérie. L’exception à cette règle concerne les utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et une clé secrète qui est envoyée au participant anonyme lorsque vous créez la conférence et invitez des participants. Pour contrôler la communication, vous pouvez configurer une ou plusieurs stratégies qui définissent la façon dont les utilisateurs à l’intérieur et à l’extérieur de votre organisation communiquent entre eux. Les stratégies et paramètres incluent la stratégie globale par défaut, les stratégies de site et les stratégies utilisateur que vous pouvez créer et configurer.
