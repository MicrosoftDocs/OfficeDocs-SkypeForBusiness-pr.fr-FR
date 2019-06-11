---
title: 'Lync Server 2013 : protection des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a>Protection des services Internet (IIS) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-12-05_

Dans Microsoft Office Communications Server 2007 et Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) s’exécutait sous un compte d’utilisateur standard. Cela pouvait entraîner un problème: si ce mot de passe est arrivé à expiration, il est possible que vous deviez nous faire perdre vos services Web. Pour vous aider à éviter le problème d’expiration des mots de passe, Microsoft Lync Server 2013 vous permet de créer un compte d’ordinateur (pour un ordinateur qui n’existe pas réellement) qui peut faire office d’identité d’authentification pour tous les ordinateurs d’un site exécutant IIS. Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont désignés sous le nom de comptes Kerberos et le nouveau processus d’authentification est connu sous le nom d’authentification Web Kerberos. Cela vous permet de gérer tous vos serveurs IIS en utilisant un seul compte.

Pour exécuter vos serveurs sous ce principal d’authentification, vous devez d’abord créer un compte d’ordinateur à l’aide de l’applet de nouvelle cmdlet New-CsKerberosAccount. ce compte est ensuite affecté à un ou plusieurs sites. Après avoir effectué l’affectation, l’association entre le compte et le site 2013 de Lync Server est activée en exécutant l’applet de la cmdlet Enable-CsTopology. Entre autres choses, cela crée le nom de principal de service (SPN) requis dans les services de domaine Active Directory (AD DS). Les noms SPN permettent aux applications clientes de localiser un service. Pour plus d’informations, reportez-vous à la rubrique [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) dans la documentation des opérations.

<div>

## <a name="best-practices"></a>Meilleures pratiques

Pour renforcer la sécurité d’IIS, nous vous recommandons de mettre en œuvre un compte Kerberos pour les services Internet (IIS). Si vous n’avez pas implémenté de compte Kerberos, IIS s’exécute sous un compte d’utilisateur standard.

</div>

</div>

<span> </span>

</div>

</div>

</div>

