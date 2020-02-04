---
title: 'Lync Server 2013 : affichage de l’état des paramètres globaux d’une forêt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec1dea4ad3d5052bc2ba23cccd9e19ab138414ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757228"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="d34f8-102">Afficher l’état des paramètres globaux pour une forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d34f8-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d34f8-103">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="d34f8-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="d34f8-104">Les administrateurs doivent vérifier les paramètres globaux d’un déploiement de Lync Server 2013 au mois.</span><span class="sxs-lookup"><span data-stu-id="d34f8-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="d34f8-105">L’objectif consiste à passer en revue des paramètres implémentés à l’aide d’un ensemble de configurations connues : une configuration de référence pour garantir que les paramètres soient valides et déterminez si la documentation de référence doit être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="d34f8-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="d34f8-106">Les modifications apportées au paramètre global doivent être implémentées par le biais d’un processus de contrôle des modifications qui devrait inclure la documentation des nouveaux paramètres.</span><span class="sxs-lookup"><span data-stu-id="d34f8-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="d34f8-107">Les paramètres globaux qui doivent être examinés sont décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="d34f8-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="d34f8-108">Vérifier les paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="d34f8-108">Check general settings</span></span>

<span data-ttu-id="d34f8-109">Vérifiez les paramètres généraux, y compris les domaines compatibles SIP (Session Initiation Protocol) pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d34f8-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="d34f8-110">Les informations de domaine SIP peuvent être renvoyées à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="d34f8-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="d34f8-111">Pour obtenir ces informations, exécutez la `Get-CsSipDomain` commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d34f8-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="d34f8-112">Get-CsSipDomain renverra des informations similaires à ce qui suit pour tous les domaines SIP autorisés :</span><span class="sxs-lookup"><span data-stu-id="d34f8-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="d34f8-113">Nom d’identité IsDefault</span><span class="sxs-lookup"><span data-stu-id="d34f8-113">Identity Name IsDefault</span></span>

<span data-ttu-id="d34f8-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="d34f8-114">\-------- ---- ---------</span></span>

<span data-ttu-id="d34f8-115">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="d34f8-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="d34f8-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="d34f8-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="d34f8-117">Si la propriété IsDefault est définie sur true, le domaine correspondant est le domaine SIP par défaut.</span><span class="sxs-lookup"><span data-stu-id="d34f8-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="d34f8-118">Vous pouvez utiliser l’applet de cmdlet Set-CsSipDomain pour modifier le domaine SIP par défaut de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d34f8-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="d34f8-119">Toutefois, vous ne pouvez pas supprimer le domaine SIP par défaut, car cela vous laisserait sans domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="d34f8-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="d34f8-120">Si vous souhaitez supprimer le domaine fabrikam.com (comme illustré dans l’exemple précédent), vous devez commencer par configurer na.fabrikam.com comme domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="d34f8-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="d34f8-121">Vérifier les paramètres de la réunion</span><span class="sxs-lookup"><span data-stu-id="d34f8-121">Check meeting settings</span></span>

<span data-ttu-id="d34f8-122">Les paramètres de réunion incluent les définitions de stratégie de réunion et la prise en charge de la participation d’utilisateurs anonymes à des réunions.</span><span class="sxs-lookup"><span data-stu-id="d34f8-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="d34f8-123">Les paramètres de configuration de réunion peuvent être récupérés à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d34f8-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="d34f8-124">Par exemple, la commande suivante renvoie des informations sur les paramètres de configuration de la réunion globale :</span><span class="sxs-lookup"><span data-stu-id="d34f8-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="d34f8-125">Get-CsMeetingConfiguration-Identity les paramètres de configuration de la réunion « global » peuvent également être configurés sur l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="d34f8-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="d34f8-126">Pour cette raison, vous souhaiterez peut-être utiliser la commande suivante qui renvoie des informations sur tous les paramètres de configuration de la réunion :</span><span class="sxs-lookup"><span data-stu-id="d34f8-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="d34f8-127">L’applet de commande **Get-CsMeetingConfiguration** renvoie des informations similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="d34f8-128">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-128">Identity : Global</span></span>

<span data-ttu-id="d34f8-129">PstnCallersBypassLobby : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="d34f8-130">EnableAssignedConferenceType : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="d34f8-131">DesignateAsPresenter : société</span><span class="sxs-lookup"><span data-stu-id="d34f8-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="d34f8-132">AssignedConferenceTypeByDefault : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="d34f8-133">AdmitAnonymousUsersByDefault : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="d34f8-134">Là encore, le dernier élément de la liste, **AdmitAnonymousUsersByDefault**, active ou désactive la possibilité pour les utilisateurs anonymes de participer aux réunions.</span><span class="sxs-lookup"><span data-stu-id="d34f8-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="d34f8-135">Lors de la vérification des paramètres de configuration de la réunion, vous trouverez peut-être utile de comparer les paramètres actuels par rapport aux équivalents par défaut.</span><span class="sxs-lookup"><span data-stu-id="d34f8-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="d34f8-136">Vous pouvez afficher les paramètres de configuration de la réunion par défaut en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d34f8-137">La commande précédente crée une instance en mémoire uniquement des paramètres de configuration de réunion globale, une instance qui utilise la valeur par défaut pour chaque propriété.</span><span class="sxs-lookup"><span data-stu-id="d34f8-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="d34f8-138">Aucun paramètre de configuration de réunion réel n’est créé lors de l’exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="d34f8-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="d34f8-139">Toutefois, toutes les valeurs de propriété par défaut s’affichent à l’écran.</span><span class="sxs-lookup"><span data-stu-id="d34f8-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="d34f8-140">Vérifier les serveurs Edge et leurs paramètres</span><span class="sxs-lookup"><span data-stu-id="d34f8-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="d34f8-141">Vous pouvez récupérer les informations sur le serveur Edge à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d34f8-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d34f8-142">Cette commande renvoie des informations sur tous les serveurs Edge configurés pour une utilisation au sein de votre organisation :</span><span class="sxs-lookup"><span data-stu-id="d34f8-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="d34f8-143">Les informations renvoyées incluent tous les paramètres de nom de domaine complet et de port de chaque serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="d34f8-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="d34f8-144">Identité : EdgeServer : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="d34f8-145">Bureau d’enregistrement : LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="d34f8-146">AccessEdgeInternalSipPort : 5061</span><span class="sxs-lookup"><span data-stu-id="d34f8-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="d34f8-147">AccessEdgeExternalSipPort : 5061</span><span class="sxs-lookup"><span data-stu-id="d34f8-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="d34f8-148">AccessEdgeClientPort : 443</span><span class="sxs-lookup"><span data-stu-id="d34f8-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="d34f8-149">DataPsomServerPort : 8057</span><span class="sxs-lookup"><span data-stu-id="d34f8-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="d34f8-150">DataPsomClientPort : 444</span><span class="sxs-lookup"><span data-stu-id="d34f8-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="d34f8-151">MediaRelayAuthEdgePort : 5062</span><span class="sxs-lookup"><span data-stu-id="d34f8-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="d34f8-152">MediaRelayAuthInternalTurnTcpPort : 443</span><span class="sxs-lookup"><span data-stu-id="d34f8-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="d34f8-153">MediaRelayAuthExternalTurnTcpPort : 445</span><span class="sxs-lookup"><span data-stu-id="d34f8-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="d34f8-154">MediaRelayAuthInternalTurnUdpPort : 3478</span><span class="sxs-lookup"><span data-stu-id="d34f8-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d34f8-155">MediaRelayAuthExternalTurnUdpPort : 3478</span><span class="sxs-lookup"><span data-stu-id="d34f8-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d34f8-156">MediaCommunicationPortStart : 50000</span><span class="sxs-lookup"><span data-stu-id="d34f8-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="d34f8-157">MediaComunicationPortCount : 10000</span><span class="sxs-lookup"><span data-stu-id="d34f8-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="d34f8-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d34f8-159">DataEdgeExternalFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d34f8-160">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="d34f8-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="d34f8-161">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="d34f8-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="d34f8-162">ExternalMrasFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d34f8-163">DependentServiceList : {Registrar : LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="d34f8-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="d34f8-164">ConferencingServer : LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="d34f8-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="d34f8-165">com, MediationServer : LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="d34f8-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="d34f8-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="d34f8-166">fabrikam.com}</span></span>

<span data-ttu-id="d34f8-167">ServiceId : fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="d34f8-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="d34f8-168">SiteId : site :fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="d34f8-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="d34f8-169">PoolFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d34f8-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d34f8-170">Version : 5</span><span class="sxs-lookup"><span data-stu-id="d34f8-170">Version : 5</span></span>

<span data-ttu-id="d34f8-171">Rôle : EdgeServer</span><span class="sxs-lookup"><span data-stu-id="d34f8-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="d34f8-172">Vérifier les paramètres de Fédération</span><span class="sxs-lookup"><span data-stu-id="d34f8-172">Check federation settings</span></span>

<span data-ttu-id="d34f8-173">Vérifiez les paramètres de Fédération (par exemple, s’il est configuré et, si la réponse est « oui »), les nom de domaine complet et port.</span><span class="sxs-lookup"><span data-stu-id="d34f8-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="d34f8-174">La Fédération est activée et désactivée à l’aide de l’ensemble global de paramètres de configuration de Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="d34f8-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="d34f8-175">Entre autres choses, cela signifie que la Fédération est configurée sur une base « tout-le » : une Fédération est activée pour l’ensemble de l’organisation ou la Fédération est désactivée pour l’ensemble de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="d34f8-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="d34f8-176">Les paramètres de configuration de Microsoft Edge peuvent être retournés à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d34f8-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d34f8-177">Pour cela, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="d34f8-178">Ensuite, cette commande renvoie des données similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="d34f8-179">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-179">Identity : Global</span></span>

<span data-ttu-id="d34f8-180">AllowAnonymousUsers : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="d34f8-181">AllowFederatedUsers : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="d34f8-182">AllowOutsideUsers : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="d34f8-183">Concentrez-vous : faux</span><span class="sxs-lookup"><span data-stu-id="d34f8-183">BeClearingHouse : False</span></span>

<span data-ttu-id="d34f8-184">EnablePartnerDiscovery : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="d34f8-185">EnableArchivingDisclaimer : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="d34f8-186">KeepCrlsUpToDateForPeers : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="d34f8-187">MarkSourceVerifiableOnOutgoingMessages : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="d34f8-188">OutgoingTlsCountForFederatedPartners : 4</span><span class="sxs-lookup"><span data-stu-id="d34f8-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="d34f8-189">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="d34f8-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="d34f8-190">Si la propriété **AllowFederatedUsers** est définie sur true, cela signifie que la Fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="d34f8-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="d34f8-191">(Si vous définissez la propriété **AllowFederatedUsers** sur true, dans un scénario de domaine fractionné, vos utilisateurs locaux pourront communiquer en toute transparence avec vos utilisateurs dans le Cloud.)</span><span class="sxs-lookup"><span data-stu-id="d34f8-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="d34f8-192">Pour récupérer les paramètres de nom de domaine complet et de port de votre serveur Edge, voir la tâche précédente (serveurs de bord et leurs paramètres).</span><span class="sxs-lookup"><span data-stu-id="d34f8-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="d34f8-193">L’activation de la Fédération au niveau de l’étendue globale signifie que les utilisateurs peuvent éventuellement communiquer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="d34f8-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="d34f8-194">Pour déterminer si des utilisateurs individuels peuvent communiquer avec des utilisateurs fédérés, vous devez examiner la stratégie d’accès des utilisateurs externes affectée à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d34f8-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="d34f8-195">Les informations d’accès des utilisateurs externes peuvent être renvoyées à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d34f8-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d34f8-196">Par exemple, cette commande renvoie des informations sur la stratégie globale d’accès des utilisateurs externes :</span><span class="sxs-lookup"><span data-stu-id="d34f8-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="d34f8-197">Cette commande renvoie des informations pour toutes les stratégies d’accès des utilisateurs externes :</span><span class="sxs-lookup"><span data-stu-id="d34f8-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="d34f8-198">Les informations renvoyées sont similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-198">The returned information will resemble this:</span></span>

<span data-ttu-id="d34f8-199">Identity : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-199">Identity : False</span></span>

<span data-ttu-id="d34f8-200">Description</span><span class="sxs-lookup"><span data-stu-id="d34f8-200">Description :</span></span>

<span data-ttu-id="d34f8-201">EnableFederationAccess : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="d34f8-202">EnablePublicCloudAccess : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="d34f8-203">EnablePublicCloudAccessAudioVideoAccess : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="d34f8-204">EnableOutsideAccess : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="d34f8-205">Si **EnableFederationAccess** est défini sur true, les utilisateurs gérés par la stratégie donnée peuvent communiquer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="d34f8-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="d34f8-206">Vérifier les paramètres d’archivage</span><span class="sxs-lookup"><span data-stu-id="d34f8-206">Check archiving settings</span></span>

<span data-ttu-id="d34f8-207">Vérifiez les paramètres d’archivage des communications internes et fédérées. Avant de vérifier les paramètres de l’archivage interne et externe, vérifiez que l’archivage est activé.</span><span class="sxs-lookup"><span data-stu-id="d34f8-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="d34f8-208">Les paramètres de configuration de l’archivage peuvent être vérifiés à l’aide de Windows PowerShell et de l’applet de passe Get-CsArchivingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="d34f8-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="d34f8-209">Notez que vous pouvez également configurer les paramètres d’archivage à l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="d34f8-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="d34f8-210">Pour renvoyer des informations sur les paramètres d’archivage, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="d34f8-211">L’applet de requête get-CsArchivingConfiguration renvoie des données similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d34f8-212">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-212">Identity : Global</span></span>

<span data-ttu-id="d34f8-213">EnableArchiving : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-213">EnableArchiving : False</span></span>

<span data-ttu-id="d34f8-214">EnablePurging : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-214">EnablePurging : False</span></span>

<span data-ttu-id="d34f8-215">PurgeExportedArchivesOnly : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="d34f8-216">BlockOnArchiveFailure : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="d34f8-217">KeepArchivingDataForDays : 14</span><span class="sxs-lookup"><span data-stu-id="d34f8-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="d34f8-218">PurgeHourOfDay : 2</span><span class="sxs-lookup"><span data-stu-id="d34f8-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d34f8-219">ArchiveDuplicateMessages : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="d34f8-220">CachePurgingInterval : 24</span><span class="sxs-lookup"><span data-stu-id="d34f8-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="d34f8-221">Si la propriété EnableArchiving est définie sur false, cela signifie qu’aucune session de communication n’est archivée.</span><span class="sxs-lookup"><span data-stu-id="d34f8-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="d34f8-222">Si vous voulez uniquement archiver des sessions de messagerie instantanée, utilisez une commande telle que celle qui suit pour activer l’archivage des sessions de messagerie instantanée :</span><span class="sxs-lookup"><span data-stu-id="d34f8-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d34f8-223">Pour archiver des sessions de conférence et des sessions de messagerie instantanée, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d34f8-224">Si vous souhaitez comparer vos paramètres d’archivage actuels avec les paramètres par défaut, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d34f8-225">Cette commande crée une instance en mémoire uniquement des paramètres de configuration de l’archivage global.</span><span class="sxs-lookup"><span data-stu-id="d34f8-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="d34f8-226">Ce n’est pas une collection réelle de paramètres qui est utilisée par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d34f8-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="d34f8-227">Toutefois, elle affiche les valeurs par défaut de toutes les propriétés de configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="d34f8-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="d34f8-228">Vous pouvez également utiliser cette commande pour renvoyer le nom de domaine complet de vos serveurs d’archivage :</span><span class="sxs-lookup"><span data-stu-id="d34f8-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="d34f8-229">Après vérification de l’activation de l’archivage, vous pouvez afficher vos politiques d’archivage pour déterminer si les sessions internes et externes de communication sont archivées.</span><span class="sxs-lookup"><span data-stu-id="d34f8-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="d34f8-230">Vous pouvez récupérer les informations de stratégie d’archivage à l’aide de l’applet de passe Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="d34f8-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="d34f8-231">Par exemple, cette commande renvoie des informations sur la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="d34f8-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="d34f8-232">Étant donné que les stratégies d’archivage peuvent également être configurées au niveau du site et de l’étendue par utilisateur, vous pouvez également utiliser cette commande pour renvoyer des informations sur toutes les stratégies d’archivage :</span><span class="sxs-lookup"><span data-stu-id="d34f8-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="d34f8-233">Les informations que vous recevez de Get-CsArchivingPolicy sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d34f8-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="d34f8-234">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-234">Identity : Global</span></span>

<span data-ttu-id="d34f8-235">Description</span><span class="sxs-lookup"><span data-stu-id="d34f8-235">Description :</span></span>

<span data-ttu-id="d34f8-236">ArchiveInternal : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-236">ArchiveInternal : False</span></span>

<span data-ttu-id="d34f8-237">ArchiveExternal : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-237">ArchiveExternal : False</span></span>

<span data-ttu-id="d34f8-238">Notez que, par défaut, l’archivage interne et externe est désactivé dans une stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="d34f8-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="d34f8-239">Vérifier les paramètres CDR</span><span class="sxs-lookup"><span data-stu-id="d34f8-239">Check CDR settings</span></span>

<span data-ttu-id="d34f8-240">Vérifiez les paramètres d’enregistrement des détails des appels (CDR) pour l’enregistrement des détails des appels d’égal à égal, de conférence et d’appel vocal.</span><span class="sxs-lookup"><span data-stu-id="d34f8-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="d34f8-241">Des informations détaillées sur vos paramètres CDR peuvent être renvoyées à l’aide de l’applet **de passe Get-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d34f8-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d34f8-242">Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration de CDR :</span><span class="sxs-lookup"><span data-stu-id="d34f8-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="d34f8-243">Comme CDR peut également être configuré sur l’étendue du site, vous souhaiterez peut-être également exécuter cette commande, qui renvoie des informations sur tous les paramètres de configuration de CDR :</span><span class="sxs-lookup"><span data-stu-id="d34f8-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="d34f8-244">L’applet de requête get-CsCdrConfiguration renvoie des informations similaires à ce qui suit pour chaque collection de paramètres de configuration CDR :</span><span class="sxs-lookup"><span data-stu-id="d34f8-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="d34f8-245">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-245">Identity : Global</span></span>

<span data-ttu-id="d34f8-246">EnableCDR : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-246">EnableCDR : True</span></span>

<span data-ttu-id="d34f8-247">EnablePurging : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-247">EnablePurging : True</span></span>

<span data-ttu-id="d34f8-248">KeepCallDetailForDays : 60</span><span class="sxs-lookup"><span data-stu-id="d34f8-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="d34f8-249">KeepErrorReportForDays : 60</span><span class="sxs-lookup"><span data-stu-id="d34f8-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="d34f8-250">PurgeHourOfDay : 2</span><span class="sxs-lookup"><span data-stu-id="d34f8-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d34f8-251">Des informations similaires peuvent être renvoyées pour la surveillance QoE en utilisant l’applet de requête get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d34f8-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="d34f8-252">Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration QoE :</span><span class="sxs-lookup"><span data-stu-id="d34f8-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="d34f8-253">Cette information ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="d34f8-253">That information will resemble this:</span></span>

<span data-ttu-id="d34f8-254">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-254">Identity : Global</span></span>

<span data-ttu-id="d34f8-255">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="d34f8-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="d34f8-256">EnablePurging : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-256">EnablePurging : True</span></span>

<span data-ttu-id="d34f8-257">KeepQoEDataForDays : 60</span><span class="sxs-lookup"><span data-stu-id="d34f8-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="d34f8-258">PurgeHourOfDay : 1</span><span class="sxs-lookup"><span data-stu-id="d34f8-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="d34f8-259">EnableExternalConsumer : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="d34f8-260">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="d34f8-260">ExternalConsumerName :</span></span>

<span data-ttu-id="d34f8-261">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="d34f8-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="d34f8-262">EnableQoE : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-262">EnableQoE : True</span></span>

<span data-ttu-id="d34f8-263">Si vous souhaitez comparer vos paramètres de CDR actuels avec les paramètres CDR par défaut, les valeurs par défaut peuvent être examinées en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d34f8-264">De même, les valeurs par défaut pour la surveillance QoE peuvent être récupérées à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d34f8-265">Vous pouvez également renvoyer le nom de domaine complet de vos serveurs de surveillance en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="d34f8-266">Vérifier les paramètres de la voix</span><span class="sxs-lookup"><span data-stu-id="d34f8-266">Check voice settings</span></span>

<span data-ttu-id="d34f8-267">Les paramètres vocaux sont généralement importants pour les administrateurs dans les politiques vocales et les itinéraires vocaux : les stratégies vocales contiennent les paramètres qui déterminent les fonctionnalités exposées aux utilisateurs individuels (par exemple, la possibilité de transférer ou de transférer les appels), tout en les itinéraires vocaux déterminent la manière dont les appels (et si) sont routés sur le RTC.</span><span class="sxs-lookup"><span data-stu-id="d34f8-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="d34f8-268">Les informations de la stratégie vocale peuvent être récupérées à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d34f8-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d34f8-269">Par exemple, la commande suivante renvoie des informations sur la politique vocale globale :</span><span class="sxs-lookup"><span data-stu-id="d34f8-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="d34f8-270">Cette commande renvoie des informations sur toutes les stratégies vocales configurées pour une utilisation au sein de l’Organisation :</span><span class="sxs-lookup"><span data-stu-id="d34f8-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="d34f8-271">Les informations renvoyées par la cmdlet Get-CsVoicePolicy sont similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="d34f8-272">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-272">Identity : Global</span></span>

<span data-ttu-id="d34f8-273">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="d34f8-273">PstnUsages : {}</span></span>

<span data-ttu-id="d34f8-274">Description</span><span class="sxs-lookup"><span data-stu-id="d34f8-274">Description :</span></span>

<span data-ttu-id="d34f8-275">AllowSimulRing : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-275">AllowSimulRing : True</span></span>

<span data-ttu-id="d34f8-276">AllowCallForwarding : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="d34f8-277">AllowPSTNReRouting : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="d34f8-278">Nom : DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="d34f8-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="d34f8-279">EnableDelegation : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-279">EnableDelegation : True</span></span>

<span data-ttu-id="d34f8-280">EnableTeamCall : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-280">EnableTeamCall : True</span></span>

<span data-ttu-id="d34f8-281">EnableCallTransfer : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="d34f8-282">EnableCallPark : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-282">EnableCallPark : False</span></span>

<span data-ttu-id="d34f8-283">EnableMaliciousCallTracing : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="d34f8-284">EnableBWPolicyOverride : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="d34f8-285">PreventPSTNTollBypass : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="d34f8-286">Vous pouvez également créer des requêtes qui renvoient un sous-ensemble de vos stratégies vocales.</span><span class="sxs-lookup"><span data-stu-id="d34f8-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="d34f8-287">Par exemple, cette commande renvoie toutes les stratégies vocales qui autorisent le transfert d’appel :</span><span class="sxs-lookup"><span data-stu-id="d34f8-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="d34f8-288">Ainsi, cette commande renvoie toutes les stratégies vocales qui n’autorisent pas le transfert d’appel :</span><span class="sxs-lookup"><span data-stu-id="d34f8-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="d34f8-289">Dans Windows PowerShell, vous pouvez utiliser l’applet de passe Get-CsVoiceRouting pour renvoyer des informations sur vos itinéraires vocaux :</span><span class="sxs-lookup"><span data-stu-id="d34f8-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="d34f8-290">Cette commande renvoie des informations telles que celle-ci pour tous les itinéraires vocaux :</span><span class="sxs-lookup"><span data-stu-id="d34f8-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="d34f8-291">Identité : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d34f8-291">Identity : LocalRoute</span></span>

<span data-ttu-id="d34f8-292">Priorité : 0</span><span class="sxs-lookup"><span data-stu-id="d34f8-292">Priority : 0</span></span>

<span data-ttu-id="d34f8-293">Description</span><span class="sxs-lookup"><span data-stu-id="d34f8-293">Description :</span></span>

<span data-ttu-id="d34f8-294">NumberPattern : ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="d34f8-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="d34f8-295">PstnUsages :{}</span><span class="sxs-lookup"><span data-stu-id="d34f8-295">PstnUsages : {}</span></span>

<span data-ttu-id="d34f8-296">PstnGatewayList :{}</span><span class="sxs-lookup"><span data-stu-id="d34f8-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="d34f8-297">Nom : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d34f8-297">Name : LocalRoute</span></span>

<span data-ttu-id="d34f8-298">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="d34f8-298">SuppressCallerId :</span></span>

<span data-ttu-id="d34f8-299">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="d34f8-299">AlternateCallerId :</span></span>

<span data-ttu-id="d34f8-300">Lync Server vous permet de créer des itinéraires vocaux sans utilisation PSTN et de ne spécifier aucune passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="d34f8-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="d34f8-301">Toutefois, vous ne pouvez pas acheminer les appels sur un itinéraire vocal qui ne possède pas les deux valeurs de propriété configurées.</span><span class="sxs-lookup"><span data-stu-id="d34f8-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="d34f8-302">Pour cette raison, il peut être utile d’exécuter cette commande de manière périodique, qui renvoie l’identité d’un itinéraire vocal sans utilisation RTC :</span><span class="sxs-lookup"><span data-stu-id="d34f8-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="d34f8-303">De même, cette commande renvoie l’identité d’un itinéraire vocal qui n’a pas été configuré pour avoir une passerelle RTC :</span><span class="sxs-lookup"><span data-stu-id="d34f8-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="d34f8-304">Vérifier les paramètres du surveillant de conférences</span><span class="sxs-lookup"><span data-stu-id="d34f8-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="d34f8-305">Vérifiez les paramètres du surveillant de conférences pour la Conférence rendez-vous PSTN.</span><span class="sxs-lookup"><span data-stu-id="d34f8-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="d34f8-306">Les paramètres du surveillant de conférences peuvent uniquement être récupérés à l’aide de l’applet de passe **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d34f8-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="d34f8-307">Ces paramètres ne sont pas disponibles dans le panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d34f8-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="d34f8-308">Pour afficher les paramètres de votre surveillant de conférences, utilisez une commande Windows PowerShell semblable à la suivante qui renvoie la collection globale de paramètres du surveillant de conférences :</span><span class="sxs-lookup"><span data-stu-id="d34f8-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="d34f8-309">Notez que les paramètres du surveillant de conférences peuvent également être configurés sur l’étendue du site.</span><span class="sxs-lookup"><span data-stu-id="d34f8-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="d34f8-310">Pour renvoyer des informations sur tous les paramètres du surveillant de conférences, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d34f8-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="d34f8-311">L’applet de requête get-CsDialInConferencingConfiguration renvoie des données similaires à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d34f8-312">Identity : global</span><span class="sxs-lookup"><span data-stu-id="d34f8-312">Identity : Global</span></span>

<span data-ttu-id="d34f8-313">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="d34f8-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="d34f8-314">EnableNameRecording : true</span><span class="sxs-lookup"><span data-stu-id="d34f8-314">EnableNameRecording : True</span></span>

<span data-ttu-id="d34f8-315">EntryExitAnnouncementsEnabledByDefault : false</span><span class="sxs-lookup"><span data-stu-id="d34f8-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="d34f8-316">Si EntryExitAnnouncementsEnabledByDefault est défini sur false, cela signifie que les annonces de conférences sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="d34f8-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="d34f8-317">Pour activer les annonces d’entrée et de sortie, exécutez une commande Windows PowerShell semblable à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="d34f8-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d34f8-318">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d34f8-318">See Also</span></span>


[<span data-ttu-id="d34f8-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="d34f8-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="d34f8-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="d34f8-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="d34f8-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d34f8-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="d34f8-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="d34f8-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="d34f8-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="d34f8-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="d34f8-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="d34f8-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="d34f8-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="d34f8-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="d34f8-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="d34f8-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d34f8-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

