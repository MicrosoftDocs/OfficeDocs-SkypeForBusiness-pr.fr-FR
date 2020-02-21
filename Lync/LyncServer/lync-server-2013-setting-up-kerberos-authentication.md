---
title: 'Lync Server 2013 : configuration de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f2c781b01aaa1ac00793f97067f24233c1e8db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configuration de l’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Lync Server 2013 prend en charge l’authentification NTLM et l’authentification Kerberos pour les services Web. Office Communications Server 2007 et Office Communications Server 2007 R2 utilisaient le RTCComponentService et le RTCService par défaut comme comptes d’utilisateur pour exécuter les pools d’applications des services Web, ce qui permet d’attribuer un nom de principal du service (SPN) à l’utilisateur Accounts et agir en tant que principal d’authentification. Lync Server utilise NetworkService pour exécuter les services Web et NetworkService ne peut pas avoir de noms principaux de service.

Pour résoudre le problème de non-utilisation d’objets Active Directory pour conserver les SPN, le panneau de configuration Lync Server peut utiliser des objets de compte d’ordinateur à cet effet. Les objets de compte d’ordinateur peuvent contenir les noms principaux de domaine et ne font pas l’objet d’une expiration de mot de passe, ce qui était un problème lors de l’utilisation de comptes d’utilisateur dans les versions précédentes.

Vous utilisez les applets de commande Windows PowerShell pour configurer les objets ordinateur afin de fournir l’authentification Kerberos.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Conditions préalables à l’activation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Créer un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Affecter un compte d’authentification Kerberos à un site dans Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Dans Lync Server 2013, ajoutez l’authentification Kerberos à d’autres sites](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Dans Lync Server 2013, supprimez l’authentification Kerberos d’un site.](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Test et création de rapports sur l’État et l’affectation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

