---
title: 'Lync Server 2013 : Configuration des stratégies de contrôle d’accès des utilisateurs distants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configuration des stratégies de contrôle d’accès des utilisateurs distants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-18_

Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs internes du serveur Lync. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau du site, du site et de l’utilisateur. Les stratégies de site remplacent la stratégie globale et les stratégies d’utilisateur remplacent les stratégies de site et globales. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir gestion de la [Fédération et accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Les paramètres de stratégie Lync Server appliqués à un niveau de stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. Le niveau de priorité de la stratégie de serveur Lync est défini comme suit: la stratégie d’utilisateur (la plus influence) a pour effet de remplacer une stratégie de site, puis une stratégie de site remplace une stratégie globale (moins l’influence). Cela signifie que le paramètre de stratégie est plus proche de l’objet affecté par la stratégie, plus l’influence sur l’objet.

<div>


> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation. Toutefois, les stratégies que vous configurez ne s’appliquent que si l’accès des utilisateurs distants est activé pour votre organisation. Pour plus d’informations sur l’activation de l’accès des utilisateurs distants, voir <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">activer ou désactiver la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013</A>. De plus, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs qui peuvent se connecter à Lync Server à partir d’emplacements distants, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès des utilisateurs externes à un utilisateur compatible Lync dans Lync Server 2013</A>.



</div>

Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe à utiliser pour contrôler l’accès des utilisateurs distants.

<div>


> [!NOTE]  
> Cette procédure décrit comment configurer une stratégie uniquement pour activer les communications avec les utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants peut également configurer l’accès des utilisateurs fédérés et l’accès des utilisateurs publics. Pour plus d’informations sur la configuration des stratégies pour la prise en charge des utilisateurs fédérés, voir <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configurer des stratégies pour contrôler l’accès des utilisateurs fédérés dans Lync Server 2013</A>. Pour plus d’informations sur la configuration des stratégies permettant de prendre en charge les utilisateurs publics, voir <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">créer ou modifier des fournisseurs fédérés SIP publics dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Pour configurer une stratégie d’accès externe pour prendre en charge l’accès des utilisateurs distants

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **accès utilisateur externe**, puis sur **stratégie d’accès externe**.

4.  Dans la page de **stratégie d’accès externe** , effectuez l’une des opérations suivantes:
    
      - Pour configurer la stratégie globale de manière à prendre en charge l’accès des utilisateurs distants, cliquez sur la stratégie globale, cliquez sur **modifier**, puis sur **afficher les détails**.
    
      - Pour créer une stratégie de site, cliquez sur **nouveau**, puis cliquez sur **stratégie de site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans **nouvelle stratégie d’accès externe**, créez un nom unique dans le champ **nom** qui indique le texte de la stratégie de l’utilisateur (par exemple, **EnableRemoteUsers** pour une stratégie utilisateur qui autorise les communications pour les utilisateurs distants).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

5.  Facultatif Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des actions suivantes :
    
      - Pour autoriser l’accès des utilisateurs distants à la stratégie, activez la case à cocher **activer les communications avec les utilisateurs** distants.
    
      - Pour désactiver l’accès des utilisateurs distants de la stratégie, décochez la case **activer les communications avec les utilisateurs** distants.

7.  Cliquez sur **Valider**.

Pour autoriser l’accès des utilisateurs distants, vous devez également activer la prise en charge de l’accès des utilisateurs distants au sein de votre organisation. Pour plus d’informations, reportez-vous à [activation ou désactivation de la connectivité de Fédération et de messagerie instantanée publique dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) dans la documentation de déploiement ou la documentation des opérations.

S’il s’agit d’une stratégie de l’utilisateur, vous devez également appliquer la stratégie aux utilisateurs auxquels vous voulez vous connecter à distance. Pour plus d’informations, voir [affecter une stratégie d’accès utilisateur externe à un utilisateur compatible Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) dans la documentation de déploiement ou la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

