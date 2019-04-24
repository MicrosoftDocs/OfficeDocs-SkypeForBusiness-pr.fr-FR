---
title: Créer un pool VIS dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créez un pool de serveurs d’interopérabilité vidéo dans Skype pour Business Server à l’aide du Générateur de topologie.'
ms.openlocfilehash: 484cb1c504680dde393d24ce65606e415d070edb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219635"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="5e69a-103">Créer un pool VIS dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5e69a-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="5e69a-104">**Résumé :** Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour Business Server à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="5e69a-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="5e69a-105">Création d’un VIS ou d’un pool de VIS à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="5e69a-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="5e69a-106">Ouvrez le Générateur de topologie sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="5e69a-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="5e69a-107">Dans le volet gauche du Générateur de topologie, cliquez avec le bouton droit sur **Pools de serveurs d’interopérabilité vidéo** et choisissez **Nouveau Pool de serveurs d’interopérabilité vidéo**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="5e69a-108">Cela a pour effet d’ouvrir l’assistant **Créer un nouveau pool de serveurs d’interopérabilité vidéo**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="5e69a-109">Fournir le nom complet du Pool pour le nouveau serveur d’interopérabilité vidéo et sélectionnez **ce pool possède un seul serveur** ou **ce pool possède plusieurs serveurs** en fonction de vos besoins, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="5e69a-110">Si vous souhaitez déployer un pool de serveurs d’interopérabilité de vidéo pour fournir une haute disponibilité, sélectionnez **ce pool possède plusieurs serveurs**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="5e69a-111">Avec cette option, n’oubliez pas que :</span><span class="sxs-lookup"><span data-stu-id="5e69a-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="5e69a-112">Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="5e69a-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="5e69a-113">Sur la page suivante, pour l’élément **Définir les ordinateurs dans ce pool**, entrez le **nom de domaine complet de l’ordinateur** pour chaque serveur du pool dans la zone de texte, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="5e69a-114">Répétez cette étape pour ajouter un autre serveur d’interopérabilité vidéo vers le pool.</span><span class="sxs-lookup"><span data-stu-id="5e69a-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="5e69a-115">Quand vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="5e69a-116">Si vous souhaitez ne déployer qu’un seul serveur d’interopérabilité vidéo dans le pool, car vous n’avez pas besoin de haute disponibilité, sélectionnez **ce pool possède un seul serveur** , puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="5e69a-117">Sélectionnez le pool du tronçon suivant/FE dans la liste déroulante et appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="5e69a-118">Sélectionnez un pool Edge à associer au VIS et appuyez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="5e69a-119">Configurez un port TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="5e69a-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="5e69a-120">Sélectionnez le serveur d’interopérabilité vidéo nouvellement ajoutés dans le volet gauche du Générateur de topologie, avec le bouton droit dessus et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="5e69a-121">Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="5e69a-122">Bien que TLS est ajouté par défaut, seul TCP a été intégralement testé avec Cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="5e69a-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="5e69a-p106">Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo**.</span><span class="sxs-lookup"><span data-stu-id="5e69a-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="5e69a-p107">Indiquez le nom de domaine complet ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se trouver dans un sous-domaine ou dans un domaine différent. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="5e69a-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="5e69a-p108">Sélectionnez IPv4 ou IPv6 selon la situation. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service à certaines adresses IP.</span><span class="sxs-lookup"><span data-stu-id="5e69a-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="5e69a-130">Sélectionnez le port d’écoute de la passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="5e69a-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="5e69a-131">Sélectionnez le protocole de Transport (TCP ou TLS) et l’associer à un serveur d’interopérabilité vidéo qui est définie pour une jonction SIP vidéo.</span><span class="sxs-lookup"><span data-stu-id="5e69a-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="5e69a-132">Le protocole de transport pour la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.</span><span class="sxs-lookup"><span data-stu-id="5e69a-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="5e69a-133">Une jonction vidéo SIP correspondante est ajoutée une fois que l’étape ci-dessus a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="5e69a-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="5e69a-134">Cliquez avec le bouton droit sur la jonction vidéo SIP et sélectionnez la jonction qui vient d’être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5e69a-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="5e69a-135">Le nom de jonction SIP vidéo, associée à la vidéo serveur de protocole de Transport SIP, interopérabilité et port est possible de modifier.</span><span class="sxs-lookup"><span data-stu-id="5e69a-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5e69a-136">Un serveur d’interopérabilité vidéo prend en charge des jonctions 1 : n.</span><span class="sxs-lookup"><span data-stu-id="5e69a-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="5e69a-137">Par conséquent, plusieurs jonctions peuvent être ajoutées, qui sont associé à un seul serveur vidéo Interop, où chaque jonction s’arrête sur une passerelle vidéo différents.</span><span class="sxs-lookup"><span data-stu-id="5e69a-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="5e69a-138">La limite est qu’une passerelle vidéo particulier qu’une seule jonction qui peut être définies pour le Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5e69a-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="5e69a-139">Publier le Document de topologie, comme décrit dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="5e69a-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e69a-140">Pour améliorer la résistance, vous souhaiterez peut-être configurer un pool de serveur d’interopérabilité vidéo ou VIS deuxième ou un pool frontal de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5e69a-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="5e69a-141">Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).</span><span class="sxs-lookup"><span data-stu-id="5e69a-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="5e69a-142">Toutes les tâches exécutées à l’aide du Générateur de topologie sont maintenant terminées.</span><span class="sxs-lookup"><span data-stu-id="5e69a-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="5e69a-143">Installez maintenant le logiciel sur le ou les nouveaux serveurs VIS.</span><span class="sxs-lookup"><span data-stu-id="5e69a-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="5e69a-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e69a-144">See also</span></span>

[<span data-ttu-id="5e69a-145">Déployer le rôle de serveur VIS Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="5e69a-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="5e69a-146">Planification de serveur interopérabilité vidéo dans Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="5e69a-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="5e69a-147">Création et publication d’une topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e69a-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
