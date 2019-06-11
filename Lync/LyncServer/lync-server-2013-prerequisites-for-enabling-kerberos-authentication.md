---
title: 'Lync Server 2013 : Conditions prérequises à l’activation de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Conditions prérequises à l’activation de l’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-21_

Avant d’activer l’authentification Kerberos, assurez-vous d’avoir effectué toutes les préparations de configuration et d’infrastructure prérequises:

  - Le schéma Active Directory est étendu pour Lync Server 2013.

  - La préparation de la forêt Active Directory est terminée pour Lync Server 2013.

  - La préparation du domaine Active Directory est terminée pour Lync Server 2013.

  - Le centre de gestion central est correctement installé et disponible.

  - Le module topologique a été créé et publié à l’aide du générateur de topologie.

  - Les serveurs et rôles nécessitant la définition et le déploiement de services Web, notamment les serveurs front end, les serveurs Standard Edition et les directeurs.

  - Internet Information Services (IIS) est configuré et déployé avec les services de rôle recommandés pour prendre en charge les services Web dans Lync Server 2013.

Lorsque les conditions préalables sont remplies, vous devez être prêt à créer un ou plusieurs comptes pour les services Web à utiliser pour l’authentification Kerberos pour votre déploiement. Au minimum, vous devez créer un compte d’authentification Kerberos pour chaque déploiement. Toutefois, vous pouvez créer un compte pour chaque site afin de fournir une authentification Kerberos locale sur le site. Vous ne pouvez spécifier qu’un seul compte d’authentification Kerberos par site.

</div>

<span> </span>

</div>

</div>

</div>

