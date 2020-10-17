---
title: 'Lync Server 2013 : configuration des stratégies de contrôle de l’accès des utilisateurs distants'
description: 'Lync Server 2013 : configurez les stratégies pour contrôler l’accès des utilisateurs distants.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548710"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurer des stratégies pour contrôler l’accès des utilisateurs distants dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-18_

Vous configurez une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler si les utilisateurs distants peuvent collaborer avec des utilisateurs internes de Lync Server. Pour contrôler l’accès des utilisateurs distants, vous pouvez configurer des stratégies au niveau global, du site et de l’utilisateur. Les stratégies de site remplacent la stratégie globale, et les stratégies utilisateur remplacent les stratégies de site et globale. Pour plus d’informations sur les types de stratégies que vous pouvez configurer, voir gestion de la [Fédération et de l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). Les paramètres de stratégie Lync Server qui sont appliqués au niveau d’une stratégie peuvent remplacer les paramètres appliqués à un autre niveau de stratégie. La politique de priorité de Lync Server est la suivante : la stratégie utilisateur (la plus influente) remplace une stratégie site, et une stratégie site remplace une stratégie globale (la moins influente). Cela signifie que plus le paramètre de stratégie est proche de l’objet que la stratégie affecte, plus elle a d’influence sur l’objet.

<div>


> [!NOTE]  
> Vous pouvez configurer des stratégies pour contrôler l’accès des utilisateurs distants, même si vous n’avez pas activé l’accès des utilisateurs distants pour votre organisation. Toutefois, les stratégies que vous configurez sont effectives uniquement quand vous activez l’accès des utilisateurs distants pour votre organisation. Pour plus d’informations sur l’activation de l’accès des utilisateurs distants, consultez la rubrique <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013</A>. En outre, si vous spécifiez une stratégie utilisateur pour contrôler l’accès des utilisateurs distants, la stratégie s’applique uniquement aux utilisateurs qui sont activés pour Lync Server et qui sont configurés pour utiliser cette stratégie. Pour plus d’informations sur la spécification des utilisateurs qui peuvent se connecter à Lync Server à partir d’emplacements distants, voir <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">affecter une stratégie d’accès des utilisateurs externes à un utilisateur à extension Lync dans Lync Server 2013</A>.



</div>

Utilisez la procédure suivante pour configurer chaque stratégie d’accès externe que vous comptez utiliser pour contrôle l’accès des utilisateurs distants.

<div>


> [!NOTE]  
> Cette procédure décrit comment configurer une stratégie uniquement pour activer les communications avec les utilisateurs distants, mais chaque stratégie que vous configurez pour prendre en charge l’accès des utilisateurs distants peut également configurer l’accès des utilisateurs fédérés et des utilisateurs publics. Pour plus d’informations sur la configuration des stratégies afin de prendre en charge les utilisateurs fédérés, voir <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in Lync Server 2013</A>. Pour plus d’informations sur la configuration des stratégies afin de prendre en charge les utilisateurs publics, voir <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">créer ou modifier des fournisseurs fédérés SIP publics dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Pour configurer une stratégie d’accès externe permettant de prendre en charge l’accès des utilisateurs distants

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Accès des utilisateurs externes**, puis sur **Stratégie d’accès externe**.

4.  Dans la page **Stratégie d’accès externe**, effectuez l’une des opérations suivantes :
    
      - Pour configurer la stratégie globale permettant la prise en charge de l’accès des utilisateurs distants, cliquez sur la stratégie globale, sur **Modifier**, puis sur **Afficher les détails**.
    
      - Pour créer une nouvelle stratégie de site, cliquez sur **Nouveau**, puis sur **Stratégie du site**. Dans **Sélectionner un site**, cliquez sur le site approprié dans la liste, puis cliquez sur **OK**.
    
      - Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans **Nouvelle stratégie d’accès externe**, créez dans le champ **Nom** un nom unique qui indique ce que couvre la stratégie utilisateur (par exemple, **EnableRemoteUsers** pour une stratégie utilisateur qui permet les communications des utilisateurs distants).
    
      - Pour modifier une stratégie existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  (Facultatif) Si vous souhaitez ajouter ou modifier une description, spécifiez les informations relatives à la stratégie dans **Description**.

6.  Effectuez l’une des opérations suivantes :
    
      - Afin d’activer l’accès des utilisateurs distants pour la stratégie, activez la case à cocher **Autoriser les communications avec des utilisateurs distants**.
    
      - Afin de désactiver l’accès des utilisateurs distants pour la stratégie, désactivez la case à cocher **Autoriser les communications avec des utilisateurs distants**.

7.  Cliquez sur **Valider**.

Pour activer l’accès des utilisateurs distants, vous devez aussi activer la prise en charge de l’accès des utilisateurs distants dans votre organisation. Pour plus d’informations, consultez la rubrique [activation ou désactivation de la Fédération et de la connectivité PIC dans Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) dans la documentation de déploiement ou la documentation des opérations.

S’il s’agit d’une stratégie utilisateur, vous devez aussi appliquer la stratégie aux utilisateurs que vous souhaitez autoriser à se connecter à distance. Pour plus d’informations, reportez-vous à la rubrique [attribuer une stratégie d’accès des utilisateurs externes à un utilisateur activé pour Lync dans Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) dans la documentation de déploiement ou dans la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

