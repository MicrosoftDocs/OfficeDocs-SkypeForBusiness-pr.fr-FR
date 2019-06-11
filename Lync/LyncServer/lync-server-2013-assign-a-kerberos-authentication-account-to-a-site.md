---
title: 'Lync Server 2013 : Attribution d’un compte d’authentification Kerberos sur un site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c706f9fdd8932456a9f1617e55dc9231dbd6a84
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Attribution d’un compte d’authentification Kerberos sur un site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2017-04-18_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Après avoir créé le compte Kerberos, vous devez l’attribuer à un site. Il s’agit d’un site Lync Server 2013, et non d’un site Active Directory. Vous pouvez créer plusieurs comptes d’authentification Kerberos par déploiement, mais vous ne pouvez attribuer qu’un seul compte à un site. Utilisez la procédure suivante pour affecter un compte d’authentification Kerberos précédemment créé à un site. Pour plus d’informations sur la création du compte Kerberos, voir [créer un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Pour attribuer un compte d’authentification Kerberos à un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez les deux commandes suivantes:
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```
        Enable-CsTopology
       ```
    
    Par exemple :
    
       ```
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Vous devez spécifier le paramètre UserAccount en utilisant le format domaine\utilisateur. Le format user @ domain. extension n’est pas pris en charge pour référencer les objets ordinateur créés à des fins d’authentification Kerberos.

    
    </div>

4.  **Facultatif**: il est possible que vous ayez configuré un nom de domaine complet (FQDN) de remplacement pour vos services Web, en fonction [du changement d’URL des services Web dans Lync Server 2013](lync-server-2013-change-the-web-services-url.md). Si tel est le cas, vous devez ajouter un SPN pour ce nom de domaine complet. Par exemple, si le nom de domaine complet était WebServices. contoso. local, vous exécuterez:
    
        setspn -S http/webservices.contoso.local kerbauth

5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Après avoir apporté des modifications à l’authentification Kerberos (par exemple, ajout d’un compte ou suppression d’un compte), vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes de Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

