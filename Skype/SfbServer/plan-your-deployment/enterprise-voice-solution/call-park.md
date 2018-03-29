---
title: Planification du parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: Planification de parc d’appel dans Skype pour Business Server Voix Entreprise, qui permet de placer des appels bloqués et transférez des appels aux services. Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: 6198b54a93c36c2e6a2fcd28fa91f51c43fb59de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a><span data-ttu-id="e4797-104">Planification du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="e4797-104">Plan for Call Park in Skype for Business 2015</span></span>
 
<span data-ttu-id="e4797-105">Planification de parc d’appel dans Skype pour Business Server Voix Entreprise, qui permet de placer des appels bloqués et transférez des appels aux services.</span><span class="sxs-lookup"><span data-stu-id="e4797-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="e4797-106">Cela inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e4797-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="e4797-107">L’application d’appel Park permet aux utilisateurs de Voix Entreprise effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4797-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="e4797-108">mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;</span><span class="sxs-lookup"><span data-stu-id="e4797-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="e4797-109">mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;</span><span class="sxs-lookup"><span data-stu-id="e4797-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="e4797-110">mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.</span><span class="sxs-lookup"><span data-stu-id="e4797-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="e4797-111">Lorsque les parcs à un utilisateur un appel, Skype pour Business Server transfère l’appel vers un numéro temporaire, appelé une orbite, où l’appel est maintenu jusqu'à ce qu’il est extrait ou il arrive à expiration. Skype pour Business Server envoie l’orbite à l’utilisateur qui stationnés de l’appel.</span><span class="sxs-lookup"><span data-stu-id="e4797-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="e4797-112">Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.</span><span class="sxs-lookup"><span data-stu-id="e4797-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="e4797-p104">L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.</span><span class="sxs-lookup"><span data-stu-id="e4797-p104">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="e4797-115">Car les plages d’orbite sont globalement uniques, il est possible de récupérer des appels à partir de n’importe quel Skype pour site Business Server ou le téléphone PBX si le routage est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="e4797-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="e4797-116">Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée.</span><span class="sxs-lookup"><span data-stu-id="e4797-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="e4797-117">Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte.</span><span class="sxs-lookup"><span data-stu-id="e4797-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="e4797-118">Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix.</span><span class="sxs-lookup"><span data-stu-id="e4797-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="e4797-119">Si personne ne répond à un appel transféré, l’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="e4797-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="e4797-120">L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="e4797-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="e4797-121">Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels.</span><span class="sxs-lookup"><span data-stu-id="e4797-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="e4797-122">Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué.</span><span class="sxs-lookup"><span data-stu-id="e4797-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="e4797-123">Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="e4797-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="e4797-124">Chaque pool frontal comporte une table de parc d’appel sur le correspondant serveur principal qui est utilisé pour gérer les appels qui sont stationnés sur le pool.</span><span class="sxs-lookup"><span data-stu-id="e4797-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="e4797-125">La liste de plages d’orbite est stockée dans la direction centrale stocker et est utilisé pour router des orbites vers le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="e4797-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="e4797-126">Chaque Skype pour le pool de serveur de l’entreprise où l’application d’appel Park est déployée et configurée peut avoir une ou plusieurs plages d’orbite.</span><span class="sxs-lookup"><span data-stu-id="e4797-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="e4797-127">Plages d’orbite doivent être globalement uniques sur le Skype pour le déploiement du serveur de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="e4797-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="e4797-p107">Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.</span><span class="sxs-lookup"><span data-stu-id="e4797-p107">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4797-130">Les fichiers de musique en attente personnalisés pour le parc de l’appel ne sont pas sauvegardés dans le cadre de la Skype pour le processus de récupération après sinistre Business Server et seront perdues si les fichiers téléchargés vers le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="e4797-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="e4797-131">Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.</span><span class="sxs-lookup"><span data-stu-id="e4797-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="e4797-132">L’application d’appel Park est un composant de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e4797-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="e4797-133">Lors du déploiement de Voix Entreprise, l’application d’appel Park est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="e4797-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="e4797-134">Avant de pouvoir utiliser appel Park, toutefois, l’administrateur de Voix Entreprise doit le configurer et l’activer pour les utilisateurs via la stratégie voice.</span><span class="sxs-lookup"><span data-stu-id="e4797-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="e4797-135">Déploiement et configuration requise</span><span class="sxs-lookup"><span data-stu-id="e4797-135">Deployment and requirements</span></span>

<span data-ttu-id="e4797-136">L’application d’appel Park est automatiquement installée lors du déploiement de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e4797-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e4797-137">Vous activez le parc d’appel en configurant la stratégie voice.</span><span class="sxs-lookup"><span data-stu-id="e4797-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="e4797-138">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="e4797-138">Software requirements</span></span>

<span data-ttu-id="e4797-139">Les serveurs de tous les serveurs frontaux et Standard Edition où est déployé le parc de l’appel doivent être Windows Media Format Runtime installé pour les serveurs exécutant Windows Server 2008 R2, ou Microsoft Media Foundation pour les serveurs exécutant Windows Server ou Windows Server 2012 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="e4797-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="e4797-140">Pour Windows Server 2008 R2, Windows Media Format Runtime est installé dans le cadre de l’expérience utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="e4797-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="e4797-141">Windows Media Format Runtime ou Microsoft Media Foundation est requise pour Windows Media Audio (.wma) fichiers appel Park joue de la musique en attente.</span><span class="sxs-lookup"><span data-stu-id="e4797-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="e4797-142">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="e4797-142">Port requirements</span></span>

<span data-ttu-id="e4797-143">L’application d’appel Park utilise le **Port 5075** pour les requêtes d’écoute SIP.</span><span class="sxs-lookup"><span data-stu-id="e4797-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e4797-144">Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer** .</span><span class="sxs-lookup"><span data-stu-id="e4797-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="e4797-145">Pour plus d’informations sur cette applet de commande, consultez la documentation de Communications Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="e4797-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="e4797-146">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="e4797-146">Audio File requirements</span></span>

<span data-ttu-id="e4797-147">Le parc d’appel application prend en charge uniquement les fichiers Audio Windows Media (.wma) de la musique sur Maintenez.</span><span class="sxs-lookup"><span data-stu-id="e4797-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="e4797-148">Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="e4797-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="e4797-149">Pour télécharger Microsoft Expression Encoder 4, consultez [« Expression Encoder 4 »](https://go.microsoft.com/fwlink/p/?linkId=202843).</span><span class="sxs-lookup"><span data-stu-id="e4797-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="e4797-150">Utilisez l’outil pour convertir le fichier au format .wma.</span><span class="sxs-lookup"><span data-stu-id="e4797-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="e4797-151">Le format recommandé pour les fichiers de musique en attente d’appel Park est Media Audio 9, 44 kHz, 16 bits Mono, CBR, 32 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="e4797-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4797-152">Le fichier converti est lu sur le téléphone à seulement 16 kHz, même s’il a été enregistré à 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="e4797-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="e4797-153">Types d’appels et clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="e4797-153">Supported clients and calls</span></span>

<span data-ttu-id="e4797-154">Les clients et les types d’appels suivants sont pris en charge pour le parc de l’appel</span><span class="sxs-lookup"><span data-stu-id="e4797-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="e4797-155">Clients pris en charge pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="e4797-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="e4797-156">Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), PSTN (réseau téléphonique commuté) ou mobile peuvent être parqués.</span><span class="sxs-lookup"><span data-stu-id="e4797-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4797-p114">Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible.</span><span class="sxs-lookup"><span data-stu-id="e4797-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="e4797-159">Les clients suivants permettent appel Park park appels :</span><span class="sxs-lookup"><span data-stu-id="e4797-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="e4797-160">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e4797-160">Skype for Business</span></span>
    
- <span data-ttu-id="e4797-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e4797-161">Lync 2013</span></span>
    
- <span data-ttu-id="e4797-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e4797-162">Lync 2010</span></span>
    
- <span data-ttu-id="e4797-163">Intendant Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e4797-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="e4797-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="e4797-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="e4797-165">Téléphones mobiles ne permet pas appel Park park appels.</span><span class="sxs-lookup"><span data-stu-id="e4797-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="e4797-166">Clients pris en charge pour la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="e4797-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="e4797-p115">Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et PSTN ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="e4797-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="e4797-169">Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="e4797-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="e4797-170">Les clients suivants peuvent récupérer les appels qui sont stationnés sur le parc de l’appel :</span><span class="sxs-lookup"><span data-stu-id="e4797-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="e4797-171">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e4797-171">Skype for Business</span></span>
    
- <span data-ttu-id="e4797-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e4797-172">Lync 2013</span></span>
    
- <span data-ttu-id="e4797-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e4797-173">Lync 2010</span></span>
    
- <span data-ttu-id="e4797-174">Intendant Lync 2010</span><span class="sxs-lookup"><span data-stu-id="e4797-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="e4797-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="e4797-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="e4797-176">Téléphones de partie commune IP</span><span class="sxs-lookup"><span data-stu-id="e4797-176">IP common area phones</span></span>
    
- <span data-ttu-id="e4797-177">Les téléphones IP non connectés à la Skype pour l’infrastructure de serveur d’entreprise, y compris les téléphones de zone courants et des téléphones private branch exchange (PBX)</span><span class="sxs-lookup"><span data-stu-id="e4797-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="e4797-178">Planification de capacité pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="e4797-178">Call Park capacity planning</span></span>

<span data-ttu-id="e4797-179">Le tableau suivant décrit le modèle d’appel Park utilisateur que vous pouvez utiliser comme base pour la planification de capacité.</span><span class="sxs-lookup"><span data-stu-id="e4797-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e4797-180">Gardez à l’esprit que, pour la planification de capacité la récupération après sinistre, chaque pool d’un pool de paires devrait être en mesure de gérer les charges de travail pour les services d’appel Park dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="e4797-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="e4797-181">**Modèle d’utilisateur appel Park**</span><span class="sxs-lookup"><span data-stu-id="e4797-181">**Call Park User Model**</span></span>

|<span data-ttu-id="e4797-182">**Métrique**</span><span class="sxs-lookup"><span data-stu-id="e4797-182">**Metric**</span></span>|<span data-ttu-id="e4797-183">**Par pool frontal <br/> (avec 8 serveurs frontaux)**</span><span class="sxs-lookup"><span data-stu-id="e4797-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="e4797-184">**Par serveur Standard Edition server**</span><span class="sxs-lookup"><span data-stu-id="e4797-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4797-185">Taux de parcage</span><span class="sxs-lookup"><span data-stu-id="e4797-185">Park rate</span></span>  <br/> |<span data-ttu-id="e4797-186">8 par minute</span><span class="sxs-lookup"><span data-stu-id="e4797-186">8 per minute</span></span>  <br/> |<span data-ttu-id="e4797-187">1 par minute</span><span class="sxs-lookup"><span data-stu-id="e4797-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="e4797-188">Taux d’appels parqués récupérés</span><span class="sxs-lookup"><span data-stu-id="e4797-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="e4797-189">8 par minute</span><span class="sxs-lookup"><span data-stu-id="e4797-189">8 per minute</span></span>  <br/> |<span data-ttu-id="e4797-190">1 par minute</span><span class="sxs-lookup"><span data-stu-id="e4797-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="e4797-191">Durée moyenne de parcage</span><span class="sxs-lookup"><span data-stu-id="e4797-191">Average park duration</span></span>  <br/> |<span data-ttu-id="e4797-192">60 secondes</span><span class="sxs-lookup"><span data-stu-id="e4797-192">60 seconds</span></span>  <br/> |<span data-ttu-id="e4797-193">60 secondes</span><span class="sxs-lookup"><span data-stu-id="e4797-193">60 seconds</span></span>  <br/> |
   

