---
title: 'Lync Server 2013 : configuration de la prise en charge de l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56c8c576c15d9f22add0f81c115c44e72a0c0234
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507501"
---
# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Configuration de la prise en charge de l’accès des utilisateurs externes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

La première étape du processus de définition de la prise en charge des utilisateurs externes consiste à déployer un serveur Edge ou un pool Edge. Pour plus d’informations sur le déploiement des serveurs Edge, voir [Deploying External User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) dans la documentation de déploiement. Avant la configuration des stratégies, il est important de bien comprendre les priorités des stratégies, ainsi que leurs applications. Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

Une fois que vous avez fini de configurer un serveur ou un pool Edge, vous devez activer les types d’accès des utilisateurs externes que vous souhaitez fournir et configurer les paramètres des accès externes. Dans Lync Server 2013, vous activez et configurez les stratégies et l’accès des utilisateurs externes à l’aide du panneau de configuration Lync Server, de Lync Server Management Shell ou des deux, en fonction des besoins de la tâche.

Pour prendre en charge l’accès des utilisateurs externes, vous devez effectuer les deux actions suivantes :

  - **Activer la prise en charge pour votre organisation**     Pour activer la prise en charge de l’accès des utilisateurs externes dans votre déploiement, vous activez chaque type d’accès externe que vous souhaitez prendre en charge. Pour activer et désactiver la prise en charge de l’accès des utilisateurs externes, vous devez modifier les paramètres globaux ou créer et configurer une stratégie de site ou d’utilisateur dans la page **stratégie d’accès externe** du groupe de **Fédération et d’accès externe** du panneau de configuration Lync Server ou à l’aide de Lync Server Management Shell et des cmdlets associées. Les applets de commande pour la gestion de la **stratégie d’accès externe** figurent dans la rubrique [Federation Policy and External Access cmdlets in Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Activation de la prise en charge de l’accès externe : indique que vos serveurs exécutant le service Edge d’accès Lync Server prennent en charge les communications avec les serveurs et les utilisateurs externes. Les utilisateurs internes et externes ne peuvent pas communiquer lorsque l’accès des utilisateurs externes est désactivé ou si les stratégies n’ont pas encore été configurées pour le prendre en charge.

  - **Configurer et attribuer une ou plusieurs stratégies**     Pour prendre en charge l’accès des utilisateurs externes, vous configurez des stratégies pour répondre aux exigences qui incluent :
    
      - Stratégies d’accès **externe**     Créé avec une étendue de site ou d’utilisateur (une stratégie globale existe par défaut et n’a pas de paramètres activés). Vous créez et configurez des stratégies pour contrôler l’utilisation d’un ou de plusieurs types d’accès des utilisateurs externes, y compris l’accès des utilisateurs fédérés (y compris, le cas échéant, les domaines XMPP fédérés) et l’accès des utilisateurs distants aux utilisateurs distants et les fournisseurs de services de messagerie instantanée publics pris en charge. Vous configurez des stratégies externes dans le panneau de configuration Lync Server à l’aide de la stratégie globale ou d’une ou de plusieurs stratégies de site et utilisateur créées administrativement dans la page **stratégie d’accès externe** dans le groupe **Fédération et accès externe** . La stratégie globale ne peut pas être supprimée. Vous créez et configurez les stratégies de site et d’utilisateur que vous souhaitez utiliser pour limiter l’accès des utilisateurs externes à des sites ou utilisateurs spécifiques. Les stratégies globales et de site sont automatiquement attribuées. Si vous créez et configurez une stratégie utilisateur, vous devez l’attribuer à des utilisateurs spécifiques à l’aide de la page Configuration de l’utilisateur dans le panneau de configuration de Lync Server, dans la page **utilisateurs** . Recherchez l’utilisateur ou les utilisateurs auxquels vous souhaitez que cette stratégie s’applique et affectez la stratégie. à qui vous voulez qu’il s’applique. Pour affecter une stratégie utilisateur configurée à un utilisateur, reportez-vous à la rubrique [attribuer une stratégie d’accès des utilisateurs externes à un utilisateur compatible Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Chaque stratégie d’accès des utilisateurs externes peut prendre en charge un ou plusieurs des éléments suivants : accès des utilisateurs distants, accès des utilisateurs fédérés SIP, accès des utilisateurs fédérés XMPP et connectivité PIC.
    
      - **Stratégies**     de conférence Vous créez et configurez des stratégies pour contrôler les conférences au sein de votre organisation, notamment les utilisateurs de votre organisation qui peuvent inviter des utilisateurs anonymes à des conférences qu’ils hébergent. Sur la page de **Conférence** du panneau de configuration Lync Server se trouvent les paramètres de stratégie au niveau de l’étendue globale, du site et de l’utilisateur qui contrôlent les paramètres des conférences. Pour plus d’informations, reportez-vous à la rubrique [gestion des réunions et des conférences dans Lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). La page **Configuration du serveur Edge d’accès** permet d’autoriser les utilisateurs anonymes à assister aux conférences et d'activer les utilisateurs distants et fédérés. La stratégie de la **Configuration du serveur Edge d’accès** est d’étendue globale. Il n’y a pas d’option pour définir une stratégie de site ou d’utilisateur. L’étendue est contrôlée sur la page **Stratégie d’accès externe** en utilisant les paramètres de stratégie utilisateur, globale ou de site.
        
        Par exemple, si vous souhaitez autoriser les utilisateurs à créer ou gérer des conférences, ainsi qu’à inviter des participant lorsqu’il s’agit d’utilisateurs distants, vous devez définir **Autoriser les communications avec des utilisateurs distants** sur la **Stratégie d’accès externe** globale, de site ou utilisateur, et **Autoriser les communications avec des utilisateurs distants** sur la page **Configuration du serveur Edge d’accès**. De même, pour autoriser les conférences avec les utilisateurs anonymes ou les partenaires fédérés avec lesquels vous avez une relation définie (comme les domaines et fournisseurs SIP fédérés configurés – la fédération XMPP ne prend pas en charge la conférence), définissez **Autoriser les communications avec des utilisateurs publics** et **Autoriser les communications avec des utilisateurs fédérés** dans la **Stratégie d’accès externe** globale, de site ou utilisateur. Puis, sélectionnez les paramètres de stratégie globale complémentaire **Autoriser l’accès utilisateur anonyme aux conférences** et **Autoriser la connectivité des messageries instantanées publiques et fédérées** sur la page **Configuration du serveur Edge d’accès**.

Vous pouvez configurer les paramètres d’accès des utilisateurs externes, y compris les stratégies de contrôle de l’accès des utilisateurs externes, même si vous n’avez pas activé l’accès des utilisateurs externes pour votre organisation. Toutefois, les stratégies et les autres paramètres que vous configurez ne prennent effet que lorsque vous activez l’accès des utilisateurs externes pour votre organisation. Les utilisateurs externes ne peuvent pas communiquer avec les utilisateurs de votre organisation si l’accès des utilisateurs externes est désactivé ou si aucune stratégie de prise en charge de l’accès des utilisateurs externes n’a été configurée.

Votre déploiement Edge authentifie les types d’utilisateurs externes (à l’exception des utilisateurs anonymes, qui sont authentifiés par l’ID de conférence et une clé de sécurité envoyée aux participants anonymes lorsque vous créez la conférence et invitez des participants) et contrôle l’accès selon la façon dont vous avez configuré la prise en charge de votre déploiement Edge. Pour contrôler les communications, vous pouvez configurer une ou plusieurs stratégies et des paramètres qui définissent comment les utilisateurs situés en amont ou en aval de votre déploiement communiquent entre eux. Ces stratégies et paramètres incluent la stratégie globale par défaut d’accès des utilisateurs externes, en plus des stratégies de site et utilisateur que vous créez et configurez pour activer un ou plusieurs types d’accès des utilisateurs externes à l’intention de sites ou d’utilisateurs spécifiques.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Activer ou désactiver l’accès des utilisateurs distants dans Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Activer ou désactiver l’accès des utilisateurs anonymes dans Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

