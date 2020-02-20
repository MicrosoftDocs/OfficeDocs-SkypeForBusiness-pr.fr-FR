---
title: 'Lync Server 2013 : création ou modification d’un objet contact de téléphone de partie commune'
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
ms.openlocfilehash: 699fd4413e071a9377369a383c9fd379a3451c6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>Création ou modification d’un objet contact de téléphone de partie commune dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Pour créer des objets contact des services de domaine Active Directory pour tous vos téléphones de partie commune, utilisez la cmdlet **New-CsCommonAreaPhone** . Cette applet de commande peut créer des objets contact à utiliser avec des téléphones de partie commune ou associer des objets contact existants à un nouveau téléphone de partie commune. Pour modifier les propriétés des objets contact associés à des téléphones de partie commune, utilisez la cmdlet **Set-CsCommonAreaPhone** . Les paramètres facultatifs de **Set-CsCommonAreaPhone** vous permettent de modifier des éléments, tels que le nom d’affichage du contact Active Directory ou l’URI (Uniform Resource Identifier) de ligne associé au téléphone, ainsi que d’activer et de désactiver le compte à utiliser avec Lync Server. Pour plus d’informations sur toutes les modifications disponibles, reportez-vous à la section Parameters de [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone). Pour plus d’informations sur les paramètres **New-CsCommonAreaPhone** , voir [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).

Vous pouvez exécuter ces deux cmdlets à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>Création d’un objet contact de téléphone de partie commune

  - Pour créer un objet contact de téléphone de partie commune, utilisez la cmdlet **New-CsCommonAreaPhone** . Au minimum, vous devez fournir les informations suivantes lors de la création d’un objet contact :
    
      - **LineURI**: numéro de téléphone attribué au téléphone de partie commune. Notez que vous devez utiliser le format E. 164 lorsque vous spécifiez le numéro de téléphone.
    
      - **RegistrarPool**: nom de domaine complet (FQDN) du pool de serveurs d’inscriptions qui hébergera l’objet contact.
    
      - **Ou**: nom unique du conteneur Active Directory dans lequel l’objet contact sera créé.
    
    Nous vous recommandons également de fournir un nom complet des services de domaine Active Directory. Dans le cas contraire, vous devrez utiliser un GUID pour spécifier l’identité de téléphone. Par exemple :
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>Modification d’un objet contact de téléphone de partie commune

  - Pour modifier les propriétés d’un téléphone de partie commune existant, l’objet contact utilise la cmdlet **Set-CsCommonAreaPhone** . Par exemple, cette commande configure l’adresse SIP pour le téléphone de partie commune avec la salle d’attente DisplayName :
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) et la cmdlet [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

