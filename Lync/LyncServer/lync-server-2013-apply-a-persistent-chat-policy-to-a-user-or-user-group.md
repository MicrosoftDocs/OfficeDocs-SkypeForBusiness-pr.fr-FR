---
title: 'Lync Server 2013 : Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2fbed0a752c1bf97bab5a4f67fadf12d8077a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846911"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Si un utilisateur a été activé pour Lync Server 2013, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour le serveur de chat permanent.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Pour configurer les paramètres de configuration de serveur Chat permanent, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer globalement les options de serveur de chat permanent ou pour le pool de serveurs de chat permanent dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie d’utilisateur de conversation permanente créée précédemment à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Pour appliquer une stratégie utilisateur de conversation permanente à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.

2.  Dans le menu **Démarrer** , sélectionnez le panneau de configuration de Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie de chat persistante**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous voulez appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent la stratégie d’effectivité par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

    
    </div>

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

