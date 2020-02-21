---
title: 'Lync Server 2013 : configuration d’une application SNMP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252b6ec99d19b88259aacc2fc5681b585ae1bef2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205290"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurer une application SNMP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync Server 2013 inclut une interface de service Web standard que vous pouvez utiliser pour connecter le service informations d’emplacement aux applications SNMP (simple Network Management Protocol) qui correspondent à des adresses MAC avec des informations sur les ports et les commutateurs.

Si une application SNMP est installée et que le service d’informations d’emplacement ne parvient pas à trouver une correspondance dans la base de données d’emplacements, le service d’informations d’emplacement interroge automatiquement l’application en utilisant l’adresse MAC fournie par le client. Le service d’informations d’emplacement utilise ensuite le port et les informations de commutateur renvoyées par l’application SNMP pour interroger à nouveau la base de données d’emplacements.

Pour plus d’informations, consultez la rubrique [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

