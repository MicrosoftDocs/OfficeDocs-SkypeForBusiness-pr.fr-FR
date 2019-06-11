---
title: 'Lync Server 2013 : Configuration de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86526b40ee837866cdf0e3b016a8e4e627ca2eef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a>Configuration de l’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Lync Server 2013 prend en charge l’authentification NTLM et Kerberos pour les services Web. Office Communications Server 2007 et Office Communications Server 2007 R2 utilisait le RTCComponentService et RTCService par défaut en tant que comptes d’utilisateurs pour exécuter les pools d’applications de services Web, permettant ainsi à l’utilisateur d’utiliser un nom de principal de service (SPN). comptes et agissant en tant que principal d’authentification. Lync Server utilise NetworkService pour exécuter les services Web et NetworkService ne peut pas avoir de SPN qui lui est affecté.

Pour résoudre le problème que vous n’avez pas d’objets Active Directory devant contenir les noms d’application (SPN), le panneau de configuration de Lync Server peut utiliser les objets de compte d’ordinateur. Les objets de compte d’ordinateur peuvent contenir les SPN et ne sont pas soumis à l’expiration du mot de passe, ce qui fut un problème lors de l’utilisation de comptes d’utilisateur dans les versions précédentes.

Les applets de cmdlet Windows PowerShell vous permettent de configurer les objets ordinateur pour fournir une authentification Kerberos.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Conditions prérequises à l’activation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Création d’un compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Attribution d’un compte d’authentification Kerberos sur un site dans Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Ajout d’une authentification Kerberos à d’autres sites dans Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Suppression de l’authentification Kerberos d’un site dans Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Test et création de rapports sur l’état et l’affectation de l’authentification Kerberos dans Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

