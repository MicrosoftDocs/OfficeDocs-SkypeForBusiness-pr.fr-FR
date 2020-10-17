---
title: Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer
description: Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564190"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Pour exécuter Best Practices Analyzer correctement, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local. De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants :

  - **Administrateurs**     de domaine Pour énumérer les informations des services de domaine Active Directory et appeler les fournisseurs WMI (Windows Management Instrumentation) sur les contrôleurs de domaine et les serveurs de catalogue global.

  - **Administrateurs**     Obligatoire sur chaque ordinateur interne Lync Server 2013 et chaque serveur Edge pour appeler les fournisseurs WMI (Windows Management Instrumentation) et accéder au registre.

  - **RTCUniversalReadOnlyAdmins**     Droits d’administration complets ou délégués en lecture seule de Lync Server 2013.

  - Administrateur Exchange affichage **seul**     Administrateur complet ou délégué Exchange Affichage seul de l’organisation Microsoft Exchange.

Si votre compte d’utilisateur ne dispose pas des droits utilisateur suffisants, deux options s’offrent à vous :

  - À l’invite de commande, utilisez la commande **runas** pour exécuter l’outil sous un compte doté des droits utilisateur suffisants. La syntaxe est la suivante :
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Sur la page **Connexion à Active Directory**, définissez les informations d’identification des comptes que vous prévoyez d’utiliser pour exécuter Best Practices Analyzer. Cliquez sur **Afficher les options de connexion avancées**. Vous pouvez entrer trois comptes : un pour la connexion aux services de domaine Active Directory, un pour la connexion aux serveurs Edge Lync Server 2013 et un pour la connexion aux serveurs Exchange. Si vous ne spécifiez aucun de ces comptes, le compte utilisateur servant à la connexion et l’exécution de Best Practices Analyzer est utilisé.

</div>

<span> </span>

</div>

</div>

</div>

