---
title: 'Lync Server 2013 : gestion de la Fédération et de l’accès externe à Skype entreprise Server'
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
f1.keywords:
- NOCSH
localization_priority: Normal
description: Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs de Skype entreprise Server internes.
ms.openlocfilehash: a5437cb15f47a9414ed33dca94e55b770f36d651
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221648"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>Gestion de la Fédération et de l’accès externe à Skype entreprise Server

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool Edge. Pour plus d’informations sur le déploiement des serveurs Edge, voir [Deploy Edge Server in Skype for Business Server](../../deploy/deploy-edge-server/deploy-edge-server.md).

Après avoir installé et configuré votre déploiement interne de Skype entreprise Server, les utilisateurs internes au sein de votre organisation peuvent collaborer avec d’autres utilisateurs internes disposant de comptes SIP dans vos services de domaine Active Directory (AD DS). La collaboration peut prendre la forme d’envoi et réception de messages instantanés et de mise à jour du statut de présence ainsi que la participation à des conférences (ou réunions). Vous activez et configurez l’accès des utilisateurs externes pour contrôler si les utilisateurs externes pris en charge peuvent collaborer avec des utilisateurs de Skype entreprise Server internes. Les utilisateurs externes peuvent inclure les utilisateurs distants de votre déploiement, les utilisateurs fédérés (y compris les utilisateurs pris en charge par les fournisseurs de services de messagerie instantanée publique) et les participants anonymes aux conférences.

Si votre déploiement inclut l’installation d’un serveur Edge Skype entreprise Server ou d’un pool Edge, l’étendue des types de communication possibles est grandement étendue avec un certain nombre d’options pour l’accès des utilisateurs externes, la communication avec les membres d’autres domaines fédérés SIP et les fournisseurs fédérés SIP. Après avoir configuré le serveur Edge ou le pool de serveurs Edge, vous permettez aux types d’accès des utilisateurs externes que vous souhaitez fournir et vous configurez les stratégies pour contrôler l’accès externe. Dans Skype entreprise Server, vous activez et configurez les stratégies et l’accès des utilisateurs externes à l’aide du panneau de configuration Skype entreprise Server, de [Skype entreprise Server Management Shell](../management-shell.md), ou des deux, en fonction des besoins de la tâche. 



> [!IMPORTANT]  
> Vous devez bien saisir la priorité des stratégies et la façon dont elles sont appliquées avant de concevoir votre configuration et vos stratégies pour l’accès des utilisateurs externes. Les paramètres de stratégie de Skype entreprise Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Skype Entreprise Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.


Par défaut, aucune stratégie n’est configurée pour prendre en charge l’accès des utilisateurs externes, notamment l’accès des utilisateurs distants et des utilisateurs fédérés, même si vous avez déjà activé la prise en charge de l’accès des utilisateurs externes dans votre organisation. Pour contrôler l’accès des utilisateurs externes, vous devez configurer au moins une stratégie, qui spécifie le type d’accès des utilisateurs externes pris en charge. Cela inclut les stratégies d’accès externe suivantes :

  - **Stratégie globale**   la stratégie globale est créée lorsque vous déployez vos serveurs Edge. Par défaut, aucune option d’accès utilisateur externe n’est activée dans la stratégie globale. Pour prendre en charge l’accès utilisateur externe au niveau global, vous devez configurer la stratégie globale pour prendre en charge un ou plusieurs types d’options d’accès utilisateur externe. La stratégie globale s’applique à tous les utilisateurs de votre organisation, mais les stratégies de site et les stratégies d’utilisateur remplacent la stratégie globale. Si vous supprimez la stratégie globale, vous ne la supprimez pas. Au lieu de cela, vous la réinitialisez au paramètre par défaut.

  - **Stratégie de site**   Vous pouvez créer et configurer une ou plusieurs stratégies de site pour limiter la prise en charge de l’accès des utilisateurs externes à des sites spécifiques. La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie. Par exemple, si vous activez l’accès des utilisateurs distants dans la stratégie globale, vous pouvez spécifier une stratégie de site qui désactive l’accès sur un site donné. Par défaut, une stratégie de site s’applique à tous les utilisateurs de ce site, mais vous pouvez affecter une stratégie d’utilisateur qui supplante la configuration de la stratégie de site.

  - **Stratégie d’utilisateur**   Vous pouvez créer et configurer une ou plusieurs stratégies utilisateur pour limiter la prise en charge de l’accès des utilisateurs distants à des utilisateurs spécifiques. La stratégie utilisateur supplante les stratégies globale et de site, uniquement pour les utilisateurs auxquels elle est affectée. Par exemple, si vous activez l’accès des utilisateurs distants dans les stratégies globale et de site, vous pouvez définir une stratégie utilisateur qui désactive l’accès des utilisateurs distants et l’affecter à des utilisateurs spécifiques. Si vous créez une stratégie utilisateur, vous devez l’appliquer à un ou plusieurs utilisateurs pour qu’elle prenne effet.

Pour déterminer les paramètres de configuration et les stratégies à créer ou modifier, reportez-vous aux points de décision suivants :

**Voulez-vous autoriser les utilisateurs internes et externes de votre domaine à collaborer à l’aide de la messagerie instantanée, des conférences web et de l’audio/vidéo ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Remote User adtentions](external-access-policies/configure-policies-to-control-remote-user-access.md), et [Enable or Disable Federation and Public IM Connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

**Voulez-vous autoriser les utilisateurs anonymes à participer et être invité à des conférences hébergées par des utilisateurs au sein de votre déploiement ?**

Configurez les paramètres comme indiqué dans la rubrique [attribuer des stratégies de conférence pour prendre en charge les utilisateurs anonymes](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) et [créer des stratégies de conférence](../conferencing/create-policies.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec des contacts de domaines fédérés SIP ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Federated User Access](external-access-policies/configure-policies-to-control-federated-user-access.md), [Enable or Disable Federation and Public IM Connectivity et](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) [Manage SIP Federated Domains for Your Organization](sip-domains/manage-sip-federated-domains-for-your-organization.md).


**Si vous avez activé la communication avec les domaines fédérés SIP, voulez-vous activer la découverte automatique de la Fédération SIP ?**

Configurez les paramètres comme indiqué dans la rubrique [activation ou désactivation de la découverte des partenaires de Fédération](access-edge/enable-or-disable-discovery-of-federation-partners.md).

**Si vous avez activé la communication avec les domaines de fédération SIP, voulez-vous activer l’envoi d’un dédit de responsabilité aux contacts fédérés leur indiquant que vous utilisez l’archivage et que les communications peuvent être archivées ?**

Configurez les paramètres comme indiqué dans la rubrique [activer ou désactiver l’envoi d’une clause d’exclusion de responsabilité d’archivage aux partenaires fédérés dans](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).

**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui permettent la communication avec des fournisseurs publics ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control public user Access](external-access-policies/configure-policies-to-control-public-user-access.md), [Enable or Disable Federation and Public IM Connectivity et](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) [Create or Edit public public Federated Providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server) .


**Voulez-vous autoriser les utilisateurs à communiquer avec des fournisseurs fédérés SIP qui sont des fournisseurs hébergés exécutant Microsoft 365 ou Office 365 et Skype entreprise Online ?**

Configurez les paramètres comme indiqué dans les rubriques [activation ou désactivation de la Fédération et de la connectivité PIC](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) et [création ou modification des fournisseurs fédérés SIP hébergés](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).

**Votre déploiement est-il configuré dans un domaine séparé (ou domaine hybride), dans lequel certains utilisateurs possèdent leur serveur central dans un déploiement local et d’autres dans un environnement en ligne ?**

Configurez les paramètres comme indiqué dans les rubriques [configure Policies to Control Federated User Access](external-access-policies/configure-policies-to-control-federated-user-access.md), [Enable or Disable Federation and Public IM Connectivity](access-edge/enable-or-disable-federation-and-public-im-connectivity.md), et [Create or Edit Hosted SIP Federated Providers](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server).


Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies de contrôle de l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation si l’accès des utilisateurs externes est désactivé ou si aucune stratégie de prise en charge de l’accès des utilisateurs externes n’a été configurée.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et une clé de sécurité envoyée aux participants anonymes lorsque vous créez la conférence et invitez des participants) et contrôle l’accès selon la façon dont vous avez configuré la prise en charge de votre déploiement Edge. Pour contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et des paramètres qui définissent comment les utilisateurs situés en amont ou en aval de votre déploiement communiquent entre eux. Ces stratégies et paramètres incluent la stratégie globale par défaut d’accès des utilisateurs externes, en plus des stratégies de site et utilisateur que vous créez et configurez pour activer un ou plusieurs types d’accès des utilisateurs externes à l’intention de sites ou d’utilisateurs spécifiques.

