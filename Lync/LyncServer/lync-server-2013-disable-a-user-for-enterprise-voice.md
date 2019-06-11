---
title: 'Lync Server 2013: désactiver un utilisateur pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="a6f61-102">Désactiver un utilisateur pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f61-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6f61-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a6f61-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a6f61-104">Utilisez la procédure suivante pour désactiver Enterprise Voice pour un compte d’utilisateur activé pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a6f61-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="a6f61-105">Pour désactiver un compte d’utilisateur pour voix entreprise</span><span class="sxs-lookup"><span data-stu-id="a6f61-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="a6f61-106">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="a6f61-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a6f61-107">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a6f61-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a6f61-108">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a6f61-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a6f61-109">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="a6f61-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a6f61-110">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="a6f61-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="a6f61-111">Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="a6f61-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="a6f61-112">Dans le menu **Edition**, cliquez sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="a6f61-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="a6f61-113">Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur une option sauf **entreprise voix**.</span><span class="sxs-lookup"><span data-stu-id="a6f61-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a6f61-114">Pour empêcher un utilisateur de passer des appels audio ou vidéo à l’aide de Lync, sous <STRONG>téléphonie</STRONG>, cliquez sur <STRONG>audio/vidéo désactivé</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a6f61-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="a6f61-115">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a6f61-115">Click **Commit**.</span></span>

<span data-ttu-id="a6f61-116">L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="a6f61-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a6f61-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6f61-117">See Also</span></span>


[<span data-ttu-id="a6f61-118">Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f61-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="a6f61-119">Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a6f61-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="a6f61-120">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="a6f61-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

