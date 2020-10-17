---
title: 'Lync Server 2013 : suppression d’un objet contact de téléphone de partie commune'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38126f54e02738b1f48b42022a9061055e271d18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525721"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Supprimer un objet contact de téléphone de partie commune dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous pouvez supprimer l’objet contact associé à un téléphone de partie commune. Par exemple, si vous supprimez le téléphone d’une salle d’employés, il n’est pas nécessaire qu’un objet contact soit associé à ce téléphone. L’applet de commande **Remove-CsCommonAreaPhone** vous permet de supprimer des comptes de téléphonie de partie commune. Lorsque vous exécutez cette applet de commande, le téléphone est supprimé de la liste des téléphones de partie commune renvoyée par **Get-CsCommonAreaPhone**. En outre, l’objet contact associé à ce téléphone est supprimé des services de domaine Active Directory.

Utilisez **Remove-CsCommonAreaPhone** pour supprimer un téléphone de partie commune ou tous les téléphones de partie commune qui ont un élément commun, comme un nom d’affichage, un pays et un indicatif régional. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Suppression d’un téléphone de partie commune spécifié

  - La commande suivante permet de supprimer le téléphone de partie commune avec l’adresse SIP sip :mainlobby@litwareinc.com :
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Suppression des téléphones de partie commune en fonction de leur nom d’affichage

  - Cette commande permet de supprimer tous les téléphones de partie commune pour lesquels le nom d’affichage inclut la valeur de chaîne « Building 14 » :
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Suppression des téléphones de partie commune en fonction de leurs indicatifs de pays et de région

  - Cette commande permet de supprimer tous les téléphones de partie commune pour les États-Unis (code pays 1) et l’indicatif régional 425 :
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

