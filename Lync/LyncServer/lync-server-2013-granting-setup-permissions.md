---
title: 'Lync Server 2013 : octroi d’autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f557fdda658650fd2cb3dd5a4a080600be023ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498861"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a>Octroi d’autorisations de configuration dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-08-27_

L’applet de commande **Grant-CsSetupPermission** vous permet d’ajouter des autorisations Read, Write, ReadSPN et WriteSPN au groupe RTCUniversalServerAdmins d’une unité d’organisation (UO) Active Directory spécifiée. Les membres du groupe RTCUniversalServerAdmins de cette unité d’organisation peuvent alors installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs du domaine.

L’applet de commande **Test-CsSetupPermission** vous permet de vérifier les autorisations que vous avez configurées à l’aide de l’applet de commande **Grant-CsSetupPermission**.

L’applet de commande **Revoke-CsSetupPermission** vous permet de supprimer les autorisations que vous avez accordées à l’aide de l’applet de commande **Grant-CsSetupPermission**.

<div>

## <a name="to-grant-setup-permissions"></a>Pour accorder des autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez accorder des autorisations de configuration. Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Pour vérifier les autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez vérifier les autorisations d’installation que vous avez accordées à l’aide de la cmdlet **Grant-CsSetupPermission** . Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Pour révoquer des autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine où vous souhaitez révoquer les autorisations d’installation accordées par la cmdlet **Grant-CsSetupPermission** . Utilisez un compte membre du groupe Administrateurs du domaine ou du groupe Administrateurs d’entreprise si l’unité d’organisation (UO) est dans un autre domaine enfant.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu selon le contexte d’appellation par défaut du domaine spécifié (par exemple, CN=ordinateurs). Vous pouvez également spécifier ce paramètre comme nom unique complet (DN) de l’unité d’organisation (par exemple, « CN=ordinateurs,DC=Contoso,DC=com »). Dans le dernier cas, vous devez spécifier un DN d’unité d’organisation (UO) qui correspond au domaine que vous spécifiez.
    
    Si vous omettez le paramètre Domain, le domaine local est utilisé par défaut.

</div>

</div>

<span> </span>

</div>

</div>

</div>

