---
title: 'Lync Server 2013 : suppression de l’authentification Kerberos d’un site'
description: 'Lync Server 2013 : supprimez l’authentification Kerberos d’un site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3d9100d07d37e98800cfce106bc75fcfaeaa59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553530"
---
# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a>Dans Lync Server 2013, supprimez l’authentification Kerberos d’un site.

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Si vous devez supprimer l’authentification Kerberos d’un site ou supprimer un site, vous devez supprimer l’affectation du compte d’authentification Kerberos du site à l’aide de l’applet de commande **Remove-CsKerberosAccountAssignment**. Utilisez la procédure suivante pour supprimer l’affectation du compte d’authentification Kerberos, ce qui a pour effet de supprimer l’affectation de tous les ordinateurs présents sur le site.

<div class=" ">


> [!WARNING]  
> Si vous supprimez définitivement le compte Kerberos, utilisez utilisateurs et ordinateurs Active Directory pour le supprimer des services de domaine Active Directory après avoir supprimé l’attribution. Si vous envisagez d’utiliser l’objet ultérieurement, vous pouvez peut-être conserver l’objet Active Directory.



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a>Pour supprimer l’authentification Kerberos d’un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    Par exemple :
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

