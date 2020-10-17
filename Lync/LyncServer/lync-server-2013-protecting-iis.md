---
title: 'Lync Server 2013 : protection des services Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aae84d208df1d7c2945fee641b243bf7110902c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513191"
---
# <a name="protecting-iis-in-lync-server-2013"></a>Protection des services Internet (IIS) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-12-05_

Dans Microsoft Office Communications Server 2007 et Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) s’est exécuté sous un compte d’utilisateur standard. Cela était susceptible de provoquer des problèmes : si ce mot de passe a expiré, vous pouviez perdre vos services Web, un problème souvent difficile à diagnostiquer. Pour éviter le problème d’expiration des mots de passe, Microsoft Lync Server 2013 vous permet de créer un compte d’ordinateur (pour un ordinateur qui n’existe pas réellement) qui peut servir de principal d’authentification pour tous les ordinateurs d’un site qui exécutent les services Internet (IIS). Étant donné que ces comptes utilisent le protocole d’authentification Kerberos, les comptes sont appelés comptes Kerberos et le nouveau processus d’authentification est appelé authentification Web Kerberos. Cela vous permet de gérer tous vos serveurs IIS à l’aide d’un seul compte.

Pour pouvoir exécuter vos serveurs sous ce nom principal d’authentification, vous devez créer un compte d’ordinateur au moyen de l’applet de commande New-CsKerberosAccount, le compte étant ensuite affecté à un ou plusieurs sites. Une fois l’affectation effectuée, l’association entre le compte et le site Lync Server 2013 est activée en exécutant l’applet de commande Enable-CsTopology. Entre autres choses, cela crée le nom de principal du service (SPN) requis dans les services de domaine Active Directory (AD DS). Les noms SPN permettent aux applications clientes de localiser un service. Pour plus d’informations, consultez la rubrique [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) dans la documentation des opérations.

<div>

## <a name="best-practices"></a>Meilleures pratiques

Pour aider à améliorer la sécurité d’IIS, nous vous recommandons d’implémenter un compte Kerberos pour IIS. Si vous ne le faites pas, IIS est exécuté sous un compte utilisateur standard.

</div>

</div>

<span> </span>

</div>

</div>

</div>

