---
title: 'Lync Server 2013 : création ou modification d’un objet de contact pour les téléphones communs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e9e7ddf1a4911b9afb3428531911223f62ea723
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Création ou modification d’un objet de contact pour les téléphones communs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Pour créer des objets de contact de services de domaine Active Directory pour tous vos téléphones de zone commune, utilisez l’applet **de contrôle New-CsCommonAreaPhone** . Cette applet de cmdlet peut créer de nouveaux objets de contact à utiliser avec des téléphones de type zone commune ou associer des objets de contact existants à un nouveau téléphone. Pour modifier les propriétés des objets de contact associés aux téléphones de zone commune, utilisez l’applet de passe **Set-CsCommonAreaPhone** . Les paramètres facultatifs pour **Set-CsCommonAreaPhone** vous permettent de modifier des éléments tels que le nom d’affichage Active Directory du contact ou l’URI (Uniform Resource Identifier) de ligne associé au téléphone, et d’activer et de désactiver le compte à utiliser avec Lync Server. Pour plus d’informations sur les modifications que vous pouvez apporter, voir la section paramètres de [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Pour plus d’informations sur les paramètres de **New-CsCommonAreaPhone** , voir [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Vous pouvez exécuter ces deux applets de commande à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Création d’un objet de contact pour les téléphones communs

  - Pour créer un objet de contact de téléphone de zone commune, utilisez l’applet **de nouvelle applet de nouveau-CsCommonAreaPhone** . Au minimum, vous devez fournir les informations suivantes lors de la création d’un objet de contact :
    
      - **LineURI**: numéro de téléphone attribué au numéro de téléphone de la zone commune. Notez que vous devez utiliser le format E. 164 lorsque vous spécifiez le numéro de téléphone.
    
      - **RegistrarPool**: nom de domaine complet (FQDN) du pool d’inscriptions qui hébergera l’objet contact.
    
      - **UO**: nom unique du conteneur Active Directory où l’objet de contact est créé.
    
    Nous vous recommandons également de fournir un nom complet des services de domaine Active Directory. Dans le cas contraire, vous devrez utiliser un GUID pour spécifier l’identité du téléphone. Par exemple :
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modification d’un objet de contact pour les téléphones communs

  - Pour modifier les propriétés d’un numéro de téléphone commun existant, vous pouvez utiliser l’applet de cmdlet **Set-CsCommonAreaPhone** . Par exemple, cette commande configure l’adresse SIP pour le numéro de téléphone commun avec le champ DisplayName lobby :
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Pour plus d’informations, consultez les rubriques d’aide pour la cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) et l’applet de connexion [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

