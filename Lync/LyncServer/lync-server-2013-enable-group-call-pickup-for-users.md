---
title: 'Lync Server 2013 : activer le prélèvement d’appels de groupe pour les utilisateurs'
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
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>Activer le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-30_

Utilisez l’outil de kit de ressources SEFAUtil pour activer le regroupement d’appels de groupe pour les utilisateurs. Les utilisateurs doivent se voir attribuer un numéro de groupe avec le type GroupPickup dans la table de stationnement d’appel. Vous attribuez un numéro de groupe de capture d’appel et activez la collecte d’appels de groupe en même temps à l’aide du paramètre/enablegrouppickup lorsque vous exécutez SEFAUtil. exe.

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>Pour activer le prélèvement d’appels de groupe pour un utilisateur

1.  Ouvrez une session sur l’ordinateur où vous avez installé l’outil SEFAUtil avec des droits d’administrateur.

2.  À partir de la ligne de commande, exécutez la commande suivante :
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Exemple :
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Attribution de numéros de numérotation des appels de groupe aux utilisateurs dans Lync Server 2013](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Désactiver le prélèvement d’appels de groupe pour les utilisateurs dans Lync Server 2013](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

