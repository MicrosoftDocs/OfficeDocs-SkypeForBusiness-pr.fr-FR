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
ms.openlocfilehash: 2245cbbe32e8751948f32dc83dae7ca58f92091f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="8c6cd-102">Appartenances aux groupes et exigences relatives aux droits des utilisateurs pour Best Practices Analyzer dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c6cd-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c6cd-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8c6cd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8c6cd-p101">Pour exécuter Best Practices Analyzer correctement, le compte d’utilisateur que vous utilisez pour vous connecter doit être membre du groupe Administrateurs sur l’ordinateur local. De plus, pour analyser votre environnement, le compte d’utilisateur doit être membre des groupes suivants :</span><span class="sxs-lookup"><span data-stu-id="8c6cd-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="8c6cd-106">**Administrateurs de domaine**   pour énumérer les informations des services de domaine Active Directory et appeler les fournisseurs WMI (Windows Management Instrumentation) sur les contrôleurs de domaine et les serveurs de catalogue global.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="8c6cd-107">**Administrateurs**   requis sur chaque ordinateur interne Lync Server 2013 et chaque serveur Edge pour appeler les fournisseurs WMI (Windows Management Instrumentation) et accéder au registre.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="8c6cd-108">\*\*\*\*   Droits d’administration RTCUniversalReadOnlyAdmins complets ou délégués en lecture seule de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="8c6cd-109">**Administrateur Exchange Affichage seul**   administrateur complet ou délégué Exchange Affichage seul de l’organisation Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="8c6cd-110">Si votre compte d’utilisateur ne dispose pas des droits utilisateur suffisants, deux options s’offrent à vous :</span><span class="sxs-lookup"><span data-stu-id="8c6cd-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="8c6cd-111">À l’invite de commande, utilisez la commande **runas** pour exécuter l’outil sous un compte doté des droits utilisateur suffisants.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="8c6cd-112">La syntaxe est la suivante :</span><span class="sxs-lookup"><span data-stu-id="8c6cd-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="8c6cd-113">Sur la page **Connexion à Active Directory**, définissez les informations d’identification des comptes que vous prévoyez d’utiliser pour exécuter Best Practices Analyzer.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="8c6cd-114">Cliquez sur **Afficher les options de connexion avancées**.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="8c6cd-115">Vous pouvez entrer trois comptes : un pour la connexion aux services de domaine Active Directory, un pour la connexion aux serveurs Edge Lync Server 2013 et un pour la connexion aux serveurs Exchange.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="8c6cd-116">Si vous ne spécifiez aucun de ces comptes, le compte utilisateur servant à la connexion et l’exécution de Best Practices Analyzer est utilisé.</span><span class="sxs-lookup"><span data-stu-id="8c6cd-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

