---
title: 'Lync Server 2013 : attribution d’un compte d’authentification Kerberos à un site'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a28efed0276fd1665746f55fdf2bdc14cef8e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a>Affecter un compte d’authentification Kerberos à un site dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-04-18_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Après avoir créé le compte Kerberos, vous devez l’assigner à un site. Il s’agit d’un site Lync Server 2013 et non d’un site Active Directory. Vous pouvez créer plusieurs comptes d’authentification Kerberos par déploiement, mais vous ne pouvez assigner qu’un seul compte à un site. Pour assigner un compte d’authentification Kerberos existant à un site, procédez comme suit. Pour plus d’informations sur la création du compte Kerberos, voir [créer un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a>Pour assigne un compte d’authentification Kerberos à un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez les deux commandes suivantes :
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    Par exemple :
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Vous devez spécifier le paramètre Compte d’utilisateur au format Domaine\Utilisateur. Le format Utilisateur@Domaine.extension n’est pas pris en charge pour la référence aux objets créés à des fins d’authentification Kerberos.

    
    </div>

4.  **Facultatif**: vous avez peut-être configuré un nom de domaine complet (FQDN) de remplacement pour vos WebServices, en fonction de [la modification de l’URL des services Web dans Lync Server 2013](lync-server-2013-change-the-web-services-url.md). Si c’est le cas, vous devrez également ajouter un SPN pour ce nom de domaine complet. Par exemple, si le nom de domaine complet était WebServices. contoso. local, vous devez exécuter :
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > Après avoir apporté des modifications à l’authentification Kerberos, telles que l’ajout d’un compte ou la suppression d’un compte, vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

