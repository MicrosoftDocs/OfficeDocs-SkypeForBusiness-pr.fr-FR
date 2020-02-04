---
title: DNS Summary-SIP, Fédération de XMPP et messagerie instantanée publique
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c927836377a0c7c14054073a9cf17ce638662450
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="01f6d-102">Résumé DNS-SIP, Fédération de XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01f6d-103">_**Dernière modification de la rubrique :** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="01f6d-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="01f6d-104">Les enregistrements DNS (Domain Name System) requis pour la définition d’une Fédération auprès d’Office Communications Server ou de partenaires Lync Server sont déterminés par votre décision d’autoriser la découverte automatique de DNS de votre domaine par d’autres partenaires en perspective.</span><span class="sxs-lookup"><span data-stu-id="01f6d-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="01f6d-105">Si vous publiez \_le sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="01f6d-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="01f6d-106">\* \<Nom\> de domaine SIP\* Enregistrement SRV, tout autre domaine fédéré SIP peut « découvrir » votre Fédération.</span><span class="sxs-lookup"><span data-stu-id="01f6d-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="01f6d-107">Vous pouvez contrôler quels domaines fédérés peuvent communiquer avec vous à l’aide des paramètres des domaines et des domaines bloqués dans le panneau de configuration de Lync Server, ou en définissant la configuration des domaines autorisés ou bloqués à l’aide de Lync Server Management Shell et des applets de commande PowerShell **Get**, **Set**, **New**, **Remove-CsAllowedDomain** et **-CsBlockedDomain** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01f6d-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="01f6d-108">Pour plus d’informations sur la configuration de ces paramètres et l’utilisation des cmdlets PowerShell, voir les **Rubriques connexes** à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="01f6d-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="01f6d-109">La table de synthèse des enregistrements DNS représente les entrées nécessaires pour une Fédération ouverte ou détectable.</span><span class="sxs-lookup"><span data-stu-id="01f6d-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="01f6d-110">Si vous ne voulez pas implémenter la découverte de la Fédération, vous pouvez décider de \_ne pas configurer le sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="01f6d-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="01f6d-111">Enregistrement de *nom\> de domaine SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="01f6d-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="01f6d-112">Il existe des scénarios spécifiques dans lesquels vous devez disposer de l' _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="01f6d-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="01f6d-113"><EM> &lt;Nom&gt; de domaine SIP</EM> Enregistrement SRV, mais vous ne souhaitez pas disposer d’une Fédération détectable.</span><span class="sxs-lookup"><span data-stu-id="01f6d-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="01f6d-114">Par exemple, vous avez déployé une mobilité pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="01f6d-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="01f6d-115">Le système de notifications de transmission mobile Clearinghouse (PNCH) est un type spécial de Fédération qui est utilisé pour les clients mobiles Microsoft Lync sur Apple iPhone ou iPad utilisant le client mobile Lync 2010 ou Windows Phone à l’aide des clients mobiles Lync 2010 mobile ou Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="01f6d-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="01f6d-116">_Sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="01f6d-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="01f6d-117"><EM> &lt;Nom&gt; de domaine SIP</EM> L’enregistrement SRV est utilisé dans le cas d’une notification de mobilité et de transmission.</span><span class="sxs-lookup"><span data-stu-id="01f6d-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="01f6d-118">Pour limiter ce problème et contrôler votre détectabilité, décochez la case <STRONG>activer la découverte de domaines partenaires</STRONG> pour désactiver la découverte.</span><span class="sxs-lookup"><span data-stu-id="01f6d-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="01f6d-119">Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements au service Edge d’accès de votre serveur Edge ou de votre pool Edge.</span><span class="sxs-lookup"><span data-stu-id="01f6d-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="01f6d-120">Lorsque vous configurez DNS (Domain Name System) pour la connectivité de messagerie instantanée publique, vous constaterez que la configuration qui prend en charge les utilisateurs externes prend en charge la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="01f6d-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="01f6d-121">Si vous avez déjà configuré votre serveur Edge ou votre pool Edge, vous devez disposer des enregistrements DNS nécessaires à la prise en charge de la connectivité de messagerie instantanée publique.</span><span class="sxs-lookup"><span data-stu-id="01f6d-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="01f6d-122">Résumé DNS-Fédération SIP incluant la connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="01f6d-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f6d-123">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="01f6d-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01f6d-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="01f6d-124">FQDN</span></span></th>
<th><span data-ttu-id="01f6d-125">Enregistrement d’adresse IP/nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="01f6d-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01f6d-126">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="01f6d-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f6d-127">DNS/SRV/5061 externes</span><span class="sxs-lookup"><span data-stu-id="01f6d-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="01f6d-128">_sipfederationtls._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f6d-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f6d-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f6d-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f6d-130">L’interface externe du service Edge d’accès est requise pour une découverte automatique de votre Fédération auprès d’autres partenaires de Fédération potentiels, et est désignée sous le nom de « domaines SIP autorisés » (appelé Fédération avancée dans les versions antérieures). Répétez cette opération pour tous les domaines SIP pour lesquels Lync est compatible avec les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="01f6d-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="01f6d-131">Cet enregistrement SRV est requis pour la mobilité et l’hébergement d’échanges de notifications de transmission.</span><span class="sxs-lookup"><span data-stu-id="01f6d-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="01f6d-132">Dans les cas où il existe plusieurs domaines SIP, vous pouvez créer et publier un enregistrement SRV pour chaque domaine qui disposera de clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="01f6d-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="01f6d-133">Le service de notifications de transmission et le service de notifications de type Apple peut ne pas fonctionner comme prévu s’il n’y a pas d’enregistrement SRV explicite pour chaque domaine SIP pris en charge par le déploiement.</span><span class="sxs-lookup"><span data-stu-id="01f6d-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="01f6d-134">DNS Summary-extensible Messaging and Presence Protocol (XMPP)</span><span class="sxs-lookup"><span data-stu-id="01f6d-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01f6d-135">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="01f6d-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="01f6d-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="01f6d-136">FQDN</span></span></th>
<th><span data-ttu-id="01f6d-137">Enregistrement d’adresse IP/nom de domaine complet</span><span class="sxs-lookup"><span data-stu-id="01f6d-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="01f6d-138">Cartes sur/Commentaires</span><span class="sxs-lookup"><span data-stu-id="01f6d-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01f6d-139">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="01f6d-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="01f6d-140">_xmpp-server._tcp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f6d-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f6d-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="01f6d-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="01f6d-142">Interface externe du proxy XMPP du service Edge d’accès ou du pool Edge. Répétez cette opération pour tous les domaines SIP internes avec Lync pour les utilisateurs pour lesquels le contact avec les contacts XMPP est autorisé via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, d’une stratégie de site à l’emplacement de l’utilisateur ou d’une stratégie utilisateur appliquée au Utilisateur compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="01f6d-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="01f6d-143">Un domaine XMPP autorisé doit également être configuré dans la stratégie partenaires fédérés de XMPP.</span><span class="sxs-lookup"><span data-stu-id="01f6d-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="01f6d-144">Pour plus d’informations, voir rubriques supplémentaires dans la <strong>section Voir aussi</strong> .</span><span class="sxs-lookup"><span data-stu-id="01f6d-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01f6d-145">DNS/A externe</span><span class="sxs-lookup"><span data-stu-id="01f6d-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="01f6d-146">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="01f6d-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="01f6d-147">Adresse IP du service Edge d’accès sur votre serveur Edge ou pool d’hébergement de proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="01f6d-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="01f6d-148">Pointe vers le service Edge d’accès ou le pool Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="01f6d-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="01f6d-149">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement hôte (A ou AAAA).</span><span class="sxs-lookup"><span data-stu-id="01f6d-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01f6d-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="01f6d-150">See Also</span></span>


[<span data-ttu-id="01f6d-151">Configuration de la fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="01f6d-152">Configuration des notifications push dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="01f6d-153">Activation ou désactivation de la découverte de partenaires de fédération dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="01f6d-154">Scénarios d’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="01f6d-155">Détermination de la configuration requise pour DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="01f6d-156">Gestion des domaines fédérés SIP pour l’organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01f6d-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

