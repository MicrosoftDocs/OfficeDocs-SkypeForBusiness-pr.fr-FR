---
title: 'Lync Server 2013 : configuration des compléments pour les salles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca916731f34bf08e59ae2ba281a1c6d723b46ae8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a><span data-ttu-id="90a2d-102">Configurer des compléments pour les salles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90a2d-102">Configure add-ins for rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90a2d-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="90a2d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="90a2d-104">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la section **complément** de la page **conversation permanente** pour associer des URL à des salles de conversation permanentes.</span><span class="sxs-lookup"><span data-stu-id="90a2d-104">In Lync Server 2013 Control Panel, you can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="90a2d-105">Ces URL apparaissent dans le client Lync 2013 dans la salle de conversation dans le volet d’extensibilité de conversation.</span><span class="sxs-lookup"><span data-stu-id="90a2d-105">These URLs appear in the Lync 2013 client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="90a2d-106">Un administrateur doit ajouter des compléments à la liste des compléments inscrits, et les gestionnaires de salle de conversation/créateurs doivent associer des salles à l’un des compléments inscrits pour que les utilisateurs puissent voir cette mise à niveau dans leur client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="90a2d-106">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators have to associate rooms with one of the registered add-ins before users can see this upgrade in their Lync 2013 client.</span></span>

<span data-ttu-id="90a2d-107">Les compléments servent à étendre l’expérience dans la salle.</span><span class="sxs-lookup"><span data-stu-id="90a2d-107">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="90a2d-108">Un complément classique peut inclure une URL pointant vers une application Silverlight qui intercepte quand un ticker boursier est publié dans une salle de conversation et affiche l’historique des actions dans le volet d’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="90a2d-108">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="90a2d-109">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="90a2d-109">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="90a2d-110">Pour configurer des compléments pour des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="90a2d-110">To configure Add-ins for chat rooms</span></span>

1.  <span data-ttu-id="90a2d-111">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="90a2d-111">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="90a2d-112">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="90a2d-112">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="90a2d-113">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="90a2d-113">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="90a2d-114">Vous pouvez également utiliser des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90a2d-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="90a2d-115">Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="90a2d-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="90a2d-116">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="90a2d-116">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="90a2d-117">Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="90a2d-117">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="90a2d-118">Dans la page **Complément**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="90a2d-118">On the **Add-in** page, click **New**.</span></span>

5.  <span data-ttu-id="90a2d-119">Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente dans lequel vous devez créer le complément.</span><span class="sxs-lookup"><span data-stu-id="90a2d-119">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="90a2d-120">Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.</span><span class="sxs-lookup"><span data-stu-id="90a2d-120">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6.  <span data-ttu-id="90a2d-121">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="90a2d-121">In **New Add-in**, do the following:</span></span>
    
      - <span data-ttu-id="90a2d-122">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="90a2d-122">In **Name**, specify a name for the new add-in.</span></span>
    
      - <span data-ttu-id="90a2d-p106">Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="90a2d-p106">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7.  <span data-ttu-id="90a2d-125">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="90a2d-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90a2d-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90a2d-126">See Also</span></span>


[<span data-ttu-id="90a2d-127">Ouvrir les outils d’administration de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="90a2d-127">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="90a2d-128">Configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90a2d-128">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</span></span>](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

