---
title: 'Lync Server 2013 : Préparation des services de domaine Active Directory verrouillés'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 482c5a59c6dc53fc712db7e77430367dd9c37af5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-05-14_

Les organisations verrouillent souvent les services de domaine Active Directory pour réduire les risques liés à la sécurité. Toutefois, un environnement Active Directory verrouillé peut limiter les autorisations requises par Lync Server 2013. La préparation correcte d’un environnement Active Directory verrouillé pour Lync Server 2013 implique quelques considérations et étapes supplémentaires.

Il existe deux méthodes courantes pour lesquelles les autorisations sont limitées dans un environnement Active Directory verrouillé:

  - Les entrées de contrôle d’accès des utilisateurs authentifiées (ACE) sont supprimées des conteneurs.

  - L’héritage des autorisations est désactivé sur les conteneurs d’objets utilisateur, de contact, de InetOrgPerson ou d’ordinateur.

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Suppression des autorisations d’utilisateur authentifié dans Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [Désactivation de l’héritage des autorisations sur les conteneurs des objets Ordinateur, Utilisateur ou InetOrgPerson dans Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

