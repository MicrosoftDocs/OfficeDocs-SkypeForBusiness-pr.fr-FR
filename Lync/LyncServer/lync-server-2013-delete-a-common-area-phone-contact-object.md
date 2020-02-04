---
title: 'Lync Server 2013 : supprimer un objet de contact de téléphone de zone commune'
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
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>Supprimer un objet de contact de téléphone pour les zones communes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous souhaiterez peut-être supprimer l’objet contact associé à un téléphone de zone commune. Par exemple, si vous supprimez le téléphone d’une salon d’employé, il est inutile d’avoir un objet de contact associé à ce téléphone. L’applet de passe **Remove-CsCommonAreaPhone** vous permet de supprimer les comptes de téléphone de zone commune. Lorsque vous exécutez cette cmdlet, le téléphone est supprimé de la liste des téléphones communs renvoyés par **Get-CsCommonAreaPhone**. Par ailleurs, l’objet contact associé à ce téléphone est supprimé des services de domaine Active Directory (AD FS).

Utilisez **Remove-CsCommonAreaPhone** pour supprimer un téléphone standard ou tous les téléphones communs qui possèdent un élément commun, comme un nom d’affichage ou un indicatif de pays ou de région. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>Suppression d’un téléphone commun spécifié

  - La commande suivante permet de supprimer le téléphone de zone commune avec l’adresse SIP sip :mainlobby@litwareinc.com :
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>Suppression de téléphones communs en fonction de leur nom d’affichage

  - Cette commande supprime tous les téléphones de surface courants dans lesquels le nom d’affichage inclut la valeur de chaîne « bâtiment 14 » :
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>Supprimer des téléphones communs en fonction de leur indicatif national et de leur région

  - Cette commande supprime tous les téléphones de surface commune pour les États-Unis (code pays 1) et l’indicatif régional 425 :
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) .

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

