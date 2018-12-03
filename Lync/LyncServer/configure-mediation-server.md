---
title: Configurer le serveur de médiation
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="9bb9d-102">Configurer le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="9bb9d-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="9bb9d-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="9bb9d-103"></span></span>

<span data-ttu-id="9bb9d-104">_**Dernière modification :** 09-2012-28_</span><span class="sxs-lookup"><span data-stu-id="9bb9d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9bb9d-105">Cette procédure détaille les étapes pour configurer le pool Lync Server 2013 pour utiliser le serveur de médiation Lync Server 2013, au lieu du hérité Office Communications Server 2007 R2 Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="9bb9d-106">Pour publier avec succès, activer ou désactiver une topologie lors de l’ajout ou suppression d’un rôle de serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="9bb9d-107">Il est également possible de déléguer les droits d’administrateur approprié et les autorisations permettant d’ajouter des rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="9bb9d-108">Pour plus d’informations, voir Delegate Setup Permissions dans le serveur Standard Edition server ou Enterprise Edition server documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="9bb9d-109">Autres modifications de configuration, pour seulement l’appartenance au groupe RTCUniversalServerAdmins est requis.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bb9d-110">Pour obtenir les dernières informations sur la recherche de passerelles PSTN qualifiées, IP-PBX et services d’acheminement SIP qui fonctionnent avec Lync Server 2013, voir « Microsoft Unified Communications programme Open Interoperability » à <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="9bb9d-111">Pour configurer Mediation Server à l’aide de générateur de topologies</span><span class="sxs-lookup"><span data-stu-id="9bb9d-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="9bb9d-112">Ouvrez une topologie existante du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="9bb9d-113">Dans le volet gauche, accédez à **passerelles PSTN**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="9bb9d-114">Avec le bouton droit de **passerelles PSTN**, puis cliquez sur **Nouvelle passerelle IP/RTC**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="9bb9d-115">Configurez la page **Définir une nouvelle passerelle IP/RTC** avec les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bb9d-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="9bb9d-116">Entrez la nom de domaine complet ou l’adresse IP de passerelle.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="9bb9d-117">Le nom de domaine complet de la passerelle est requis si la passerelle utilise le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="9bb9d-118">Acceptez la valeur par défaut du **port d’écoute pour la passerelle IP/PSTN** ou entrez le nouveau port d’écoute s’il a été modifié.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="9bb9d-119">Définir le **protocole de Transport de Sip**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="9bb9d-120">Dans le volet de gauche, naviguez vers le **pool frontal Enterprise Edition** ou le **Serveur Standard Edition Server**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="9bb9d-121">Avec le bouton droit de la liste, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="9bb9d-122">Sous **Serveur de médiation**, de configurer les **ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="9bb9d-123">Ensuite, associez la passerelle PSTN nouvellement créée en la sélectionnant et en cliquant sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="9bb9d-124">Dans **Le Générateur de topologie**, sélectionnez le nœud supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="9bb9d-125">Dans le menu **Action** , sélectionnez **Publier la topologie** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="9bb9d-126">Lorsque l' **Assistant Publication** a terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bb9d-127">Il est important que vous terminiez la rubrique suivante, les <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">itinéraires de communications vocales modification à utiliser le nouveau serveur de médiation Lync Server 2013</A> pour vous assurer que les itinéraires de communications vocales pointent vers le serveur de médiation approprié.</span><span class="sxs-lookup"><span data-stu-id="9bb9d-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="9bb9d-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="9bb9d-128"></span></span></div>

