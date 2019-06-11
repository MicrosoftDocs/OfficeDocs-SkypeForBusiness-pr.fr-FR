---
title: 'Lync Server 2013 : Octroi d’autorisations de configuration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a>Octroi d’autorisations de configuration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-08-27_

Vous pouvez utiliser l’applet de contrôle **Grant-CsSetupPermission** pour ajouter des autorisations de lecture, d’écriture, de ReadSPN et de WriteSPN au groupe RTCUniversalServerAdmins de l’unité d’organisation Active Directory spécifiée. Les membres du groupe RTCUniversalServerAdmins dans cette UO peuvent installer des serveurs exécutant Lync Server 2013 dans le domaine spécifié sans être membres du groupe administrateurs de domaine.

Utilisez l’applet de **contrôle test-CsSetupPermission** pour vérifier les autorisations que vous avez configurées à l’aide de l’applet de contrôle **Grant-CsSetupPermission** .

Vous pouvez utiliser l’applet de passe **Revoke-CsSetupPermission** pour supprimer les autorisations accordées à l’aide de l’applet de passe **Grant-CsSetupPermission** .

<div>

## <a name="to-grant-setup-permissions"></a>Pour accorder des autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine auquel vous voulez accorder des autorisations de configuration. Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs). Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»). Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.

</div>

<div>

## <a name="to-verify-setup-permissions"></a>Pour vérifier les autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez vérifier les autorisations de configuration que vous avez accordées à l’aide de l’applet de contrôle **Grant-CsSetupPermission** . Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs). Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»). Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.

</div>

<div>

## <a name="to-revoke-setup-permissions"></a>Pour révoquer les autorisations de configuration

1.  Ouvrez une session sur un ordinateur exécutant Lync Server 2013 dans le domaine dans lequel vous voulez révoquer les autorisations de configuration accordées par l’applet de connexion **Grant-CsSetupPermission** . Utilisez un compte membre du groupe administrateurs de domaine ou administrateurs d’entreprise si l’unité d’organisation se trouve dans un domaine enfant différent.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    Vous pouvez spécifier le paramètre ComputerOu en fonction du contexte de nommage par défaut du domaine spécifié (par exemple, CN = ordinateurs). Vous pouvez également spécifier ce paramètre en tant que nom unique de l’unité de nom unique (DN) complet (par exemple, «CN = ordinateurs, DC = contoso, DC = com»). Dans ce dernier cas, vous devez spécifier un DN d’unité d’organisation qui est cohérent avec le domaine que vous spécifiez.
    
    Si vous ne spécifiez pas le paramètre domain, la valeur par défaut est le domaine local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

