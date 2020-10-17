---
title: 'Lync Server 2013 : suppression d’une annonce'
description: 'Lync Server 2013 : suppression d’une annonce.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 722028f684734504d86bfc986250a2a1dd17fabc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553670"
---
# <a name="delete-an-announcement-in-lync-server-2013"></a>Supprimer une annonce dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Procédez de la façon suivante pour supprimer une annonce utilisée pour passer des appels à des numéros non attribués.

<div>

## <a name="to-delete-an-announcement"></a>Pour supprimer une annonce

1.  Ouvrez une session sur l’ordinateur sur lequel Lync Server Management Shell est installé en tant que membre du groupe RTCUniversalServerAdmins ou avec les droits d’utilisateur nécessaires tels que décrits dans [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Répertoriez toutes les annonces de votre organisation. À partir de la ligne de commande, exécutez la commande suivante :
    
        Get-CsAnnouncement

4.  Dans la liste obtenue, recherchez l’annonce que vous voulez supprimer et copiez le GUID. À partir de la ligne de commande, exécutez la commande suivante :
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    Par exemple :
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur d’autres options, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</A> et <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer une annonce dans Lync Server 2013](lync-server-2013-create-an-announcement.md)  


[Remove-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

