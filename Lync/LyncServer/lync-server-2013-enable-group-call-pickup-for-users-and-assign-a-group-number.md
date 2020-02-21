---
title: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs et attribution d’un numéro de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b4c0bc47862eaaf2cf74d29190325d9d09ee939
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013 et affecter un numéro de groupe

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Une fois que vous avez ajouté des numéros de groupe de prise d’appel à la table d’orbites de parcage d’appel, vous affectez les numéros de groupe aux utilisateurs et activez la prise d’appel de groupe. Utilisez l’outil de kit de ressources de fonctionnalité d’extension secondaire (SEFAUtil) pour affecter des numéros de groupe et activer la prise d’appel de groupe.

<div>


> [!NOTE]  
> Dans un déploiement hybride, n’affectez pas un groupe de prise d’appel de groupe aux utilisateurs hébergés en ligne. Les utilisateurs hébergés en ligne ne peuvent pas participer à la prise d’appel de groupe. Autrement dit, leurs appels ne peuvent pas être traités par d’autres utilisateurs, et ils ne peuvent pas répondre aux appels à d’autres utilisateurs.



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>Pour affecter un numéro de groupe et activer la prise d’appel de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Par exemple, pour attribuer le numéro de groupe 199 à un utilisateur :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

