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

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="97431-102">Exigences en matière d’appartenance aux groupes et de droits d’utilisateur pour les meilleurs analyseurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97431-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97431-103">_**Dernière modification de la rubrique:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="97431-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="97431-104">Pour exécuter correctement le BPA, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="97431-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="97431-105">De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants:</span><span class="sxs-lookup"><span data-stu-id="97431-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="97431-106">**Administrateurs de domaine**   pour énumérer les informations sur les services de domaine Active Directory et pour appeler les fournisseurs WMI sur les contrôleurs de domaine et les serveurs de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="97431-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="97431-107">**Les administrateurs**   sont requis sur chaque ordinateur interne Lync Server 2013 et chaque serveur Edge pour appeler les fournisseurs WMI (Windows Management Instrumentation) et accéder au registre.</span><span class="sxs-lookup"><span data-stu-id="97431-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="97431-108">**RTCUniversalReadOnlyAdmins**   complets ou délégués en lecture seule les droits d’administration de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97431-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="97431-109">**Administrateur Exchange afficher uniquement**   ou administrateur Exchange Affichage seul ou délégué dans l’organisation Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="97431-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="97431-110">Si votre compte d’utilisateur ne dispose pas des droits d’utilisateur suffisants, vous avez deux possibilités:</span><span class="sxs-lookup"><span data-stu-id="97431-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="97431-111">À l’invite de commandes, utilisez la commande **runas** pour exécuter l’outil sous un compte disposant de droits d’utilisateur suffisants.</span><span class="sxs-lookup"><span data-stu-id="97431-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="97431-112">La syntaxe est la suivante:</span><span class="sxs-lookup"><span data-stu-id="97431-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="97431-113">Dans la page **se connecter à Active Directory** , définissez les informations d’identification des comptes que vous envisagez d’utiliser pour exécuter les meilleurs analyseurs.</span><span class="sxs-lookup"><span data-stu-id="97431-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="97431-114">Cliquez sur **afficher les options de connexion avancées**.</span><span class="sxs-lookup"><span data-stu-id="97431-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="97431-115">Vous pouvez entrer trois comptes: un pour la connexion aux services de domaine Active Directory (AD FS), un pour la connexion aux serveurs Edge Lync Server 2013 et un pour la connexion aux serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="97431-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="97431-116">Si vous ne spécifiez aucun de ces comptes, le compte d’utilisateur que vous avez utilisé pour vous connecter et exécuter l’analyseur de meilleures pratiques est utilisé.</span><span class="sxs-lookup"><span data-stu-id="97431-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

