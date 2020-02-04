---
title: 'Lync Server 2013 : Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes'
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
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Par défaut, tous les utilisateurs ne peuvent pas inviter des utilisateurs anonymes à participer à une réunion. Vous contrôlez qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et en appliquant cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge les utilisateurs anonymes, voir [créer ou modifier une stratégie de conférence dans Lync server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) et [gérer la Fédération et l’accès externe à Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md).

Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence que vous avez déjà créée à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

<div>


> [!NOTE]  
> En plus de configurer et d’appliquer une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez également activer la prise en charge des utilisateurs anonymes pour votre organisation. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Pour configurer une stratégie utilisateur pour la participation anonyme aux réunions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans le champ **nom** , créez un nom unique qui indique l’objet de la stratégie de l’utilisateur (par exemple, **EnableAnonymous** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).
    
    2.  Pour configurer une stratégie d’utilisateur existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

4.  Dans la boîte de dialogue **stratégies de conférence** , activez la case à cocher **autoriser les participants à inviter des utilisateurs anonymes** .

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis recherchez le compte d’utilisateur que vous voulez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

8.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie de conférence**, sélectionnez la stratégie de l’utilisateur avec la configuration d’accès anonyme pour les utilisateurs que vous souhaitez appliquer à cet utilisateur.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent les paramètres d’installation par défaut du serveur et sont appliqués automatiquement par le serveur.

    
    </div>

Pour permettre aux utilisateurs d’inviter des utilisateurs anonymes à des conférences, vous devez également activer la prise en charge des utilisateurs anonymes au sein de votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md) dans la documentation de déploiement ou la documentation des opérations.

</div>

</div>

<span> </span>

</div>

</div>

</div>

