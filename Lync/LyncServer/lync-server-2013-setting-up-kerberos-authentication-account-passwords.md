---
title: 'Lync Server 2013 : Configuration des mots de passe de compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06ca8bf5d1b3dc90b1ceacbe581e0426b5c0aaa9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2010-11-03_

Une fois que vous avez créé l’objet ordinateur pour le compte d’authentification Kerberos, vous pouvez configurer le mot de passe du compte. Vous exécutez l’applet de cmdlet Windows PowerShell pour configurer le mot de passe du compte Kerberos sur un serveur. Vous pouvez définir le mot de passe sur l’objet que vous avez créé pour l’authentification Kerberos. Le mot de passe peut être défini sur une valeur connue, mais par défaut comme un mot de passe aléatoire. Le mot de passe est disponible pour toutes les sources d’authentification Kerberos qui utilisent le compte. Les applets de cmdlet Windows PowerShell permettent de configurer et de gérer les mots de passe des comptes Kerberos.

<div>


> [!NOTE]  
> L’objet de compte Kerberos est un objet ordinateur, mais il utilise le paramètre UserAccount pour les opérations dans les cmdlets Windows PowerShell qui sont référencées. Notez qu’il ne s’agit pas d’une erreur, mais du comportement prévu de l’applet de passe lorsqu’elle est utilisée avec la création et la maintenance du compte Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définition d’un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

