---
title: 'Lync Server 2013 : configuration des mots de passe de compte d’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21ed9f0b5bd8e9aecfb39a7dd9c159857d4b240e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a>Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2010-11-03_

Après avoir créé l’objet ordinateur pour le compte d’authentification Kerberos, vous pouvez configurer le mot de passe pour le compte. Vous exécutez l’applet de commande Windows PowerShell pour définir le mot de passe du compte Kerberos sur un serveur. Vous pouvez définir le mot de passe sur l’objet créé pour l’authentification Kerberos. Le mot de passe peut être défini sur une valeur connue, mais par défaut il s’agit d’un mot de passe aléatoire. Il est valable pour toutes les sources d’authentification Kerberos qui utilisent le compte. Vous utilisez les applets de commande Windows PowerShell pour configurer et gérer les mots de passe de compte Kerberos.

<div>


> [!NOTE]  
> L’objet de compte Kerberos est un objet ordinateur, mais il utilise le paramètre UserAccount pour les opérations des applets de commande Windows PowerShell référencées. Notez qu’il ne s’agit pas d’une erreur, mais du comportement prévu de l’applet de commande lorsqu’elle est utilisée pour la création et la maintenance du compte Kerberos.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Définir un mot de passe de compte d’authentification Kerberos sur un serveur dans Lync Server 2013](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [Synchronisation d’un mot de passe de compte d’authentification Kerberos avec les services Internet (IIS) dans Lync Server 2013](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

