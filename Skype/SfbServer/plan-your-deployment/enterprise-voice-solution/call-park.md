---
title: Plan for Call Park in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: La planification du parcage d’appel dans Skype Entreprise Server Voix Entreprise, qui permet de mettre les appels en attente et de transférer des appels vers des services. Inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825924"
---
# <a name="plan-for-call-park-in-skype-for-business"></a><span data-ttu-id="953f4-104">Plan for Call Park in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="953f4-104">Plan for Call Park in Skype for Business</span></span>
 
<span data-ttu-id="953f4-105">La planification du parcage d’appel dans Skype Entreprise Server Voix Entreprise, qui permet de mettre les appels en attente et de transférer des appels vers des services.</span><span class="sxs-lookup"><span data-stu-id="953f4-105">Planning for call park in Skype for Business Server Enterprise Voice, which enables putting calls on hold and transferring calls to departments.</span></span> <span data-ttu-id="953f4-106">Inclut la planification de la capacité, les appels pris en charge et les clients pris en charge.</span><span class="sxs-lookup"><span data-stu-id="953f4-106">Includes capacity planning, supported calls, and supported clients.</span></span>
  
<span data-ttu-id="953f4-107">L’application de parcage d’Voix Entreprise permet aux utilisateurs d’appliquer les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="953f4-107">The Call Park application enables Enterprise Voice users to do the following:</span></span>
  
- <span data-ttu-id="953f4-108">Mettez un appel en attente, puis récupérez l’appel à partir du même téléphone ou d’un autre téléphone.</span><span class="sxs-lookup"><span data-stu-id="953f4-108">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>
    
- <span data-ttu-id="953f4-109">Mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où se trouve un téléphone de partie commune).</span><span class="sxs-lookup"><span data-stu-id="953f4-109">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>
    
- <span data-ttu-id="953f4-110">Mettez un appel en attente et maintenez le téléphone de répondage d’origine gratuit pour les autres appels.</span><span class="sxs-lookup"><span data-stu-id="953f4-110">Put a call on hold and keep the original answering phone free for other calls.</span></span>
    
<span data-ttu-id="953f4-111">Lorsqu’un utilisateur pare un appel, Skype Entreprise Server transfère l’appel vers un numéro temporaire, appelé orbite, où l’appel est mis en attente jusqu’à ce qu’il soit récupéré ou qu’il n’sorte pas. Skype Entreprise Server envoie l’orbite à l’utilisateur qui a par parcé l’appel.</span><span class="sxs-lookup"><span data-stu-id="953f4-111">When a user parks a call, Skype for Business Server transfers the call to a temporary number, called an orbit, where the call is held until it is retrieved or it times out. Skype for Business Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="953f4-112">Pour récupérer l’appel par parcé, l’utilisateur peut composer le numéro d’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.</span><span class="sxs-lookup"><span data-stu-id="953f4-112">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span> 
  
<span data-ttu-id="953f4-113">L’utilisateur qui a par parcé un appel peut avertir quelqu’un de récupérer l’appel à l’aide d’un mécanisme externe, tel que la messagerie instantanée ou un système de pagination, pour communiquer le numéro d’orbite à une autre personne.</span><span class="sxs-lookup"><span data-stu-id="953f4-113">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else.</span></span> <span data-ttu-id="953f4-114">L’utilisateur qui a paré l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification lorsque l’appel est récupéré.</span><span class="sxs-lookup"><span data-stu-id="953f4-114">The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>
  
<span data-ttu-id="953f4-115">Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer des appels à partir d’un site Skype Entreprise Server ou d’un téléphone PBX si le routage est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="953f4-115">Because orbit ranges are globally unique, it is possible to retrieve calls from any Skype for Business Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="953f4-116">Si personne ne récupère l’appel dans un laps de temps configurable, l’appel revient à la personne qui l’a par parcé.</span><span class="sxs-lookup"><span data-stu-id="953f4-116">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="953f4-117">Si cette personne ne répond pas à la sonnerie, l’appel est transféré vers une destination de récupération, par exemple un opérateur, si tel est le cas.</span><span class="sxs-lookup"><span data-stu-id="953f4-117">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="953f4-118">Vous pouvez configurer le nombre de sonneries de l’appel avant d’être transféré d’une à dix fois.</span><span class="sxs-lookup"><span data-stu-id="953f4-118">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="953f4-119">Si personne ne répond à un appel transféré, l’appel est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="953f4-119">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="953f4-120">L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.</span><span class="sxs-lookup"><span data-stu-id="953f4-120">The orbit is freed when the call is retrieved or disconnected.</span></span>
  
<span data-ttu-id="953f4-121">Lorsque vous déployez le parc d’appel, vous devez réserver des plages de numéros de poste pour le parc d’appels.</span><span class="sxs-lookup"><span data-stu-id="953f4-121">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="953f4-122">Ces extensions doivent être des extensions virtuelles : les extensions qui n’ont pas d’utilisateur ou de téléphone qui leur sont affectés.</span><span class="sxs-lookup"><span data-stu-id="953f4-122">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="953f4-123">Vous configurez ensuite la table des orbites de parcage d’appel avec les plages de numéros de poste et spécifiez le service d’application qui héberge l’application de parcage d’appel qui gère chaque plage.</span><span class="sxs-lookup"><span data-stu-id="953f4-123">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="953f4-124">Chaque pool frontal dispose d’une table de parcage d’appel sur le serveur principal correspondant qui est utilisée pour gérer les appels parés sur le pool.</span><span class="sxs-lookup"><span data-stu-id="953f4-124">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="953f4-125">La liste des plages d’orbites est stockée dans le magasin central de gestion et sert à router les orbites vers le pool de destination.</span><span class="sxs-lookup"><span data-stu-id="953f4-125">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="953f4-126">Chaque pool Skype Entreprise Server où l’application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites.</span><span class="sxs-lookup"><span data-stu-id="953f4-126">Each Skype for Business Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="953f4-127">Les plages d’orbites doivent être globalement uniques dans le déploiement de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="953f4-127">Orbit ranges must be globally unique across the Skype for Business Server deployment.</span></span> 
  
<span data-ttu-id="953f4-128">Vous configurez également d’autres paramètres de parcment d’appel, tels que l’endroit où les appels sont redirigés s’ils sont hors délai et si la personne qui se trouve sur le téléphone entend de la musique pendant le parc.</span><span class="sxs-lookup"><span data-stu-id="953f4-128">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked.</span></span> <span data-ttu-id="953f4-129">Vous pouvez également spécifier le fichier de musique à lire pendant l’attente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="953f4-129">You can also specify the music file to play while the call is on hold.</span></span>
  
> [!NOTE]
> <span data-ttu-id="953f4-130">Les fichiers d’attente musicale personnalisés pour le parcage d’appel ne sont pas pris en charge dans le cadre du processus de récupération d’urgence de Skype Entreprise Server et seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés.</span><span class="sxs-lookup"><span data-stu-id="953f4-130">Customized music-on-hold files for Call Park are not backed up as part of the Skype for Business Server disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="953f4-131">Conservez toujours une copie de sauvegarde distincte des fichiers d’attente musicale personnalisés que vous avez téléchargés pour le parcement d’appel.</span><span class="sxs-lookup"><span data-stu-id="953f4-131">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span> 
  
<span data-ttu-id="953f4-132">L’application de parcage d’appel est un composant de Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="953f4-132">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="953f4-133">Lorsque vous déployez Voix Entreprise, l’application de parcage d’appel est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="953f4-133">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="953f4-134">Toutefois, avant de pouvoir utiliser le parcier d’appel, l’administrateur Voix Entreprise doit le configurer et l’activer pour les utilisateurs par le biais d’une stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="953f4-134">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>
  
## <a name="deployment-and-requirements"></a><span data-ttu-id="953f4-135">Déploiement et conditions requises</span><span class="sxs-lookup"><span data-stu-id="953f4-135">Deployment and requirements</span></span>

<span data-ttu-id="953f4-136">L’application de parcage d’appel est installée automatiquement lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="953f4-136">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="953f4-137">Vous activez le parcage d’appel en configurant la stratégie de voix.</span><span class="sxs-lookup"><span data-stu-id="953f4-137">You enable Call Park by configuring voice policy.</span></span>
  
### <a name="software-requirements"></a><span data-ttu-id="953f4-138">Configuration logicielle requise</span><span class="sxs-lookup"><span data-stu-id="953f4-138">Software requirements</span></span>

<span data-ttu-id="953f4-139">Le runtime du format Windows Media doit être installé sur tous les serveurs frontaux et Standard Edition Server sur lequel le parcage d’appel est déployé pour les serveurs exécutant Windows Server 2008 R2 ou Microsoft Media Foundation pour les serveurs exécutant Windows Server 2012 ou Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="953f4-139">All Front End Servers and Standard Edition servers where Call Park is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="953f4-140">Pour Windows Server 2008 R2, le runtime du format Windows Media est installé dans le cadre de l’expérience de bureau Windows.</span><span class="sxs-lookup"><span data-stu-id="953f4-140">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="953f4-141">Windows Media Format Runtime ou Microsoft Media Foundation est requis pour les fichiers Audio Windows Media (.wma) que le parcage d’appel lit pour l’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="953f4-141">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>
  
### <a name="port-requirements"></a><span data-ttu-id="953f4-142">Conditions requises en matière de ports</span><span class="sxs-lookup"><span data-stu-id="953f4-142">Port requirements</span></span>

<span data-ttu-id="953f4-143">L’application de parcage d’appel **utilise le port 5075 pour**  les demandes d’écoute SIP.</span><span class="sxs-lookup"><span data-stu-id="953f4-143">The Call Park application uses **Port 5075**  for SIP listening requests.</span></span>
    
> [!NOTE]
> <span data-ttu-id="953f4-144">Ce port est un paramètre par défaut que vous pouvez modifier à l’aide de l’applet de commande **Set-CsApplicationServer**.</span><span class="sxs-lookup"><span data-stu-id="953f4-144">This port is a default setting that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="953f4-145">Pour plus d’informations sur cette cmdlet, voir la documentation de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="953f4-145">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>
  
### <a name="audio-file-requirements"></a><span data-ttu-id="953f4-146">Conditions requises pour les fichiers audio</span><span class="sxs-lookup"><span data-stu-id="953f4-146">Audio File requirements</span></span>

<span data-ttu-id="953f4-147">L’application de parcage d’appel prend uniquement en charge les fichiers Audio Windows Media (.wma) pour l’attente musicale.</span><span class="sxs-lookup"><span data-stu-id="953f4-147">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="953f4-148">Pour personnaliser les fichiers d’attente musicale, vous pouvez utiliser Microsoft Expression Encoder 4.</span><span class="sxs-lookup"><span data-stu-id="953f4-148">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="953f4-149">Pour télécharger Expression Encoder 4, voir   [« Expression Encoder 4](https://go.microsoft.com/fwlink/p/?linkId=202843)».</span><span class="sxs-lookup"><span data-stu-id="953f4-149">To download Expression Encoder 4, see   ["Expression Encoder 4"](https://go.microsoft.com/fwlink/p/?linkId=202843).</span></span> <span data-ttu-id="953f4-150">Utilisez l’outil pour convertir le fichier au format .wma.</span><span class="sxs-lookup"><span data-stu-id="953f4-150">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="953f4-151">Le format recommandé des fichiers d’attente musicale pour le parcage d’appel est Windows Media Audio 9,44 kHz, 16 bits, Mono, CBR, 32 Kbits/s.</span><span class="sxs-lookup"><span data-stu-id="953f4-151">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>
  
> [!NOTE]
> <span data-ttu-id="953f4-152">Le fichier converti est lu à 16 kHz sur le téléphone, même s’il a été enregistré à 44 kHz.</span><span class="sxs-lookup"><span data-stu-id="953f4-152">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span> 
  
## <a name="supported-clients-and-calls"></a><span data-ttu-id="953f4-153">Appels et clients pris en charge</span><span class="sxs-lookup"><span data-stu-id="953f4-153">Supported clients and calls</span></span>

<span data-ttu-id="953f4-154">Les clients et types d’appels suivants sont pris en charge pour le parc d’appel</span><span class="sxs-lookup"><span data-stu-id="953f4-154">The following clients and types of calls are supported for Call Park</span></span>
  
### <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="953f4-155">Clients pris en charge pour le parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="953f4-155">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="953f4-156">Les appels de n’importe quel téléphone IP, PBX (autocommutateur privé), RTC (réseau téléphonique commuté) ou mobile peuvent être parqués.</span><span class="sxs-lookup"><span data-stu-id="953f4-156">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>
  
> [!NOTE]
> <span data-ttu-id="953f4-p114">Seuls les appels audio peuvent être parqués. Aucun parcage pour les messages instantanés et les conférences n’est possible.</span><span class="sxs-lookup"><span data-stu-id="953f4-p114">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span> 
  
<span data-ttu-id="953f4-159">Les clients suivants peuvent utiliser le parcier d’appel pour parer les appels :</span><span class="sxs-lookup"><span data-stu-id="953f4-159">The following clients can use Call Park to park calls:</span></span>
  
- <span data-ttu-id="953f4-160">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="953f4-160">Skype for Business</span></span>
    
- <span data-ttu-id="953f4-161">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="953f4-161">Lync 2013</span></span>
    
- <span data-ttu-id="953f4-162">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="953f4-162">Lync 2010</span></span>
    
- <span data-ttu-id="953f4-163">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="953f4-163">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="953f4-164">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="953f4-164">Lync Phone Edition</span></span>
    
> [!NOTE]
> <span data-ttu-id="953f4-165">Les téléphones mobiles ne peuvent pas utiliser le parcier d’appel pour parer les appels.</span><span class="sxs-lookup"><span data-stu-id="953f4-165">Mobile phones cannot use Call Park to park calls.</span></span> 
  
### <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="953f4-166">Clients pris en charge pour la récupération des appels</span><span class="sxs-lookup"><span data-stu-id="953f4-166">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="953f4-p115">Les plages d’orbites sont configurées en tant que blocs de postes virtuels (postes sans utilisateur ou téléphone attribué). Lorsque vous configurez des orbites sous la forme de postes virtuels, les téléphones mobiles et RTC ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="953f4-p115">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="953f4-169">Les utilisateurs fédérés ne peuvent pas récupérer des appels parqués.</span><span class="sxs-lookup"><span data-stu-id="953f4-169">Federated users cannot retrieve parked calls.</span></span>
  
<span data-ttu-id="953f4-170">Les clients suivants peuvent récupérer les appels par parcés dans le parc d’appel :</span><span class="sxs-lookup"><span data-stu-id="953f4-170">The following clients can retrieve calls that are parked on Call Park:</span></span>
  
- <span data-ttu-id="953f4-171">Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="953f4-171">Skype for Business</span></span>
    
- <span data-ttu-id="953f4-172">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="953f4-172">Lync 2013</span></span>
    
- <span data-ttu-id="953f4-173">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="953f4-173">Lync 2010</span></span>
    
- <span data-ttu-id="953f4-174">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="953f4-174">Lync 2010 Attendant</span></span>
    
- <span data-ttu-id="953f4-175">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="953f4-175">Lync Phone Edition</span></span>
    
- <span data-ttu-id="953f4-176">Téléphones de partie commune IP</span><span class="sxs-lookup"><span data-stu-id="953f4-176">IP common area phones</span></span>
    
- <span data-ttu-id="953f4-177">Téléphones non IP connectés à l’infrastructure Skype Entreprise Server, y compris les téléphones de partie commune et les téléphones PBX (private branch exchange)</span><span class="sxs-lookup"><span data-stu-id="953f4-177">Non-IP phones that are connected to the Skype for Business Server infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>
    
## <a name="call-park-capacity-planning"></a><span data-ttu-id="953f4-178">Planification de la capacité du parcier d’appel</span><span class="sxs-lookup"><span data-stu-id="953f4-178">Call Park capacity planning</span></span>

<span data-ttu-id="953f4-179">Le tableau suivant décrit le modèle utilisateur du parc d’appel que vous pouvez utiliser comme base pour les besoins de planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="953f4-179">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="953f4-180">N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel dans les deux pools.</span><span class="sxs-lookup"><span data-stu-id="953f4-180">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span> 
  
<span data-ttu-id="953f4-181">**Modèle utilisateur de parcage d’appel**</span><span class="sxs-lookup"><span data-stu-id="953f4-181">**Call Park User Model**</span></span>

|<span data-ttu-id="953f4-182">**Métrique**</span><span class="sxs-lookup"><span data-stu-id="953f4-182">**Metric**</span></span>|<span data-ttu-id="953f4-183">**Par pool frontal  <br/>  (avec 8 serveurs frontux)**</span><span class="sxs-lookup"><span data-stu-id="953f4-183">**Per Front End pool  <br/>  (with 8 Front End Servers)**</span></span>|<span data-ttu-id="953f4-184">**Par serveur Standard Edition**</span><span class="sxs-lookup"><span data-stu-id="953f4-184">**Per Standard Edition server**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="953f4-185">Taux de parcage</span><span class="sxs-lookup"><span data-stu-id="953f4-185">Park rate</span></span>  <br/> |<span data-ttu-id="953f4-186">8 par minute</span><span class="sxs-lookup"><span data-stu-id="953f4-186">8 per minute</span></span>  <br/> |<span data-ttu-id="953f4-187">1 par minute</span><span class="sxs-lookup"><span data-stu-id="953f4-187">1 per minute</span></span>  <br/> |
|<span data-ttu-id="953f4-188">Taux d’appels parqués récupérés</span><span class="sxs-lookup"><span data-stu-id="953f4-188">Retrieve parked call rate</span></span>  <br/> |<span data-ttu-id="953f4-189">8 par minute</span><span class="sxs-lookup"><span data-stu-id="953f4-189">8 per minute</span></span>  <br/> |<span data-ttu-id="953f4-190">1 par minute</span><span class="sxs-lookup"><span data-stu-id="953f4-190">1 per minute</span></span>  <br/> |
|<span data-ttu-id="953f4-191">Durée moyenne de parcage</span><span class="sxs-lookup"><span data-stu-id="953f4-191">Average park duration</span></span>  <br/> |<span data-ttu-id="953f4-192">60 secondes</span><span class="sxs-lookup"><span data-stu-id="953f4-192">60 seconds</span></span>  <br/> |<span data-ttu-id="953f4-193">60 secondes</span><span class="sxs-lookup"><span data-stu-id="953f4-193">60 seconds</span></span>  <br/> |
   

