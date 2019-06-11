---
title: 'Lync Server 2013 : Configuration de la prise en charge de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f10e266674d102b25753aeb58c89a365e7bb8e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Le déploiement d’un serveur de périphérie ou d’un pool de périphérie est la première étape de la prise en charge des utilisateurs externes. Pour plus d’informations sur le déploiement de serveurs Edge, voir [déploiement d’un accès utilisateur externe dans Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Il est important de tenir compte de la priorité des stratégies et de l’application des stratégies. Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.

Après avoir effectué l’installation d’un serveur de périphérie ou d’un pool de bords, vous devez activer les types d’accès des utilisateurs externes que vous souhaitez fournir et configurer les paramètres pour l’accès externe. Dans Lync Server 2013, vous activez et configurez l’accès et les stratégies des utilisateurs externes à l’aide du panneau de configuration de Lync Server, de Lync Server Management Shell ou les deux, en fonction de la configuration requise pour la tâche.

Pour prendre en charge l’accès utilisateur externe, vous devez effectuer les opérations suivantes:

  - **Permettre la prise en charge de votre organisation**   pour permettre la prise en charge de l’accès des utilisateurs externes à votre déploiement, vous activez chaque type d’accès externe que vous voulez prendre en charge. Vous pouvez activer et désactiver la prise en charge de l’accès des utilisateurs externes en modifiant les paramètres globaux ou en créant et en configurant une stratégie de site ou d’utilisateur sur la page de **stratégie d’accès externe** dans le groupe **Fédération et accès externe** du panneau de configuration de Lync Server. par le biais de Lync Server Management Shell et des cmdlets associées. Les applets de recherche pour la gestion de la **stratégie d’accès externe** se trouvent dans la rubrique Fédération de rubriques [et cmdlets d’accès externe dans Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). L’activation de la prise en charge de l’accès externe indique que vos serveurs exécutant le service Edge d’accès Lync Server prennent en charge les communications avec les serveurs et les utilisateurs externes. Les utilisateurs internes et externes ne peuvent pas communiquer lorsque l’accès des utilisateurs externes est désactivé ou si les stratégies n’ont pas encore été configurées pour la prise en charge.

  - **Configuration et affectation d’une ou de plusieurs stratégies**   pour la prise en charge de l’accès des utilisateurs externes, vous devez configurer des stratégies pour répondre aux exigences suivantes:
    
      - **Les stratégies**   d’accès externe créées avec un site ou une étendue utilisateur (il existe par défaut une stratégie globale et aucun paramètre activé). Vous créez et configurez des stratégies qui contrôlent l’utilisation d’un ou de plusieurs types d’accès utilisateur externe, y compris, l’accès des utilisateurs fédérés (y compris, si sélectionné, des domaines XMPP fédérés) aux utilisateurs distants et les fournisseurs de services de messagerie instantanée publics pris en charge. Vous pouvez configurer des stratégies externes dans le panneau de configuration de Lync Server à l’aide de la stratégie globale ou d’une ou plusieurs stratégies de site et d’utilisateur créées par un autre utilisateur dans la page **stratégie d’accès externe** du groupe **Fédération et accès externe** . La stratégie globale ne peut pas être supprimée. Vous créez et configurez les stratégies de site et d’utilisateur que vous souhaitez utiliser pour limiter l’accès des utilisateurs externes à des sites ou des utilisateurs spécifiques. Les stratégies globales et de site sont automatiquement affectées. Si vous créez et configurez une stratégie utilisateur, vous devez l’attribuer aux utilisateurs spécifiques à l’aide de la page Configuration de l’utilisateur dans le panneau de configuration de Lync Server de la page **utilisateurs** . Recherchez l’utilisateur ou les utilisateurs auxquels vous voulez que cette stratégie s’applique et attribue la stratégie. la personne à laquelle vous voulez qu’il s’applique. Pour attribuer une stratégie utilisateur configurée à un utilisateur, voir [affecter une stratégie d’accès utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Chaque stratégie d’accès des utilisateurs externes peut prendre en charge un ou plusieurs des éléments suivants: accès des utilisateurs distants, accès des utilisateurs fédérés SIP, accès fédéré des utilisateurs fédérés et connectivité PIC.
    
      - **Stratégies de conférence**   vous créez et configurez des stratégies pour contrôler les conférences au sein de votre organisation, notamment les utilisateurs de votre organisation qui peuvent inviter des utilisateurs anonymes à des conférences qu’elles hébergent. Dans la page de **Conférence** du panneau de configuration de Lync Server, les paramètres de stratégie s’appliquent aux stratégies globales, de site et d’utilisateur qui contrôlent les paramètres des conférences véritables. Pour plus d’informations, reportez-vous à la rubrique [gestion des réunions et conférences dans Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Vous pouvez activer les utilisateurs anonymes pour les conférences, les utilisateurs distants et les utilisateurs fédérés dans la page **configuration de Microsoft Edge** . Dans le cadre de la configuration, la stratégie d' **accès** au périmètre est globale. Il n’existe aucune option permettant de définir une stratégie de site ou d’utilisateur. L’étendue est contrôlée sur la page de **stratégie d’accès externe** par le biais de l’utilisation de paramètres de stratégie généraux, de sites ou d’utilisateurs.
        
        Par exemple, si vous voulez permettre aux utilisateurs de créer, d’inviter et de gérer des conférences avec des utilisateurs distants, vous devez définir l' **activation des communications avec les utilisateurs** distants de la **stratégie d’accès externe** , la stratégie de site ou d’utilisateur, et **activer les communications avec les utilisateurs** distants dans la page **configuration de Edge d’accès** . De même, pour permettre aux conférences avec des utilisateurs anonymes ou des partenaires fédérés que vous avez une relation définie avec (par exemple, les domaines SIP et les fournisseurs fédérés configurés) ne prenant pas en charge la fonctionnalité de conférence, vous définissez **activer les communications avec les utilisateurs publics** et **activer les communications avec les utilisateurs fédérés** dans la **stratégie d’accès externe** , stratégie de site ou d’utilisateur. Vous pouvez ensuite sélectionner des paramètres de stratégie globale supplémentaires **activez l’accès anonyme aux conférences** et **activez la connectivité de messagerie instantanée fédérée et publique** dans la page **configuration de Microsoft Edge** .

Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies que vous souhaitez utiliser pour contrôler l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et autres paramètres que vous configurez ne s’appliquent que si l’accès utilisateur externe est activé pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation lorsque l’accès des utilisateurs externes est désactivé ou s’il n’y a pas de stratégie d’accès des utilisateurs externes pour la prise en charge.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et d’une clé d’authentification envoyée au participant anonyme lors de la création de la Conférence et d’invitations aux participants) et de contrôles. Access en fonction de la configuration de votre support Edge. Afin de contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et configurer des paramètres définissant le mode de communication des utilisateurs internes et externes à votre déploiement. Les stratégies et paramètres incluent la stratégie globale par défaut de l’accès des utilisateurs externes, en plus des stratégies de site et d’utilisateur que vous pouvez créer et configurer pour activer un ou plusieurs types d’accès utilisateur externe pour des sites ou des utilisateurs spécifiques.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Activation ou désactivation de l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Activation ou désactivation de l’accès des utilisateurs anonymes dans Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

