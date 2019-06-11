---
title: 'Lync Server 2013: désactiver le prélèvement d’appels de groupe pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76b7e0d17b91accdab0f1590d9fc505dec42f430
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>Désactiver le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-01-30_

Utilisez la procédure suivante pour désactiver le prélèvement d’appels de groupe pour un utilisateur.

<div>


> [!NOTE]  
> Si vous désactivez le prélèvement d’appel de groupe pour un utilisateur, le numéro de groupe de capture d’appel qui a été affecté à l’utilisateur n’est pas conservé. Si vous voulez par la suite réactiver le prélèvement d’appels de groupe pour cet utilisateur, vous devez de nouveau affecter le numéro de groupe de capture d’appel avec le paramètre/enablegrouppickup.



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>Pour désactiver le prélèvement d’appels de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Attribution de numéros de numérotation des appels de groupe aux utilisateurs dans Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

