---
title: 'Lync Server 2013 : affectation de numéros de prise d’appel de groupe aux utilisateurs'
description: 'Lync Server 2013 : affectez des numéros de prise d’appel de groupe à des utilisateurs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566130"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Une fois que vous avez ajouté les numéros de groupe de prise d’appel de groupe à la table des orbites de parcage d’appel, vous pouvez affecter les groupes aux utilisateurs. Utilisez l’outil de kit de ressources de fonctionnalité d’extension secondaire (SEFAUtil) pour affecter des groupes de prise d’appel aux utilisateurs.

<div>


> [!NOTE]  
> Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe aux utilisateurs hébergés en ligne. Les utilisateurs hébergés en ligne ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être traités par d’autres utilisateurs, et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>Pour affecter un groupe de prise d’appel de groupe à un utilisateur

1.  Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Par exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

