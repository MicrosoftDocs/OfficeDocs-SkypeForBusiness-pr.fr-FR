---
title: Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer
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
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Pour exécuter Best Practices Analyzer correctement, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local. De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants :

  - **Administrateurs de domaine**   pour énumérer les informations des services de domaine Active Directory et appeler les fournisseurs WMI (Windows Management Instrumentation) sur les contrôleurs de domaine et les serveurs de catalogue global.

  - **Administrateurs**   requis sur chaque ordinateur interne Lync Server 2013 et chaque serveur Edge pour appeler les fournisseurs WMI (Windows Management Instrumentation) et accéder au registre.

  - ****   Droits d’administration RTCUniversalReadOnlyAdmins complets ou délégués en lecture seule de Lync Server 2013.

  - **Administrateur Exchange Affichage seul**   administrateur complet ou délégué Exchange Affichage seul de l’organisation Microsoft Exchange.

Si votre compte d’utilisateur ne dispose pas des droits utilisateur suffisants, deux options s’offrent à vous :

  - À l’invite de commande, utilisez la commande **runas** pour exécuter l’outil sous un compte doté des droits utilisateur suffisants. La syntaxe est la suivante :
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Sur la page **Connexion à Active Directory**, définissez les informations d’identification des comptes que vous prévoyez d’utiliser pour exécuter Best Practices Analyzer. Cliquez sur **Afficher les options de connexion avancées**. Vous pouvez entrer trois comptes : un pour la connexion aux services de domaine Active Directory, un pour la connexion aux serveurs Edge Lync Server 2013 et un pour la connexion aux serveurs Exchange. Si vous ne spécifiez aucun de ces comptes, le compte utilisateur servant à la connexion et l’exécution de Best Practices Analyzer est utilisé.

</div>

<span> </span>

</div>

</div>

</div>

