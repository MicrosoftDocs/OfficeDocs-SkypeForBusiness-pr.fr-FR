---
title: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs'
description: 'Lync Server 2013 : activation de la prise d’appel de groupe pour les utilisateurs.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559620"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Activer la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Utilisez l’outil Kit de ressources SEFAUtil pour activer la prise d’appel de groupe pour les utilisateurs. Les utilisateurs doivent se voir attribuer un numéro de groupe avec le type GroupPickup dans la table des orbites de parcage d’appel pour activer la prise d’appel de groupe. Vous pouvez attribuer un numéro de groupe de prise d’appel et activer la prise d’appel de groupe en même temps à l’aide du paramètre/enablegrouppickup lorsque vous exécutez SEFAUtil.exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Pour activer la prise d’appel de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur sur lequel vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Par exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Affecter des numéros de prise d’appel de groupe aux utilisateurs dans Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Désactivation de la prise d’appel de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

