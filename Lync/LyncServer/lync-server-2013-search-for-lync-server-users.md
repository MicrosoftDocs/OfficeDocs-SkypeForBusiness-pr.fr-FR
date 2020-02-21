---
title: 'Lync Server 2013 : recherche d’utilisateurs Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Search for Lync Server users
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429701(v=OCS.15)
ms:contentKeyID: 48183871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f503736b22453f6c3aafd76bc2fac7211f11dec7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="search-for-lync-server-users-in-lync-server-2013"></a><span data-ttu-id="8105c-102">Rechercher des utilisateurs Lync Server dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8105c-102">Search for Lync Server users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8105c-103">_**Dernière modification de la rubrique :** 2014-05-14_</span><span class="sxs-lookup"><span data-stu-id="8105c-103">_**Topic Last Modified:** 2014-05-14_</span></span>

<span data-ttu-id="8105c-104">Vous pouvez utiliser les résultats d’une requête de recherche pour configurer des utilisateurs pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8105c-104">You can use the results of a search query to configure users for Lync Server 2013.</span></span> <span data-ttu-id="8105c-105">Vous pouvez rechercher des utilisateurs par nom d’affichage, prénom, nom de famille, nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), adresse SIP ou URI (Uniform Resource Identifier) de ligne.</span><span class="sxs-lookup"><span data-stu-id="8105c-105">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="8105c-106">Vous pouvez rechercher des utilisateurs à partir du Panneau de configuration Lync Server ou du composant Utilisateurs et ordinateurs Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8105c-106">You can search for users by using the Lync Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="8105c-107">La procédure suivante explique comment utiliser le panneau de configuration Lync Server pour rechercher des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8105c-107">The following procedure describes how to use Lync Server Control Panel to search for users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8105c-108">Dans un environnement avec une topologie de forêt centrale, les résultats de la recherche peuvent ne pas être précis lorsque vous recherchez un utilisateur à l’aide de son adresse de messagerie.</span><span class="sxs-lookup"><span data-stu-id="8105c-108">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user’s email address.</span></span> <span data-ttu-id="8105c-109">Au lieu de cela, vous pouvez rechercher des utilisateurs en spécifiant un préfixe d’adresse SIP, par exemple, SIP : nom, ajouter un filtre de recherche et sélectionner une adresse SIP qui contient une adresse de messagerie partielle ou utiliser la cmdlet <STRONG>Get-Csuser</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="8105c-109">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the <STRONG>Get-CSUser</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="8105c-110">Pour rechercher un ou plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="8105c-110">To search for one or more users</span></span>

1.  <span data-ttu-id="8105c-111">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="8105c-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8105c-112">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8105c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8105c-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8105c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8105c-114">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="8105c-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8105c-115">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8105c-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5.  <span data-ttu-id="8105c-116">(Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :</span><span class="sxs-lookup"><span data-stu-id="8105c-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="8105c-117">Cliquez sur la flèche déroulante située en haut à droite de l’écran, au-dessus **Résultats de la recherche**, puis sur **Ajouter un filtre**.</span><span class="sxs-lookup"><span data-stu-id="8105c-117">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="8105c-118">Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="8105c-118">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
    3.  <span data-ttu-id="8105c-119">Dans la liste déroulante **Égal à**, cliquez sur **Égal à** ou **Pas égal à**.</span><span class="sxs-lookup"><span data-stu-id="8105c-119">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
    4.  <span data-ttu-id="8105c-120">Dans la zone de texte, tapez le critère de recherche selon lequel filtrer les résultats, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="8105c-120">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6.  <span data-ttu-id="8105c-p105">les résultats de la recherche apparaissent sous **Résultats de la recherche**. Sélectionnez dans la liste les utilisateurs sur lesquels vous voulez exécuter les tâches de configuration.</span><span class="sxs-lookup"><span data-stu-id="8105c-p105">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8105c-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8105c-123">See Also</span></span>


[<span data-ttu-id="8105c-124">Affichage des informations sur les comptes d’utilisateurs activés pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8105c-124">Viewing information about user accounts enabled for Lync Server 2013</span></span>](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[<span data-ttu-id="8105c-125">Activation et désactivation des utilisateurs pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8105c-125">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

