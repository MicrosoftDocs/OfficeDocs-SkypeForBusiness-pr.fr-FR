---
title: Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Synchronize a Kerberos authentication account password to IIS
ms:assetid: 05925a66-2684-4c1b-adfa-69bd0da1bf38
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398107(v=OCS.15)
ms:contentKeyID: 48183296
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86e71f87c20064e542aa6a8db1d9b38048c5f736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="synchronize-a-kerberos-authentication-account-password-to-iis-in-lync-server-2013"></a>Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2010-11-08_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Dans un site, des serveurs frontaux, des serveurs Standard Edition et des directeurs peuvent utiliser un compte d’authentification Kerberos dans le but d’authentifier les demandes envoyées au service de services Web. Cette procédure recherche sur chaque serveur exécutant des services Web dans un site qui a été affecté un compte Kerberos et met à jour les paramètres de configuration d’Internet Information Services (IIS) pour utiliser le compte Kerberos. Pour plus d’informations, consultez [définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md).

<div>

## <a name="to-set-and-configure-a-kerberos-authentication-account-password"></a>Pour définir et configurer un mot de passe de compte d’authentification Kerberos

1.  Connectez-vous à un ordinateur source (tel que fe01.contoso.com) en tant que membre du groupe RTCUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande Lync Server Management Shell, exécutez les deux commandes suivantes :
    
        Set-CsKerberosAccountPassword -FromComputer SourceComputer -ToComputer DestinationComputer
    
    Par exemple :
    
        Set-CsKerberosAccountPassword -FromComputer fe01.contoso.com -ToComputer dir01.contoso.com
    
    <div>
    

    > [!IMPORTANT]
    > Le nom de l’ordinateur source et de l’ordinateur de destination doit être un nom de domaine complet (FQDN) du serveur. Vous ne pouvez pas utiliser le nom de domaine complet (FQDN) du pool, sauf s’il est identique à celui de l’ordinateur que vous utilisez en tant qu’ordinateur source ou ordinateur de destination.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Après avoir apporté des modifications à l’authentification Kerberos (par exemple, ajout d’un compte ou suppression d’un compte), vous devez exécuter <STRONG>Enable-CsTopology</STRONG> à partir de l’invite de commandes de Lync Server Management Shell.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

