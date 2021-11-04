---
title: 'Lync Server 2013 : Gestion de la fédération et de l’accès externe aux Skype Entreprise Server'
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs Skype Entreprise Server internes.
ms.openlocfilehash: 2521d3f4d4134c4edb89904e5a7db4e4026b79e6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743550"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestion de la fédération et de l’accès externe aux Skype Entreprise Server

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool Edge. Pour plus d’informations sur le déploiement des serveurs Edge, voir [Deploy Edge Server in Skype Entreprise Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Après avoir installé et configuré votre déploiement interne de Skype Entreprise Server, les utilisateurs internes de votre organisation peuvent collaborer avec d’autres utilisateurs internes qui ont des comptes SIP dans vos services de domaine Active Directory (AD DS). La collaboration peut prendre la forme d’envoi et réception de messages instantanés et de mise à jour du statut de présence ainsi que la participation à des conférences (ou réunions). Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs Skype Entreprise Server internes. Les utilisateurs externes peuvent inclure les utilisateurs distants de votre déploiement, les utilisateurs fédérés (y compris les utilisateurs pris en charge des fournisseurs de services de messagerie instantanée publics) et les participants anonymes aux conférences.

Si votre déploiement incluait l’installation d’un serveur Edge Skype Entreprise Server ou d’un pool de serveurs Edge, l’étendue des types de communication possibles est largement étendue avec un certain nombre d’options pour l’accès des utilisateurs externes, la communication avec les membres d’autres domaines fédérés SIP et fournisseurs fédérés SIP. Après avoir configuré le serveur Edge ou le pool de serveurs Edge, vous activez les types d’accès des utilisateurs externes que vous souhaitez fournir et configurez les stratégies à contrôler pour l’accès externe. Dans Skype Entreprise Server, vous activez et configurez l’accès des utilisateurs externes et les stratégies à l’aide du Panneau de configuration Skype Entreprise Server, de l’environnement de Skype Entreprise Server [Management Shell](../management-shell.md)ou des deux, en fonction des exigences des tâches. 



> [!IMPORTANT]  
> Vous devez bien saisir la priorité des stratégies et la façon dont elles sont appliquées avant de concevoir votre configuration et vos stratégies pour l’accès des utilisateurs externes. Skype Entreprise Server de stratégie appliquées à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.


Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer au moins une stratégie, qui spécifie le type d’accès des utilisateurs externes pris en charge. Cela inclut les stratégies d’accès externe suivantes :

  - **Stratégie globale**   La stratégie globale est créée lors du déploiement des serveurs Edge. Par défaut, aucune option d’accès des utilisateurs externes n’est activée dans cette stratégie. Pour prendre en charge l’accès des utilisateurs externes au niveau global, vous devez configurer la stratégie globale pour qu’elle prenne en charge un ou plusieurs types d’option d’accès des utilisateurs externes. La stratégie globale s’applique à tous les utilisateurs de votre organisation. Toutefois, les stratégies de niveau site et utilisateur la supplantent. Si vous supprimez la stratégie globale, il n’est pas nécessaire de la retirer. Il vous suffit de rétablir ses paramètres par défaut.

  - **Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La stratégie de site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site. Vous pouvez affecter une stratégie utilisateur qui supplante la stratégie de site.

  - **Stratégie de l’utilisateur** : vous pouvez créer et configurer une ou plusieurs stratégies d’utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La configuration de la stratégie d’utilisateur supplante les stratégies globale et du site, mais uniquement pour les utilisateurs pour lesquelles elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et du site, vous pouvez spécifier une stratégie d’utilisateur qui désactive l’accès des utilisateurs distants, puis affecte cette stratégie d’utilisateur à des utilisateurs spécifiques. Si vous créez une stratégie d’utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs avant qu’elle n’entre en vigueur.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants :

**Voulez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, des conférences web et de l’audio/vidéo ?**

Configurez les paramètres comme détaillé dans les rubriques [Configure policies to control remote user acces](external-access-policies/configure-policies-to-control-remote-user-access.md), and [Enable or disable federation and public IM connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Voulez-vous autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par des utilisateurs au sein de votre déploiement ?**

Configurez les paramètres comme détaillé [](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) dans la rubrique Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes et créer des stratégies [de conférence.](../conferencing/create-policies.md)

**Voulez-vous autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme détaillé dans les [rubriques](external-access-policies/configure-policies-to-control-federated-user-access.md)Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, Activer ou désactiver la fédération et la connectivité [DE](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)messagerie instantanée publique, et Gérer les domaines fédérés [SIP](sip-domains/manage-sip-federated-domains-for-your-organization.md)pour votre organisation.


**Si vous avez activé la communication avec les domaines fédérés SIP, souhaitez-vous activer la découverte automatique de fédération SIP ?**

Configurez les paramètres comme détaillé dans la rubrique Activer ou désactiver la [découverte des partenaires de fédération.](access-edge/enable-or-disable-discovery-of-federation-partners.md)

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer l’envoi d’un dédit de responsabilité aux contacts fédérés leur indiquant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme détaillé dans la rubrique Activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires [fédérés dans](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec les fournisseurs fédérés SIP qui permettent la communication avec des fournisseurs publics ?**

Configurez les paramètres comme détaillé dans les [rubriques](external-access-policies/configure-policies-to-control-public-user-access.md)Configurer des stratégies pour contrôler l’accès des utilisateurs publics, Activer ou désactiver la fédération et la connectivité [DE](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)messagerie instantanée publique, et créer ou modifier des fournisseurs fédérés [SIP](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) publics


**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft 365 ou Office 365 et Skype Entreprise Online ?**

Configurez les paramètres comme détaillé dans les rubriques Activer ou désactiver la fédération et la connectivité [DE](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) messagerie instantanée publique et créer ou modifier des fournisseurs fédérés [SIP hébergés.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)

**Votre déploiement est-il configuré dans un domaine séparé (ou domaine hybride), dans lequel certains utilisateurs possèdent leur serveur central dans un déploiement local et d’autres dans un environnement en ligne ?**

Configurez les paramètres comme détaillé dans les [rubriques](external-access-policies/configure-policies-to-control-federated-user-access.md)Configurer des stratégies pour contrôler l’accès des utilisateurs fédérés, Activer ou désactiver la fédération et la connectivité [DE](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)messagerie instantanée publique, et créer ou modifier des fournisseurs fédérés [SIP hébergés.](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies de contrôle de l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation si l’accès des utilisateurs externes est désactivé ou si aucune stratégie de prise en charge de l’accès des utilisateurs externes n’a été configurée.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et une clé de sécurité envoyée aux participants anonymes lorsque vous créez la conférence et invitez des participants) et contrôle l’accès selon la façon dont vous avez configuré la prise en charge de votre déploiement Edge. Pour contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et des paramètres qui définissent comment les utilisateurs situés en amont ou en aval de votre déploiement communiquent entre eux. Ces stratégies et paramètres incluent la stratégie globale par défaut d’accès des utilisateurs externes, en plus des stratégies de site et utilisateur que vous créez et configurez pour activer un ou plusieurs types d’accès des utilisateurs externes à l’intention de sites ou d’utilisateurs spécifiques.

