---
title: 'Lync Server 2013 : création d’une stratégie utilisateur pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bafc3a8681b2c85a01e48881e8a22f35c29d0d61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="36093-102">Créer une stratégie utilisateur pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36093-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36093-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="36093-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="36093-104">Dans le panneau de configuration Lync Server, vous définissez des stratégies utilisateur qui peuvent être affectées à des utilisateurs dans **les utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="36093-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="36093-105">La stratégie utilisateur supplante les stratégies globale et de site, mais uniquement pour les utilisateurs pour lesquels la stratégie utilisateur est appliquée.</span><span class="sxs-lookup"><span data-stu-id="36093-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36093-106">Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="36093-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="36093-107">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36093-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="36093-108">Pour configurer les paramètres de configuration du serveur de conversation permanente, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36093-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="36093-109">Pour créer une stratégie utilisateur pour la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="36093-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="36093-110">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="36093-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36093-111">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="36093-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="36093-112">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36093-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="36093-113">Vous pouvez également utiliser des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36093-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="36093-114">Consultez la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="36093-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="36093-115">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="36093-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="36093-116">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="36093-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="36093-117">Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="36093-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="36093-118">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.</span><span class="sxs-lookup"><span data-stu-id="36093-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="36093-119">Dans **Description**, fournissez des détails sur la stratégie utilisateur (par exemple, stratégie de conversation permanente pour un utilisateur spécifique).</span><span class="sxs-lookup"><span data-stu-id="36093-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="36093-120">Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie utilisateur, activez ou désactivez la case à cocher **activer la conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="36093-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="36093-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="36093-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

