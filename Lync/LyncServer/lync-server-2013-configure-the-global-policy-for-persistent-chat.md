---
title: 'Lync Server 2013 : configuration de la stratégie globale pour la conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b883a650a4430ee286c4824e49711e47e1509e26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520331"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="cceef-102">Configurer la stratégie globale pour la conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cceef-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cceef-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="cceef-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="cceef-104">Vous pouvez utiliser la stratégie globale par défaut pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="cceef-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="cceef-105">Vous pouvez également spécifier des stratégies supplémentaires pour les sites et les utilisateurs afin de déterminer si la conversation permanente est activée ou désactivée pour des utilisateurs et des sites spécifiques.</span><span class="sxs-lookup"><span data-stu-id="cceef-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="cceef-106">Il est impossible de supprimer la stratégie globale.</span><span class="sxs-lookup"><span data-stu-id="cceef-106">You cannot delete the global policy.</span></span> <span data-ttu-id="cceef-107">Si vous essayez de la supprimer, les valeurs par défaut de la configuration sont rétablies.</span><span class="sxs-lookup"><span data-stu-id="cceef-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cceef-108">Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="cceef-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="cceef-109">Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cceef-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="cceef-110">Pour configurer les paramètres de configuration du serveur de conversation permanente, voir <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">configurer les options de serveur de conversation permanente globalement ou pour le pool de serveurs de conversation permanente dans Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cceef-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="cceef-111">Pour configurer la stratégie globale pour la conversation permanente</span><span class="sxs-lookup"><span data-stu-id="cceef-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="cceef-112">À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="cceef-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cceef-113">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="cceef-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="cceef-114">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="cceef-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cceef-115">Vous pouvez également utiliser des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cceef-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="cceef-116">Pour plus d’informations, consultez la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configuration du serveur de conversation permanente à l’aide des applets de commande Windows PowerShell</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="cceef-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="cceef-117">Dans le panneau de configuration Lync Server, cliquez sur **conversation permanente**, puis sur **stratégie de conversation permanente**.</span><span class="sxs-lookup"><span data-stu-id="cceef-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="cceef-118">Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="cceef-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cceef-119">Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="cceef-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="cceef-120">Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut Globale.</span><span class="sxs-lookup"><span data-stu-id="cceef-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="cceef-121">Dans **Description**, fournissez des détails sur la stratégie de l’utilisateur (par exemple, stratégie globale pour centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="cceef-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="cceef-122">Pour contrôler la conversation permanente pour tous les sites et utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie de site ou une stratégie utilisateur, activez ou désactivez la case à cocher **activer la conversation permanente** .</span><span class="sxs-lookup"><span data-stu-id="cceef-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="cceef-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="cceef-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

