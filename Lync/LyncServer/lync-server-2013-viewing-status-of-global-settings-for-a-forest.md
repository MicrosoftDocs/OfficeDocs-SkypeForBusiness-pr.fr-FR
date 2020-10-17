---
title: 'Lync Server 2013 : affichage de l’état des paramètres globaux d’une forêt'
description: 'Lync Server 2013 : affichage de l’état des paramètres globaux d’une forêt.'
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
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567590"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="8b90a-103">Afficher l’état des paramètres globaux d’une forêt dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b90a-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b90a-104">_**Dernière modification de la rubrique :** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="8b90a-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="8b90a-105">Les administrateurs doivent consulter les paramètres globaux d’un déploiement de Lync Server 2013 tous les mois.</span><span class="sxs-lookup"><span data-stu-id="8b90a-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="8b90a-106">L’objectif consiste à passer en revue les paramètres implémentés par rapport à un ensemble de configurations connues, une configuration de référence pour garantir la validité des paramètres et déterminer si la documentation de référence doit être mise à jour.</span><span class="sxs-lookup"><span data-stu-id="8b90a-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="8b90a-107">Les modifications apportées au paramètre global doivent être implémentées par le biais d’un processus de contrôle des modifications qui doit inclure la documentation des nouveaux paramètres.</span><span class="sxs-lookup"><span data-stu-id="8b90a-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="8b90a-108">Les paramètres globaux à examiner sont décrits dans les sections suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b90a-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="8b90a-109">Vérifier les paramètres généraux</span><span class="sxs-lookup"><span data-stu-id="8b90a-109">Check general settings</span></span>

<span data-ttu-id="8b90a-110">Vérifiez les paramètres généraux, y compris les domaines SIP (Session Initiation Protocol) pris en charge pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b90a-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="8b90a-111">Les informations de domaine SIP peuvent être renvoyées à l’aide de Windows PowerShell et de la cmdlet **Get-CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="8b90a-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="8b90a-112">Pour renvoyer ces informations, exécutez la `Get-CsSipDomain` commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b90a-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="8b90a-113">Get-CsSipDomain renverra des informations similaires à celles-ci pour tous les domaines SIP autorisés :</span><span class="sxs-lookup"><span data-stu-id="8b90a-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="8b90a-114">Nom d’identité IsDefault</span><span class="sxs-lookup"><span data-stu-id="8b90a-114">Identity Name IsDefault</span></span>

<span data-ttu-id="8b90a-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="8b90a-115">\-------- ---- ---------</span></span>

<span data-ttu-id="8b90a-116">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="8b90a-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="8b90a-117">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="8b90a-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="8b90a-118">Si la propriété IsDefault est définie sur true, le domaine correspondant est votre domaine SIP par défaut.</span><span class="sxs-lookup"><span data-stu-id="8b90a-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="8b90a-119">Vous pouvez utiliser l’applet de commande Set-CsSipDomain pour modifier le domaine SIP par défaut de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8b90a-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="8b90a-120">Toutefois, vous ne pouvez pas supprimer simplement le domaine SIP par défaut car cela vous laissera sans domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="8b90a-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="8b90a-121">Si vous souhaitez supprimer le domaine fabrikam.com (comme indiqué dans l’exemple précédent), vous devez d’abord configurer na.fabrikam.com comme domaine par défaut.</span><span class="sxs-lookup"><span data-stu-id="8b90a-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="8b90a-122">Vérifier les paramètres de réunion</span><span class="sxs-lookup"><span data-stu-id="8b90a-122">Check meeting settings</span></span>

<span data-ttu-id="8b90a-123">Les paramètres de réunion incluent les définitions des stratégies de réunion et la prise en charge de la participation des utilisateurs anonymes aux réunions.</span><span class="sxs-lookup"><span data-stu-id="8b90a-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="8b90a-124">Les paramètres de configuration de réunion peuvent être récupérés à l’aide de Windows PowerShell et de la cmdlet **Get-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8b90a-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="8b90a-125">Par exemple, cette commande renvoie des informations sur les paramètres de configuration de réunion globale :</span><span class="sxs-lookup"><span data-stu-id="8b90a-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="8b90a-126">Get-CsMeetingConfiguration – les paramètres de configuration de réunion « globale » peuvent également être configurés au niveau de l’étendue site.</span><span class="sxs-lookup"><span data-stu-id="8b90a-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="8b90a-127">Pour cette raison, vous pouvez utiliser la commande suivante, qui retourne des informations sur tous les paramètres de configuration de réunion :</span><span class="sxs-lookup"><span data-stu-id="8b90a-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="8b90a-128">La cmdlet **Get-CsMeetingConfiguration** renvoie des informations semblables aux suivantes :</span><span class="sxs-lookup"><span data-stu-id="8b90a-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="8b90a-129">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-129">Identity : Global</span></span>

<span data-ttu-id="8b90a-130">PstnCallersBypassLobby : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="8b90a-131">EnableAssignedConferenceType : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="8b90a-132">DesignateAsPresenter : Company</span><span class="sxs-lookup"><span data-stu-id="8b90a-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="8b90a-133">AssignedConferenceTypeByDefault : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="8b90a-134">AdmitAnonymousUsersByDefault : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="8b90a-135">Encore une fois, le dernier élément de la liste, **AdmitAnonymousUsersByDefault**, active ou désactive la possibilité pour les utilisateurs anonymes de participer à des réunions.</span><span class="sxs-lookup"><span data-stu-id="8b90a-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="8b90a-136">Lors de la vérification des paramètres de configuration de réunion, il peut s’avérer utile de comparer les paramètres actuels et les équivalents par défaut.</span><span class="sxs-lookup"><span data-stu-id="8b90a-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="8b90a-137">Vous pouvez afficher les paramètres de configuration de réunion par défaut en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8b90a-138">La commande précédente crée une instance en mémoire uniquement des paramètres de configuration de réunion globaux, une instance qui utilise la valeur par défaut pour chaque propriété.</span><span class="sxs-lookup"><span data-stu-id="8b90a-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="8b90a-139">Aucun paramètre de configuration de réunion réel n’est créé lors de l’exécution de la commande.</span><span class="sxs-lookup"><span data-stu-id="8b90a-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="8b90a-140">Toutefois, toutes les valeurs de propriété par défaut sont affichées à l’écran.</span><span class="sxs-lookup"><span data-stu-id="8b90a-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="8b90a-141">Vérifier les serveurs Edge et leurs paramètres</span><span class="sxs-lookup"><span data-stu-id="8b90a-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="8b90a-142">Les informations de serveur Edge peuvent être récupérées à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b90a-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="8b90a-143">Cette commande retourne des informations sur tous les serveurs Edge configurés pour être utilisés dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="8b90a-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="8b90a-144">Les informations renvoyées incluent tous les paramètres de nom de domaine complet et de port pour chaque serveur Edge :</span><span class="sxs-lookup"><span data-stu-id="8b90a-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="8b90a-145">Identity : EdgeServer : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="8b90a-146">Serveur d’inscriptions : serveur d’inscriptions : LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="8b90a-147">AccessEdgeInternalSipPort : 5061</span><span class="sxs-lookup"><span data-stu-id="8b90a-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="8b90a-148">AccessEdgeExternalSipPort : 5061</span><span class="sxs-lookup"><span data-stu-id="8b90a-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="8b90a-149">AccessEdgeClientPort : 443</span><span class="sxs-lookup"><span data-stu-id="8b90a-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="8b90a-150">DataPsomServerPort : 8057</span><span class="sxs-lookup"><span data-stu-id="8b90a-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="8b90a-151">DataPsomClientPort : 444</span><span class="sxs-lookup"><span data-stu-id="8b90a-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="8b90a-152">MediaRelayAuthEdgePort : 5062</span><span class="sxs-lookup"><span data-stu-id="8b90a-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="8b90a-153">MediaRelayAuthInternalTurnTcpPort : 443</span><span class="sxs-lookup"><span data-stu-id="8b90a-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="8b90a-154">MediaRelayAuthExternalTurnTcpPort : 445</span><span class="sxs-lookup"><span data-stu-id="8b90a-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="8b90a-155">MediaRelayAuthInternalTurnUdpPort : 3478</span><span class="sxs-lookup"><span data-stu-id="8b90a-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="8b90a-156">MediaRelayAuthExternalTurnUdpPort : 3478</span><span class="sxs-lookup"><span data-stu-id="8b90a-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="8b90a-157">MediaCommunicationPortStart : 50000</span><span class="sxs-lookup"><span data-stu-id="8b90a-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="8b90a-158">MediaComunicationPortCount : 10000</span><span class="sxs-lookup"><span data-stu-id="8b90a-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="8b90a-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8b90a-160">DataEdgeExternalFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8b90a-161">AVEdgeExternalFqdn :</span><span class="sxs-lookup"><span data-stu-id="8b90a-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="8b90a-162">InternalInterfaceFqdn :</span><span class="sxs-lookup"><span data-stu-id="8b90a-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="8b90a-163">ExternalMrasFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8b90a-164">DependentServiceList : {Registrar : LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="8b90a-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="8b90a-165">Conferenceserver : LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="8b90a-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="8b90a-166">com, MediationServer : LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="8b90a-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="8b90a-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="8b90a-167">fabrikam.com}</span></span>

<span data-ttu-id="8b90a-168">ServiceId : fabrikam.com-EdgeServer-2</span><span class="sxs-lookup"><span data-stu-id="8b90a-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="8b90a-169">SiteId : site :fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="8b90a-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="8b90a-170">PoolFqdn : dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8b90a-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="8b90a-171">Version : 5</span><span class="sxs-lookup"><span data-stu-id="8b90a-171">Version : 5</span></span>

<span data-ttu-id="8b90a-172">Rôle : EdgeServer</span><span class="sxs-lookup"><span data-stu-id="8b90a-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="8b90a-173">Vérifier les paramètres de Fédération</span><span class="sxs-lookup"><span data-stu-id="8b90a-173">Check federation settings</span></span>

<span data-ttu-id="8b90a-174">Vérifier les paramètres de Fédération, par exemple, si elle est configurée et, si la réponse est « oui », le nom de domaine complet et le port.</span><span class="sxs-lookup"><span data-stu-id="8b90a-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="8b90a-175">La Fédération est activée et désactivée à l’aide de la collection globale des paramètres de configuration du serveur Edge d’accès.</span><span class="sxs-lookup"><span data-stu-id="8b90a-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="8b90a-176">Cela signifie, entre autres, que la Fédération est configurée sur une base tout ou rien : soit la Fédération est activée pour l’ensemble de l’organisation, soit la Fédération est désactivée pour l’ensemble de l’Organisation</span><span class="sxs-lookup"><span data-stu-id="8b90a-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="8b90a-177">Vos paramètres de configuration du serveur Edge d’accès peuvent être renvoyés à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b90a-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="8b90a-178">Pour ce faire, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="8b90a-179">À son tour, cette commande renvoie des données semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="8b90a-180">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-180">Identity : Global</span></span>

<span data-ttu-id="8b90a-181">AllowAnonymousUsers : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="8b90a-182">AllowFederatedUsers : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="8b90a-183">AllowOutsideUsers : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="8b90a-184">To ClearingHouse : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-184">BeClearingHouse : False</span></span>

<span data-ttu-id="8b90a-185">EnablePartnerDiscovery : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="8b90a-186">EnableArchivingDisclaimer : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="8b90a-187">KeepCrlsUpToDateForPeers : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="8b90a-188">MarkSourceVerifiableOnOutgoingMessages : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="8b90a-189">OutgoingTlsCountForFederatedPartners : 4</span><span class="sxs-lookup"><span data-stu-id="8b90a-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="8b90a-190">RoutingMethod : UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="8b90a-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="8b90a-191">Si la propriété **AllowFederatedUsers** est définie sur true, cela signifie que la Fédération est activée pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="8b90a-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="8b90a-192">(Définir **AllowFederatedUsers** sur true signifie également que, dans un scénario de domaine fractionné, vos utilisateurs locaux pourront communiquer de façon transparente avec vos utilisateurs dans le Cloud.)</span><span class="sxs-lookup"><span data-stu-id="8b90a-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="8b90a-193">Pour récupérer le nom de domaine complet et les paramètres de port de votre serveur Edge, reportez-vous à la tâche précédente (serveurs Edge et leurs paramètres).</span><span class="sxs-lookup"><span data-stu-id="8b90a-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="8b90a-194">L’activation de la Fédération au niveau de l’étendue globale signifie que les utilisateurs peuvent éventuellement communiquer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="8b90a-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="8b90a-195">Pour déterminer si des utilisateurs individuels peuvent communiquer avec des utilisateurs fédérés, vous devez examiner la stratégie d’accès des utilisateurs externes attribuée à cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8b90a-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="8b90a-196">Les informations d’accès des utilisateurs externes peuvent être renvoyées à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b90a-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="8b90a-197">Par exemple, cette commande renvoie des informations sur la stratégie d’accès des utilisateurs externes globale :</span><span class="sxs-lookup"><span data-stu-id="8b90a-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="8b90a-198">Cette commande renvoie les informations de toutes les stratégies d’accès des utilisateurs externes :</span><span class="sxs-lookup"><span data-stu-id="8b90a-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="8b90a-199">Les informations renvoyées ressembleront à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-199">The returned information will resemble this:</span></span>

<span data-ttu-id="8b90a-200">Identity : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-200">Identity : False</span></span>

<span data-ttu-id="8b90a-201">Description</span><span class="sxs-lookup"><span data-stu-id="8b90a-201">Description :</span></span>

<span data-ttu-id="8b90a-202">EnableFederationAccess : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="8b90a-203">EnablePublicCloudAccess : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="8b90a-204">EnablePublicCloudAccessAudioVideoAccess : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="8b90a-205">EnableOutsideAccess : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="8b90a-206">Si **EnableFederationAccess** est défini sur true, les utilisateurs gérés par la stratégie donnée peuvent communiquer avec des utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="8b90a-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="8b90a-207">Vérifier les paramètres d’archivage</span><span class="sxs-lookup"><span data-stu-id="8b90a-207">Check archiving settings</span></span>

<span data-ttu-id="8b90a-208">Vérifier les paramètres d’archivage pour les communications internes et fédérées. Avant de vérifier les paramètres pour l’archivage interne et externe, vous devez vérifier que l’archivage est activé.</span><span class="sxs-lookup"><span data-stu-id="8b90a-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="8b90a-209">Les paramètres de configuration de l’archivage peuvent être vérifiés à l’aide de Windows PowerShell et de l’applet de commande Get-CsArchivingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="8b90a-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="8b90a-210">Notez que les paramètres d’archivage peuvent également être configurés au niveau de l’étendue site.</span><span class="sxs-lookup"><span data-stu-id="8b90a-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="8b90a-211">Pour renvoyer des informations sur tous les paramètres d’archivage, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="8b90a-212">L’applet de commande Get-CsArchivingConfiguration renvoie des données semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="8b90a-213">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-213">Identity : Global</span></span>

<span data-ttu-id="8b90a-214">EnableArchiving : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-214">EnableArchiving : False</span></span>

<span data-ttu-id="8b90a-215">EnablePurging : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-215">EnablePurging : False</span></span>

<span data-ttu-id="8b90a-216">PurgeExportedArchivesOnly : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="8b90a-217">BlockOnArchiveFailure : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="8b90a-218">KeepArchivingDataForDays : 14</span><span class="sxs-lookup"><span data-stu-id="8b90a-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="8b90a-219">PurgeHourOfDay : 2</span><span class="sxs-lookup"><span data-stu-id="8b90a-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="8b90a-220">Archiveduplicatemessages a : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="8b90a-221">CachePurgingInterval : 24</span><span class="sxs-lookup"><span data-stu-id="8b90a-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="8b90a-222">Si la propriété EnableArchiving est définie sur false, cela signifie qu’aucune session de communication ne sera archivée.</span><span class="sxs-lookup"><span data-stu-id="8b90a-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="8b90a-223">Si vous souhaitez archiver les sessions de messagerie instantanée uniquement, utilisez une commande comme celle qui suit pour activer l’archivage des sessions de messagerie instantanée :</span><span class="sxs-lookup"><span data-stu-id="8b90a-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="8b90a-224">Pour archiver les sessions de conférence et les sessions de messagerie instantanée, utilisez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="8b90a-225">Si vous souhaitez comparer vos paramètres d’archivage actuels et les paramètres par défaut, exécutez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8b90a-226">Cette commande crée une instance en mémoire uniquement des paramètres de configuration d’archivage globaux.</span><span class="sxs-lookup"><span data-stu-id="8b90a-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="8b90a-227">Il ne s’agit pas d’une collection réelle de paramètres utilisés par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b90a-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="8b90a-228">Toutefois, il affiche les valeurs par défaut pour toutes les propriétés de configuration de l’archivage.</span><span class="sxs-lookup"><span data-stu-id="8b90a-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="8b90a-229">Vous pouvez également utiliser cette commande pour renvoyer le nom de domaine complet de vos serveurs d’archivage :</span><span class="sxs-lookup"><span data-stu-id="8b90a-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="8b90a-230">Une fois que vous avez vérifié que l’archivage est activé, vous pouvez afficher vos stratégies d’archivage pour déterminer si les sessions de communication interne et externe sont en cours d’archivage.</span><span class="sxs-lookup"><span data-stu-id="8b90a-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="8b90a-231">Les informations de stratégie d’archivage peuvent être récupérées à l’aide de la cmdlet Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="8b90a-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="8b90a-232">Par exemple, cette commande renvoie des informations sur la stratégie d’archivage globale :</span><span class="sxs-lookup"><span data-stu-id="8b90a-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="8b90a-233">Étant donné que les stratégies d’archivage peuvent également être configurées au niveau du site et de l’étendue par utilisateur, vous pouvez également utiliser cette commande, qui retourne des informations sur toutes les stratégies d’archivage :</span><span class="sxs-lookup"><span data-stu-id="8b90a-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="8b90a-234">Les informations que vous recevez d' Get-CsArchivingPolicy ressemblent à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="8b90a-235">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-235">Identity : Global</span></span>

<span data-ttu-id="8b90a-236">Description</span><span class="sxs-lookup"><span data-stu-id="8b90a-236">Description :</span></span>

<span data-ttu-id="8b90a-237">ArchiveInternal : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-237">ArchiveInternal : False</span></span>

<span data-ttu-id="8b90a-238">ArchiveExternal : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-238">ArchiveExternal : False</span></span>

<span data-ttu-id="8b90a-239">Notez que, par défaut, l’archivage interne et externe est désactivé dans une stratégie d’archivage.</span><span class="sxs-lookup"><span data-stu-id="8b90a-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="8b90a-240">Vérifier les paramètres CDR</span><span class="sxs-lookup"><span data-stu-id="8b90a-240">Check CDR settings</span></span>

<span data-ttu-id="8b90a-241">Vérifiez les paramètres d’enregistrement des détails des appels (CDR) pour l’enregistrement des détails des appels d’égal à égal, de conférence et de conférence.</span><span class="sxs-lookup"><span data-stu-id="8b90a-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="8b90a-242">Des informations détaillées sur vos paramètres CDR peuvent être renvoyées à l’aide de la cmdlet **Get-applet cscdrconfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8b90a-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="8b90a-243">Par exemple, cette commande renvoie des informations sur la collection globale de paramètres de configuration CDR :</span><span class="sxs-lookup"><span data-stu-id="8b90a-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="8b90a-244">Étant donné que les enregistrements des détails des appels peuvent également être configurés au niveau de l’étendue site, vous pouvez également exécuter cette commande, qui retourne des informations sur tous les paramètres de configuration CDR :</span><span class="sxs-lookup"><span data-stu-id="8b90a-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="8b90a-245">L’applet de commande Get-CsCdrConfiguration renvoie des informations similaires à celles-ci pour chaque collection de paramètres de configuration CDR :</span><span class="sxs-lookup"><span data-stu-id="8b90a-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="8b90a-246">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-246">Identity : Global</span></span>

<span data-ttu-id="8b90a-247">EnableCDR : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-247">EnableCDR : True</span></span>

<span data-ttu-id="8b90a-248">EnablePurging : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-248">EnablePurging : True</span></span>

<span data-ttu-id="8b90a-249">KeepCallDetailForDays : 60</span><span class="sxs-lookup"><span data-stu-id="8b90a-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="8b90a-250">KeepErrorReportForDays : 60</span><span class="sxs-lookup"><span data-stu-id="8b90a-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="8b90a-251">PurgeHourOfDay : 2</span><span class="sxs-lookup"><span data-stu-id="8b90a-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="8b90a-252">Des informations similaires peuvent être renvoyées pour la surveillance QoE à l’aide de la cmdlet Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="8b90a-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="8b90a-253">Par exemple, cette commande renvoie des informations sur la collection globale des paramètres de configuration QoE :</span><span class="sxs-lookup"><span data-stu-id="8b90a-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="8b90a-254">Ces informations ressembleront à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-254">That information will resemble this:</span></span>

<span data-ttu-id="8b90a-255">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-255">Identity : Global</span></span>

<span data-ttu-id="8b90a-256">ExternalConsumerIssuedCertId :</span><span class="sxs-lookup"><span data-stu-id="8b90a-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="8b90a-257">EnablePurging : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-257">EnablePurging : True</span></span>

<span data-ttu-id="8b90a-258">KeepQoEDataForDays : 60</span><span class="sxs-lookup"><span data-stu-id="8b90a-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="8b90a-259">PurgeHourOfDay : 1</span><span class="sxs-lookup"><span data-stu-id="8b90a-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="8b90a-260">EnableExternalConsumer : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="8b90a-261">ExternalConsumerName :</span><span class="sxs-lookup"><span data-stu-id="8b90a-261">ExternalConsumerName :</span></span>

<span data-ttu-id="8b90a-262">ExternalConsumerURL :</span><span class="sxs-lookup"><span data-stu-id="8b90a-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="8b90a-263">EnableQoE : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-263">EnableQoE : True</span></span>

<span data-ttu-id="8b90a-264">Si vous souhaitez comparer vos paramètres de CD-r actuels avec les paramètres CDR par défaut, vous pouvez examiner les valeurs par défaut en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8b90a-265">De même, les valeurs par défaut de la surveillance QoE peuvent être récupérées à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="8b90a-266">Vous pouvez également renvoyer le nom de domaine complet de vos serveurs de surveillance en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8b90a-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="8b90a-267">Vérifier les paramètres vocaux</span><span class="sxs-lookup"><span data-stu-id="8b90a-267">Check voice settings</span></span>

<span data-ttu-id="8b90a-268">Les paramètres vocaux généralement importants pour les administrateurs sont contenus dans des stratégies de voix et des itinéraires de communications vocales : les stratégies de voix contiennent les paramètres qui déterminent les fonctionnalités exposées aux utilisateurs individuels (comme la possibilité de transférer ou de transférer des appels), tandis que les itinéraires vocaux déterminent la façon dont les appels (et si) sont acheminés via le réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="8b90a-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="8b90a-269">Les informations de stratégie de voix peuvent être récupérées à l’aide de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b90a-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="8b90a-270">Par exemple, cette commande renvoie des informations sur la stratégie de voix globale :</span><span class="sxs-lookup"><span data-stu-id="8b90a-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="8b90a-271">Cette commande renvoie des informations sur toutes les stratégies de voix configurées pour être utilisées dans l’Organisation :</span><span class="sxs-lookup"><span data-stu-id="8b90a-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="8b90a-272">Les informations renvoyées par la cmdlet Get-CsVoicePolicy ressemblent à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="8b90a-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="8b90a-273">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-273">Identity : Global</span></span>

<span data-ttu-id="8b90a-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="8b90a-274">PstnUsages : {}</span></span>

<span data-ttu-id="8b90a-275">Description</span><span class="sxs-lookup"><span data-stu-id="8b90a-275">Description :</span></span>

<span data-ttu-id="8b90a-276">AllowSimulRing : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-276">AllowSimulRing : True</span></span>

<span data-ttu-id="8b90a-277">AllowCallForwarding : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="8b90a-278">AllowPSTNReRouting : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="8b90a-279">Nom : DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="8b90a-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="8b90a-280">EnableDelegation : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-280">EnableDelegation : True</span></span>

<span data-ttu-id="8b90a-281">EnableTeamCall : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-281">EnableTeamCall : True</span></span>

<span data-ttu-id="8b90a-282">EnableCallTransfer : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="8b90a-283">EnableCallPark : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-283">EnableCallPark : False</span></span>

<span data-ttu-id="8b90a-284">EnableMaliciousCallTracing : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="8b90a-285">EnableBWPolicyOverride : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="8b90a-286">PreventPSTNTollBypass : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="8b90a-287">Vous pouvez également créer des requêtes qui retournaient un sous-ensemble de vos stratégies de voix.</span><span class="sxs-lookup"><span data-stu-id="8b90a-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="8b90a-288">Par exemple, cette commande renvoie toutes les stratégies de voix qui autorisent le transfert d’appel :</span><span class="sxs-lookup"><span data-stu-id="8b90a-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="8b90a-289">Cette commande renvoie toutes les stratégies de voix qui n’autorisent pas le transfert d’appel :</span><span class="sxs-lookup"><span data-stu-id="8b90a-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="8b90a-290">Dans Windows PowerShell, utilisez l’applet de commande Get-CsVoiceRouting pour renvoyer des informations sur vos itinéraires vocaux :</span><span class="sxs-lookup"><span data-stu-id="8b90a-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="8b90a-291">Cette commande renvoie des informations comme celles-ci pour tous les itinéraires des communications vocales :</span><span class="sxs-lookup"><span data-stu-id="8b90a-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="8b90a-292">Identity : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="8b90a-292">Identity : LocalRoute</span></span>

<span data-ttu-id="8b90a-293">Priorité : 0</span><span class="sxs-lookup"><span data-stu-id="8b90a-293">Priority : 0</span></span>

<span data-ttu-id="8b90a-294">Description</span><span class="sxs-lookup"><span data-stu-id="8b90a-294">Description :</span></span>

<span data-ttu-id="8b90a-295">NumberPattern : ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="8b90a-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="8b90a-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="8b90a-296">PstnUsages : {}</span></span>

<span data-ttu-id="8b90a-297">PstnGatewayList : {}</span><span class="sxs-lookup"><span data-stu-id="8b90a-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="8b90a-298">Nom : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="8b90a-298">Name : LocalRoute</span></span>

<span data-ttu-id="8b90a-299">SuppressCallerId :</span><span class="sxs-lookup"><span data-stu-id="8b90a-299">SuppressCallerId :</span></span>

<span data-ttu-id="8b90a-300">AlternateCallerId :</span><span class="sxs-lookup"><span data-stu-id="8b90a-300">AlternateCallerId :</span></span>

<span data-ttu-id="8b90a-301">Lync Server vous permet de créer des itinéraires vocaux qui n’ont pas d’utilisation PSTN et qui ne spécifient pas de passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b90a-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="8b90a-302">Toutefois, vous ne pouvez pas acheminer les appels via un itinéraire des communications vocales pour lequel ces deux valeurs de propriétés ne sont pas configurées.</span><span class="sxs-lookup"><span data-stu-id="8b90a-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="8b90a-303">Pour cette raison, il peut s’avérer utile d’exécuter régulièrement cette commande, qui renvoie l’identité de n’importe quel itinéraire des communications vocales qui n’a pas d’utilisation PSTN :</span><span class="sxs-lookup"><span data-stu-id="8b90a-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="8b90a-304">De même, cette commande renvoie l’identité de tout itinéraire des communications vocales qui n’a pas été configuré pour disposer d’une passerelle PSTN :</span><span class="sxs-lookup"><span data-stu-id="8b90a-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="8b90a-305">Vérifier les paramètres du service de conférence</span><span class="sxs-lookup"><span data-stu-id="8b90a-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="8b90a-306">Vérifier les paramètres du service de conférence pour la Conférence rendez-vous PSTN.</span><span class="sxs-lookup"><span data-stu-id="8b90a-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="8b90a-307">Les paramètres du service de surveillance de conférence ne peuvent être récupérés qu’à l’aide de la cmdlet **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8b90a-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="8b90a-308">Ces paramètres ne sont pas disponibles dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b90a-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="8b90a-309">Pour afficher vos paramètres de surveillance des conférences, utilisez une commande Windows PowerShell semblable à la suivante, qui renvoie la collection globale des paramètres du service d’assistance de conférence :</span><span class="sxs-lookup"><span data-stu-id="8b90a-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="8b90a-310">Notez que les paramètres du service de surveillance de conférence peuvent également être configurés au niveau de l’étendue site.</span><span class="sxs-lookup"><span data-stu-id="8b90a-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="8b90a-311">Pour renvoyer des informations sur tous les paramètres du service de conférence, utilisez plutôt cette commande :</span><span class="sxs-lookup"><span data-stu-id="8b90a-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="8b90a-312">L’applet de commande Get-CsDialInConferencingConfiguration renvoie des données semblables à ceci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="8b90a-313">Identity : global</span><span class="sxs-lookup"><span data-stu-id="8b90a-313">Identity : Global</span></span>

<span data-ttu-id="8b90a-314">EntryExitAnnouncementsType : UseNames</span><span class="sxs-lookup"><span data-stu-id="8b90a-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="8b90a-315">EnableNameRecording : true</span><span class="sxs-lookup"><span data-stu-id="8b90a-315">EnableNameRecording : True</span></span>

<span data-ttu-id="8b90a-316">EntryExitAnnouncementsEnabledByDefault : false</span><span class="sxs-lookup"><span data-stu-id="8b90a-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="8b90a-317">Si EntryExitAnnouncementsEnabledByDefault est défini sur false, cela signifie que les annonces de conférence sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="8b90a-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="8b90a-318">Pour activer les annonces d’entrée et de sortie, exécutez une commande Windows PowerShell semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="8b90a-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b90a-319">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b90a-319">See Also</span></span>


[<span data-ttu-id="8b90a-320">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="8b90a-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="8b90a-321">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="8b90a-322">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8b90a-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="8b90a-323">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="8b90a-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="8b90a-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="8b90a-325">Get-applet csarchivingconfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="8b90a-326">Get-applet cscdrconfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="8b90a-327">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="8b90a-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="8b90a-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="8b90a-329">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="8b90a-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="8b90a-330">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8b90a-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

