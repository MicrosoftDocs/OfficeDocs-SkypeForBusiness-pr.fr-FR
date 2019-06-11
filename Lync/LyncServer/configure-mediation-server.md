---
title: Configurer le serveur de médiation
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bacd308249536aee49101cbcab739a0876343e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="e6723-102">Configurer le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="e6723-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6723-103">_**Dernière modification de la rubrique:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e6723-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e6723-104">Cette procédure décrit la procédure de configuration du pool Lync Server 2013 de manière à utiliser le serveur de médiation Lync Server 2013 au lieu du serveur de médiation traditionnel d’Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="e6723-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="e6723-105">Pour publier, activer ou désactiver une topologie lors de l’ajout ou de la suppression d’un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine.</span><span class="sxs-lookup"><span data-stu-id="e6723-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="e6723-106">Il est également possible de déléguer les droits d’administrateur et les autorisations nécessaires pour ajouter des rôles de serveur.</span><span class="sxs-lookup"><span data-stu-id="e6723-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="e6723-107">Pour plus d’informations, voir autorisations de configuration de délégué dans la documentation de déploiement Standard Edition Server ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="e6723-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="e6723-108">Pour les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est requise.</span><span class="sxs-lookup"><span data-stu-id="e6723-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6723-109">Pour obtenir les dernières informations sur la recherche de passerelles RTC, de PBX IP et de services d’agrégation de messages SIP qualifiés compatibles avec Lync Server 2013, voir «Microsoft Unified Communications Open <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Interoperability» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="e6723-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="e6723-110">Pour configurer la médiation serveur à l’aide du générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="e6723-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="e6723-111">Ouvrez une topologie existante à partir du générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="e6723-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="e6723-112">Dans le volet gauche, sélectionnez **passerelles RTC**.</span><span class="sxs-lookup"><span data-stu-id="e6723-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="e6723-113">Cliquez avec le bouton droit sur **passerelles RTC**, puis cliquez sur **nouvelle passerelle IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="e6723-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="e6723-114">Complétez la page **définir une nouvelle passerelle IP/RTC** en utilisant les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="e6723-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="e6723-115">Entrez le nom de domaine complet ou l’adresse IP de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="e6723-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="e6723-116">Le FQDN de la passerelle est requis si la passerelle utilise le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="e6723-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="e6723-117">Acceptez la valeur par défaut du **port d’écoute pour la passerelle IP/PSTN** ou entrez le nouveau port d’écoute s’il a été modifié.</span><span class="sxs-lookup"><span data-stu-id="e6723-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="e6723-118">Définissez le **protocole de transport SIP**.</span><span class="sxs-lookup"><span data-stu-id="e6723-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="e6723-119">Dans le volet gauche, accédez au **pool frontal d’Enterprise Edition** ou au **serveur Standard Edition Server**.</span><span class="sxs-lookup"><span data-stu-id="e6723-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="e6723-120">Cliquez avec le bouton droit sur la liste, puis cliquez sur **modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="e6723-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="e6723-121">Sous **serveur de médiation**, définissez les **ports Listening**.</span><span class="sxs-lookup"><span data-stu-id="e6723-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="e6723-122">Ensuite, associez la passerelle RTC nouvellement créée en la sélectionnant et en cliquant sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e6723-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="e6723-123">Dans **Générateur de topologie**, sélectionnez le **serveur Lync**le plus en tête de nœud.</span><span class="sxs-lookup"><span data-stu-id="e6723-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="e6723-124">Dans le menu **action** , sélectionnez la **topologie de publication** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="e6723-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="e6723-125">Lorsque l' **Assistant Publication** est terminé, cliquez sur **Terminer** pour fermer l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="e6723-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e6723-126">Il est important que vous complétiez le sujet suivant, que vous <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Modifiez les itinéraires vocaux pour utiliser le nouveau serveur de médiation Lync Server 2013</A> pour vous assurer que les itinéraires vocaux pointent vers le serveur de médiation approprié.</span><span class="sxs-lookup"><span data-stu-id="e6723-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

