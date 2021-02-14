---
title: Créer un pool VIS dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Résumé : Créez un pool de serveurs d’interconnexion vidéo dans Skype Entreprise Server à l’aide du Générateur de topologie.'
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802054"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="ea1a0-103">Créer un pool VIS dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ea1a0-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="ea1a0-104">**Résumé :** Créez un pool de serveurs d’interconnexion vidéo dans Skype Entreprise Server à l’aide du Générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="ea1a0-105">Créer un vis ou un pool VIS à l’aide du Générateur de topologie</span><span class="sxs-lookup"><span data-stu-id="ea1a0-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="ea1a0-106">Ouvrez le Générateur de topologie sur le serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="ea1a0-107">Dans le volet gauche du Générateur de  topologies, cliquez avec le bouton droit sur pools de serveurs d’interop vidéo et choisissez Nouveau pool de serveurs **d’interop res vidéo.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="ea1a0-108">Cela ouvre un Assistant Créer un nouveau pool de serveurs **d’interconnexion** vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="ea1a0-109">Fournissez le nom de groupe du pool pour le nouveau serveur d’opation vidéo et sélectionnez soit ce **pool** possède un serveur, soit ce **pool** dispose de plusieurs serveurs en fonction de vos besoins, puis appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="ea1a0-110">Si vous souhaitez déployer un pool de serveurs d’interconnexion vidéo pour fournir une haute disponibilité, sélectionnez **Ce pool dispose de plusieurs serveurs.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="ea1a0-111">Gardez à l’esprit cette option qui :</span><span class="sxs-lookup"><span data-stu-id="ea1a0-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="ea1a0-112">Vous devez déployer l’équilibrage de charge DNS pour prendre en charge les pools de serveurs d’interconnexion vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="ea1a0-113">Dans la page suivante, pour définir les ordinateurs  de cet élément **de pool,** entrez le nom de domaine complet de chaque serveur du pool dans le champ de texte, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="ea1a0-114">Répétez cette étape pour ajouter un autre serveur d’opation vidéo au pool.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="ea1a0-115">Lorsque vous avez défini tous les ordinateurs du pool, appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="ea1a0-116">Si vous souhaitez déployer un seul serveur d’opation vidéo dans le pool, car vous n’avez pas besoin d’une haute disponibilité, sélectionnez Ce **pool** a un serveur et appuyez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="ea1a0-117">Sélectionnez le pool/fe du saut suivant dans la liste de listes et appuyez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="ea1a0-118">Sélectionnez un pool edge à associer au VIS, puis appuyez sur **Terminer.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="ea1a0-119">Définissez un port TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="ea1a0-120">Sélectionnez le serveur d’opation vidéo nouvellement ajouté dans le volet gauche du Générateur de topologie, cliquez dessus avec le bouton droit et choisissez **Modifier les propriétés.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="ea1a0-121">Activez ou mettez à jour le port TCP ou TLS selon vos besoins et choisissez **OK.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="ea1a0-122">Bien que le protocole TLS soit ajouté par défaut, seul TCP a été entièrement testé avec Cisco Unified Communications Manager (CallManager ou CUCM).</span><span class="sxs-lookup"><span data-stu-id="ea1a0-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="ea1a0-123">Ajoutez une passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-123">Add a video gateway.</span></span> <span data-ttu-id="ea1a0-124">Pour ce faire, développez les composants partagés, cliquez avec le bouton droit sur **Passerelles vidéo** et sélectionnez **Nouvelle passerelle vidéo.**</span><span class="sxs-lookup"><span data-stu-id="ea1a0-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="ea1a0-125">Fournissez le FQDN ou l’adresse IP de la passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="ea1a0-126">La passerelle vidéo peut se voir dans un sous-domaine ou dans un autre domaine.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="ea1a0-127">Le CUCM utilisé par les VTC de votre système sert de passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="ea1a0-128">Sélectionnez IPv4 ou IPv6 selon le cas.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="ea1a0-129">Vous pouvez utiliser toutes les adresses IP configurées ou limiter l’utilisation du service aux adresses IP sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="ea1a0-130">Sélectionnez le port d’écoute de la passerelle vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="ea1a0-131">Sélectionnez le protocole de transport (TCP ou TLS) et associez-le à un serveur d’opation vidéo qui est installé pour une trunk SIP vidéo.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="ea1a0-132">Le protocole de transport de la passerelle vidéo doit correspondre au protocole de transport configuré pour le VIS.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="ea1a0-133">Une vidéo SIP correspondante est ajoutée une fois l’étape ci-dessus terminée.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="ea1a0-134">Cliquez avec le bouton droit sur la trunk vidéo SIP, puis sélectionnez la trunk qui vient d’être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="ea1a0-135">Le nom de la trunk sip vidéo, le serveur d’interopage vidéo associé, le protocole de transport SIP et le port peuvent tous être modifiés.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="ea1a0-136">Un serveur d’interconnexion vidéo prend en charge les trunks 1:N.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="ea1a0-137">Par conséquent, plusieurs branches peuvent être ajoutées, qui sont associées à un seul serveur d’interopivité vidéo, où chaque trunk s’termine sur une passerelle vidéo différente.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="ea1a0-138">La limitation est qu’une passerelle vidéo particulière dispose d’une seule et unique passerelle qui peut être définie pour le déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="ea1a0-139">Publiez le document de topologie comme décrit dans Créer et publier [une nouvelle topologie dans Skype Entreprise Server 2015.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="ea1a0-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ea1a0-140">Pour améliorer la résilience, vous souhaitez peut-être configurer un deuxième serveur d’interconnexion vidéo ou pool VIS, ou un pool frontal de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="ea1a0-141">Pour plus [d’informations, voir mécanismes](../../plan-your-deployment/video-interop-server.md#resiliency) de résilience.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="ea1a0-142">Toutes les tâches effectuées à l’aide du Générateur de topologie doivent maintenant être terminées.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="ea1a0-143">Procédez à l’installation du logiciel sur le ou les nouveaux serveurs VIS.</span><span class="sxs-lookup"><span data-stu-id="ea1a0-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="ea1a0-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea1a0-144">See also</span></span>

[<span data-ttu-id="ea1a0-145">Déployer le rôle serveur VIS dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ea1a0-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="ea1a0-146">Planifier le serveur d’opation vidéo dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="ea1a0-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="ea1a0-147">Création et publication d’une topologie dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea1a0-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
