---
title: 'Lync Server 2013 : conditions préalables pour l’activation de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dd399ef7a0ed2dd6609fe0455d9593e1e567b3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a>Conditions préalables à l’activation de l’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Avant d’activer l’authentification Kerberos, veillez à effectuer toutes les préparations de configuration et d’infrastructure prérequises :

  - Le schéma Active Directory est étendu pour Lync Server 2013.

  - La préparation de la forêt Active Directory est terminée pour Lync Server 2013.

  - La préparation du domaine Active Directory est terminée pour Lync Server 2013.

  - Le magasin central de gestion est correctement installé et disponible.

  - La topologie a été créée et publiée à l’aide du générateur de topologie.

  - Les serveurs et les rôles nécessitant des services Web ont été définis et déployés, y compris les serveurs frontaux, les serveurs Standard Edition et les directeurs.

  - Les services Internet (IIS) sont configurés et déployés avec les services de rôle recommandés pour prendre en charge les services Web dans Lync Server 2013.

Une fois que les conditions préalables sont remplies, vous devez être prêt à créer un ou plusieurs comptes pour les services Web à utiliser pour l’authentification Kerberos de votre déploiement. Vous devez créer au moins un compte d’authentification Kerberos pour chaque déploiement. Néanmoins, vous pouvez créer un compte pour chaque site, afin de permettre l’authentification Kerberos locale au niveau du site. Vous ne pouvez spécifier qu’un seul compte d’authentification Kerberos par site.

</div>

<span> </span>

</div>

</div>

</div>

