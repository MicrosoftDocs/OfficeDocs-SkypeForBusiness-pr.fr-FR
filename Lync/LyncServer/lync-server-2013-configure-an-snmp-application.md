---
title: 'Lync Server 2013 : configurer une application SNMP'
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
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a>Configurer une application SNMP dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Lync Server 2013 inclut une interface de service Web standard que vous pouvez utiliser pour connecter le service d’informations d’emplacement aux applications SNMP (simple Network Management Protocol) qui correspondent aux adresses MAC et aux informations sur les ports et aux commutateurs.

Si une application SNMP est installée et que le service des informations de géolocalisation ne trouve pas de correspondance dans la base de données de localisation, le service d’information d’emplacement interroge automatiquement l’application à l’aide de l’adresse MAC fournie par le client. Le service d’information d’emplacement utilise alors le port et les informations de commutation renvoyées par l’application SNMP pour interroger de nouveau la base de données d’emplacement.

Pour plus d’informations, consultez la rubrique [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).

<div>


> [!NOTE]  
> Les adresses MAC ne sont pas disponibles sur les ordinateurs exécutant Windows 8.



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a>Pour configurer l’URL de l’application SNMP

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de commande suivante pour configurer l’URL de l’application SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

