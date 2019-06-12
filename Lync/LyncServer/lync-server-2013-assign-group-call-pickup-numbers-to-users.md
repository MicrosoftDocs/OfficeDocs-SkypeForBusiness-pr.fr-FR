---
title: 'Lync Server 2013: attribution de numéros de numérotation des appels de groupe aux utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Attribution de numéros de numérotation des appels de groupe aux utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

Une fois que vous avez ajouté des numéros de groupe de sélection d’appels de groupe à la table d’orbite du parc d’appels, vous pouvez affecter les groupes aux utilisateurs. Utilisez l’outil Kit de ressources de l’extension secondaire (SEFAUtil) pour affecter des groupes de capture d’appel aux utilisateurs.

<div>


> [!NOTE]  
> Dans un déploiement hybride, n’affectez pas de groupe de collecte d’appels de groupe aux utilisateurs hébergés en ligne. Les utilisateurs hébergés en ligne ne peuvent pas participer à la cueillette du groupe. Autrement dit, leurs appels ne peuvent pas être pris par d’autres utilisateurs et ils ne peuvent pas répondre aux appels destinés à d’autres utilisateurs.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Pour affecter un groupe de prélèvement d’appels de groupe à un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Désactiver le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

