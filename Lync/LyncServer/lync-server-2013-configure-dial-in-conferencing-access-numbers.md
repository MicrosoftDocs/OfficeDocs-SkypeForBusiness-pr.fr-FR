---
title: 'Lync Server 2013 : Configuration des numéros d’accès aux conférences rendez-vous'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Configuration des numéros d’accès aux conférences rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2011-07-17_

Lorsque vous déployez des conférences rendez-vous, vous devez configurer les numéros de téléphone que les utilisateurs peuvent appeler à partir du réseau téléphonique commuté pour participer à la partie audio des conférences. Ces numéros s’affichent dans les invitations à une réunion et sur la page web des paramètres de configuration des conférences rendez-vous.

Avant de créer des numéros d’accès aux conférences rendez-vous, vous devez planifier vos régions de conférences rendez-vous puis configurer les plans de numérotation correspondants. Pour plus d’informations sur les régions, voir [exigences relatives aux conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) dans la documentation de planification. Pour plus d’informations sur la configuration de plans de numérotation pour les conférences rendez-vous, voir [configurer des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).

<div>


> [!NOTE]  
> Vous ne pouvez pas utiliser de nouveau numéro d’accès rendez-vous tant que la&nbsp;réplication des services de domaine Active Directory (AD DS) n’est pas terminée. La réplication peut durer plusieurs heures.



</div>

<div>


> [!NOTE]  
> Une fois que vous avez créé les numéros d’accès aux conférences rendez-vous, vous pouvez modifier le nom complet des objets contact Active Directory pour permettre aux utilisateurs d’identifier plus facilement le numéro d’accès approprié. Utilisez l’applet de cmdlet <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> pour modifier le nom d’affichage. Vous ne devez pas modifier manuellement les objets Active Directory. Pour plus d’informations sur la modification d’un numéro d’accès, reportez-vous à la documentation Lync Server Management Shell pour l’applet <STRONG>de connexion Set-CsDialInConferencingAccessNumber</STRONG> .



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

[Création ou modification d’un numéro d’accès à une conférence rendez-vous dans Lync Server 2013](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration requise pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md)  


[Configuration des plans de numérotation pour les conférences rendez-vous dans Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

