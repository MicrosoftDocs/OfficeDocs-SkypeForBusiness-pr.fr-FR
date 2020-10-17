---
title: 'Lync Server 2013 : affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de154fca02470003fdedd0ff29cc8c879d1865aa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523191"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Par défaut, aucun utilisateur ne peut inviter d’utilisateurs anonymes à participer à une réunion. Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la configuration des stratégies de conférence afin de prendre en charge les utilisateurs anonymes, voir [Create or Modify a Conferencing Policy in Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [Managing Federation and External Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence, que vous avez déjà créée, à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

<div>


> [!NOTE]  
> Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez aussi activer la prise en charge des utilisateurs anonymes pour votre organisation. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">configure Policies to Control public user Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Pour configurer une stratégie utilisateur en vue d’une participation anonyme aux réunions

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans le champ **Nom**, créez un nom unique indiquant ce qu’englobe la stratégie utilisateur (par exemple, **AutoriserAnonyme** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).
    
    2.  Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

4.  Dans la boîte de dialogue **Stratégies de conférence**, activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

8.  Dans **Modifier l’utilisateur Lync Server**, sous **Stratégie de conférence**, sélectionnez la stratégie utilisateur spécifiant la configuration d’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres d’installation du serveur par défaut et sont appliqués automatiquement par le serveur.

    
    </div>

Pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences, vous devez aussi activer la prise en charge des utilisateurs anonymes dans votre organisation. Pour plus d’informations, voir [configure Policies to Control public user Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) dans la documentation de déploiement ou la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

