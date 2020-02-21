---
title: Configurer le serveur de médiation
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0705d51d321aba21a8bad7ba0e26351bf26bc5f0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="d8dbc-102">Configurer le serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="d8dbc-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8dbc-103">_**Dernière modification de la rubrique :** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d8dbc-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d8dbc-104">Cette procédure décrit en détail les étapes à suivre pour configurer le pool Lync Server 2013 afin qu’il utilise le serveur de médiation Lync Server 2013, au lieu du serveur de médiation Office Communications Server 2007 R2 hérité.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="d8dbc-p101">Pour réussir à publier, activer ou désactiver une topologie quand vous ajoutez ou supprimez un rôle serveur, vous devez être connecté en tant qu’utilisateur membre des groupes RTCUniversalServerAdmins et Admins du domaine. Il est également possible de déléguer les droits et autorisations d’administrateur appropriés pour ajouter des rôles serveur. Pour plus d’informations, voir Déléguer des autorisations de configuration dans la documentation de déploiement consacrée aux serveurs Standard Edition ou Enterprise Edition. Pour toutes les autres modifications de configuration, seule l’appartenance au groupe RTCUniversalServerAdmins est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-p101">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups. It is also possible to delegate the proper administrator rights and permissions for adding server roles. For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation. For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8dbc-109">Pour obtenir les dernières informations sur la recherche de passerelles RTC qualifiées, de PBX IP et de services de jonction SIP fonctionnant avec Lync Server 2013, voir « Microsoft Unified Communications Open Interoperability <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>Program » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="d8dbc-110">Pour configurer le serveur de médiation à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="d8dbc-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="d8dbc-111">Ouvrez une topologie existante à partir du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="d8dbc-112">Dans le volet gauche, accédez à **Passerelles PSTN**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="d8dbc-113">Cliquez avec le bouton droit sur **Passerelles PSTN**, puis cliquez sur **Nouvelle passerelle IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="d8dbc-114">Complétez la page **Définir une nouvelle passerelle IP/PSTN** à l’aide des informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d8dbc-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="d8dbc-p102">Entrez le nom de domaine complet ou l’adresse IP de la passerelle. Le nom de domaine complet de la passerelle est requis si celle-ci utilise le protocole TLS.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-p102">Enter the gateway FQDN or IP address. The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="d8dbc-117">Acceptez la valeur **Port d’écoute de la passerelle IP/PSTN** par défaut ou entrez le nouveau port d’écoute s’il a été modifié.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="d8dbc-118">Définissez la valeur **Protocole de transport SIP**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="d8dbc-119">Dans le volet gauche, accédez au **Pool frontal Enterprise Edition** ou au **Serveur Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="d8dbc-120">Cliquez avec le bouton droit sur le pool, puis cliquez sur **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="d8dbc-121">Sous **Serveur de médiation**, définissez les **Ports d’écoute**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="d8dbc-122">Ensuite, associez la nouvelle passerelle PSTN créée en la sélectionnant, puis en cliquant sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="d8dbc-123">Dans le **Générateur de topologie**, sélectionnez le nœud de niveau supérieur **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="d8dbc-124">Dans le menu **Action**, sélectionnez **Publier la topologie**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="d8dbc-125">Une fois que l’**Assistant Publication** a terminé, cliquez sur **Terminer** pour le fermer.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d8dbc-126">Il est important que vous terminiez la rubrique suivante, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">change Voice routes to use the New Lync server 2013 Mediation Server</A> pour vous assurer que les itinéraires des communications vocales pointent vers le serveur de médiation approprié.</span><span class="sxs-lookup"><span data-stu-id="d8dbc-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

