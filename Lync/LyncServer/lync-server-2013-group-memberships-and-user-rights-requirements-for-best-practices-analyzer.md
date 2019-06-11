---
title: Exigences en matière d’appartenance aux groupes et de droits d’utilisateur pour les meilleures pratiques Analyzer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Exigences en matière d’appartenance aux groupes et de droits d’utilisateur pour les meilleurs analyseurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-21_

Pour exécuter correctement le BPA, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local. De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants:

  - **Administrateurs de domaine**   pour énumérer les informations sur les services de domaine Active Directory et pour appeler les fournisseurs WMI sur les contrôleurs de domaine et les serveurs de catalogue global.

  - **Les administrateurs**   sont requis sur chaque ordinateur interne Lync Server 2013 et chaque serveur Edge pour appeler les fournisseurs WMI (Windows Management Instrumentation) et accéder au registre.

  - **RTCUniversalReadOnlyAdmins**   complets ou délégués en lecture seule les droits d’administration de Lync Server 2013.

  - **Administrateur Exchange afficher uniquement**   ou administrateur Exchange Affichage seul ou délégué dans l’organisation Microsoft Exchange.

Si votre compte d’utilisateur ne dispose pas des droits d’utilisateur suffisants, vous avez deux possibilités:

  - À l’invite de commandes, utilisez la commande **runas** pour exécuter l’outil sous un compte disposant de droits d’utilisateur suffisants. La syntaxe est la suivante:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Dans la page **se connecter à Active Directory** , définissez les informations d’identification des comptes que vous envisagez d’utiliser pour exécuter les meilleurs analyseurs. Cliquez sur **afficher les options de connexion avancées**. Vous pouvez entrer trois comptes: un pour la connexion aux services de domaine Active Directory (AD FS), un pour la connexion aux serveurs Edge Lync Server 2013 et un pour la connexion aux serveurs Exchange. Si vous ne spécifiez aucun de ces comptes, le compte d’utilisateur que vous avez utilisé pour vous connecter et exécuter l’analyseur de meilleures pratiques est utilisé.

</div>

<span> </span>

</div>

</div>

</div>

