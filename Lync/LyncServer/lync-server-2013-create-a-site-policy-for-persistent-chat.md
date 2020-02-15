---
title: 'Lync Server 2013 : création d’une stratégie de site pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed149f39363610f1bc7d17cbdb08f30710eed904
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="aced0-102">Créer une stratégie de site pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aced0-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aced0-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="aced0-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="aced0-104">Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente propre au site.</span><span class="sxs-lookup"><span data-stu-id="aced0-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="aced0-105">La configuration de la stratégie du site supplante la stratégie globale, uniquement pour le site pour lequel elle est définie.</span><span class="sxs-lookup"><span data-stu-id="aced0-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aced0-106">Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="aced0-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="aced0-107">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aced0-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="aced0-108">Pour configurer les paramètres de configuration du serveur de conversation permanente, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aced0-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="aced0-109">Pour créer une stratégie de conversation permanente pour un site</span><span class="sxs-lookup"><span data-stu-id="aced0-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="aced0-110">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="aced0-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="aced0-111">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="aced0-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="aced0-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="aced0-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="aced0-113">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="aced0-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aced0-114">Vous pouvez également utiliser des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aced0-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="aced0-115">Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="aced0-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="aced0-116">Cliquez sur **Nouveau**, puis sur **Stratégie de site**.</span><span class="sxs-lookup"><span data-stu-id="aced0-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="aced0-117">Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.</span><span class="sxs-lookup"><span data-stu-id="aced0-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="aced0-118">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="aced0-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="aced0-119">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, Redmond).</span><span class="sxs-lookup"><span data-stu-id="aced0-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="aced0-120">Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, stratégie de salle de conversation pour Redmond).</span><span class="sxs-lookup"><span data-stu-id="aced0-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="aced0-121">Pour contrôler la conversation permanente pour tous les sites qui ne sont pas spécifiquement contrôlés via une stratégie de site, activez ou désactivez la case à cocher **activer la conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="aced0-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="aced0-122">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="aced0-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

