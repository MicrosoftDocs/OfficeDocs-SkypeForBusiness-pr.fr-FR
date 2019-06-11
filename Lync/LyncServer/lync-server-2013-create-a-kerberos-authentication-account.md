---
title: 'Lync Server 2013 : Création d’un compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a>Création d’un compte d’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-01-02_

Pour effectuer cette procédure, vous devez être connecté au serveur ou au domaine au minimum en tant que membre du groupe Domain Admins.

Vous pouvez créer des comptes d’authentification Kerberos pour chaque site, ou vous pouvez créer un compte d’authentification Kerberos unique et l’utiliser pour tous les sites. Les applets de cmdlet Windows PowerShell vous permettent de créer et de gérer les comptes, y compris l’identification des comptes attribués à chaque site. Le générateur de topologie et le panneau de configuration de Lync Server 2013 n’affichent pas de comptes d’authentification Kerberos. Utilisez la procédure suivante pour créer un ou plusieurs comptes d’utilisateur à utiliser pour l’authentification Kerberos.

<div>

## <a name="to-create-a-kerberos-account"></a>Pour créer un compte Kerberos

1.  En tant que membre du groupe Domain Admins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante:
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    Par exemple :
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  Vérifiez que l’objet ordinateur a été créé en ouvrant utilisateurs et ordinateurs Active Directory, développez le conteneur **utilisateurs** , puis vérifiez que l’objet ordinateur du compte d’utilisateur est dans le conteneur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

