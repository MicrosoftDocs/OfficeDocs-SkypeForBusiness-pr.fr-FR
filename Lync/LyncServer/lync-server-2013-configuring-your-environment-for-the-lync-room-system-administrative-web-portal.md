---
title: 'Lync Server 2013 : configuration de votre environnement pour le portail Web d’administration de Lync Room System'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c42b5541fb28646e4c01d9d070b67f6fe103234
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="eab03-102">Configuration de votre environnement Lync Server 2013 pour le portail Web d’administration de Lync Room System</span><span class="sxs-lookup"><span data-stu-id="eab03-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eab03-103">_**Dernière modification de la rubrique :** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="eab03-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="eab03-104">Pour utiliser le portail Web d’administration de Lync Room System (LRS), vous devez installer ou configurer les éléments prérequis suivants.</span><span class="sxs-lookup"><span data-stu-id="eab03-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eab03-105">Si le serveur est configuré avec l’authentification Kerberos et NTLM et que LRS est en cours d’exécution sur un ordinateur qui n’est pas lié au domaine, l’authentification Kerberos échoue et l’utilisateur ne voit pas l’état de LRS dans le portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="eab03-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="eab03-106">Pour résoudre ce problème, configurez le serveur avec l’authentification NTLM ou l’authentification NTLM et TLS-DSK (sans Kerberos) ou associez l’ordinateur LRS au domaine.</span><span class="sxs-lookup"><span data-stu-id="eab03-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="eab03-107">Installez les mises à jour cumulatives de Lync Server 2013 : juillet 2013 dans la topologie Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eab03-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="eab03-108">Pour obtenir la mise à jour ou voir ce qu’elle contient, consultez la rubrique [mises à jour pour Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="eab03-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="eab03-109">Créez un utilisateur Active Directory compatible SIP.</span><span class="sxs-lookup"><span data-stu-id="eab03-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="eab03-110">Le portail Web d’administration LRS utilise ces informations d’identification pour demander des informations à Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eab03-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="eab03-111">Le nom d’utilisateur recommandé est LRSApp.</span><span class="sxs-lookup"><span data-stu-id="eab03-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="eab03-112">Créez un groupe de sécurité Active Directory avec le nom LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="eab03-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="eab03-113">Créez le groupe avec une étendue de groupe globale et de type de groupe comme sécurité.</span><span class="sxs-lookup"><span data-stu-id="eab03-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="eab03-114">Les utilisateurs à extension SIP qui sont ajoutés à ce groupe seront autorisés à afficher la liste des salles et à exécuter certaines commandes, telles que la collecte des journaux.</span><span class="sxs-lookup"><span data-stu-id="eab03-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="eab03-115">Créez un groupe de sécurité Active Directory avec le nom LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="eab03-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="eab03-116">Créez le groupe avec une étendue de groupe comme global et un type de groupe pour les utilisateurs activés pour la sécurité. SIP qui sont ajoutés à ce groupe sont autorisés à utiliser toutes les fonctionnalités du portail d’administration.</span><span class="sxs-lookup"><span data-stu-id="eab03-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="eab03-117">![Liste des groupes d’administration avec le rôle de groupe de sécurité](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Liste des groupes d’administration avec le rôle de groupe de sécurité")</span><span class="sxs-lookup"><span data-stu-id="eab03-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="eab03-118">Ajoutez LRSFullAccessAdminGroup en tant que membre de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="eab03-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="eab03-119">![Page des membres de propriétés LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Page des membres de propriétés LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="eab03-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="eab03-120">Créez un utilisateur Active Directory activé pour SIP avec le nom LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="eab03-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="eab03-121">Ajoutez cet utilisateur à LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="eab03-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="eab03-122">![Page des membres de propriétés LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Page des membres de propriétés LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="eab03-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="eab03-123">Installez ASP.NET MVC 4 pour Visual Studio 2010 SP1 et Visual Web Developer 2010 SP1, disponible dans le centre de téléchargement [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)Microsoft à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="eab03-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

