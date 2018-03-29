---
title: Création d’un pool de serveurs d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour 2015 de serveur d’entreprise à l’aide du Générateur de topologies.'
ms.openlocfilehash: ab34cf5b547301314bf169b56481818f78e9908a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-vis-pool-in-skype-for-business-server-2015"></a><span data-ttu-id="5d051-103">Création d’un pool de serveurs d’interopérabilité vidéo (VIS) dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d051-103">Create a VIS pool in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5d051-104">**Résumé :** Créer un pool de serveurs d’interopérabilité vidéo dans Skype pour 2015 de serveur d’entreprise à l’aide du Générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="5d051-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server 2015 using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="5d051-105">Création d’un VIS ou d’un pool de VIS à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="5d051-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="5d051-106">Ouvrez le Générateur de topologie sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="5d051-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="5d051-107">Dans le volet gauche du Générateur de topologies, cliquez droit sur ** Pools de serveur vidéo Interop ** et choisissez **Nouveau Pool de serveur vidéo Interop**.</span><span class="sxs-lookup"><span data-stu-id="5d051-107">From the left pane of Topology Builder, right click on ** Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="5d051-108">Cela a pour effet d’ouvrir l’assistant **Créer un nouveau pool de serveurs d’interopérabilité vidéo**.</span><span class="sxs-lookup"><span data-stu-id="5d051-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="5d051-109">Fournir le nom FQDN du Pool pour le nouveau serveur d’interopérabilité vidéo et sélectionnez **ce pool possède un seul serveur** ou **ce pool possède plusieurs serveurs** en fonction de vos besoins, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d051-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="5d051-110">Si vous souhaitez déployer un pool de serveurs d’interopérabilité de vidéo pour offrir une haute disponibilité, sélectionnez **ce pool possède plusieurs serveurs**.</span><span class="sxs-lookup"><span data-stu-id="5d051-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="5d051-111">Avec cette option, n’oubliez pas que :</span><span class="sxs-lookup"><span data-stu-id="5d051-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="5d051-112">Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interopérabilité vidéo.</span><span class="sxs-lookup"><span data-stu-id="5d051-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="5d051-113">Sur la page suivante, pour l’élément **Définir les ordinateurs dans ce pool**, entrez le **nom de domaine complet de l’ordinateur** pour chaque serveur du pool dans la zone de texte, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5d051-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="5d051-114">Répétez cette étape pour ajouter un autre serveur d’interopérabilité vidéo au pool.</span><span class="sxs-lookup"><span data-stu-id="5d051-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="5d051-115">Quand vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d051-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
    <span data-ttu-id="5d051-116">Si vous souhaitez ne déployer qu’un seul serveur d’interopérabilité vidéo dans le pool, car vous n’avez pas besoin de haute disponibilité, sélectionnez **ce groupe dispose d’un serveur** puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d051-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="5d051-117">Sélectionnez le pool du tronçon suivant/FE dans la liste déroulante et appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5d051-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="5d051-118">Sélectionnez un pool Edge à associer au VIS et appuyez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="5d051-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="5d051-119">Configurez un port TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="5d051-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="5d051-120">Sélectionnez vidéo Interop serveur nouvellement ajouté à partir du volet de gauche du Générateur de topologies, avec le bouton droit dessus et sélectionnez **Modifier les propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5d051-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="5d051-121">Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d051-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="5d051-122">Bien que TLS soit ajouté par défaut, seul le port TCP a été pleinement testé avec CUCM.</span><span class="sxs-lookup"><span data-stu-id="5d051-122">Although by default TLS is added, only TCP has been fully tested with CUCM.</span></span>
    
6. <span data-ttu-id="5d051-p106">Ajoutez une passerelle vidéo. Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo**.</span><span class="sxs-lookup"><span data-stu-id="5d051-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="5d051-p107">Indiquez le nom de domaine complet ou l’adresse IP de la passerelle vidéo. La passerelle vidéo peut se trouver dans un sous-domaine ou dans un domaine différent. Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="5d051-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="5d051-p108">Sélectionnez IPv4 ou IPv6 selon la situation. Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service à certaines adresses IP.</span><span class="sxs-lookup"><span data-stu-id="5d051-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="5d051-130">Sélectionnez le port d’écoute de la passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="5d051-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="5d051-131">Sélectionnez le protocole de Transport (TCP ou TLS) et l’associer à un serveur vidéo Interop est définie pour un vidéo SIP trunk.</span><span class="sxs-lookup"><span data-stu-id="5d051-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="5d051-132">Le protocole de transport pour la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.</span><span class="sxs-lookup"><span data-stu-id="5d051-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="5d051-133">Une jonction vidéo SIP correspondante est ajoutée une fois que l’étape ci-dessus a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="5d051-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="5d051-134">Cliquez avec le bouton droit sur la jonction vidéo SIP et sélectionnez la jonction qui vient d’être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5d051-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="5d051-135">Le nom de jonction de SIP vidéo, associée à la vidéo serveur de protocole de Transport de SIP, Interop et port peut tous être modifié.</span><span class="sxs-lookup"><span data-stu-id="5d051-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="5d051-136">Un serveur d’interopérabilité vidéo prend en charge les puits 1 à n.</span><span class="sxs-lookup"><span data-stu-id="5d051-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="5d051-137">Donc plusieurs troncs peuvent être ajoutés, qui sont associés à un seul serveur vidéo Interop, où chaque ligne se termine sur une passerelle vidéo différents.</span><span class="sxs-lookup"><span data-stu-id="5d051-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="5d051-138">La limitation est qu’une passerelle vidéo tronc d’un seul et unique qui peut être définis pour le Skype pour le déploiement du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="5d051-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="5d051-139">Publier le Document de topologie, comme décrit dans [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="5d051-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5d051-140">Pour améliorer la souplesse, vous souhaiterez configurer un deuxième serveur d’interopérabilité vidéo ou de la VIS pool, ou une sauvegarde Front-End.</span><span class="sxs-lookup"><span data-stu-id="5d051-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="5d051-141">Pour obtenir des renseignements complémentaires, veuillez consulter la rubrique [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).</span><span class="sxs-lookup"><span data-stu-id="5d051-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="5d051-p113">Toutes les tâches exécutées à l’aide du Générateur de topologie sont maintenant terminées. Installez maintenant le logiciel sur le ou les nouveaux serveurs VIS.</span><span class="sxs-lookup"><span data-stu-id="5d051-p113">All tasks performed using Topology Builder should now be complete. Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="5d051-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5d051-144">See also</span></span>

#### 

[<span data-ttu-id="5d051-145">Déployer le rôle de serveur de VIS dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d051-145">Deploy the VIS server role in Skype for Business Server 2015</span></span>](deploy-the-vis-server-role.md)
#### 

[<span data-ttu-id="5d051-146">Plan pour un serveur interopérabilité vidéo dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d051-146">Plan for Video Interop Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="5d051-147">Créez et publiez la nouvelle topologie dans Skype pour Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5d051-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)

