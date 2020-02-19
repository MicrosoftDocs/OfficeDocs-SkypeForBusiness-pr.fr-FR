---
title: Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique
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
ms.openlocfilehash: 253a00a07d1d76e77c9a753f6442151beda7c801
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="12f71-102">Résumé des enregistrements DNS-SIP, Fédération XMPP et messagerie instantanée publique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f71-103">_**Dernière modification de la rubrique :** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="12f71-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="12f71-104">Les enregistrements DNS (Domain Name System) requis pour la définition d’une Fédération avec Office Communications Server ou les partenaires Lync Server sont déterminés par votre décision d’autoriser la découverte automatique de DNS de votre domaine par d’autres partenaires en perspective.</span><span class="sxs-lookup"><span data-stu-id="12f71-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="12f71-105">Si vous publiez \_le sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="12f71-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="12f71-106">\* \<Nom\> de domaine SIP\* Enregistrement SRV, tout autre domaine fédéré SIP pourra « détecter » votre Fédération.</span><span class="sxs-lookup"><span data-stu-id="12f71-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="12f71-107">Vous pouvez contrôler les domaines fédérés pouvant communiquer avec vous en utilisant les paramètres domaines et domaines bloqués dans le panneau de configuration Lync Server, ou en définissant la configuration des domaines autorisés ou bloqués à l’aide de Lync Server Management Shell et des applets de commande PowerShell **Get**, **Set**, **New**, **Remove-CsAllowedDomain** et **-applet csblockeddomain** .</span><span class="sxs-lookup"><span data-stu-id="12f71-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="12f71-108">Pour plus d’informations sur la configuration de ces paramètres et l’utilisation des applets de commande PowerShell, consultez les **Rubriques connexes** à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="12f71-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="12f71-109">Le tableau récapitulatif des enregistrements DNS décrit les entrées requises pour une fédération ouverte (détectable).</span><span class="sxs-lookup"><span data-stu-id="12f71-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="12f71-110">Si vous ne souhaitez pas implémenter la découverte de Fédération, vous pouvez décider de ne \_pas configurer le sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="12f71-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="12f71-111">Enregistrement de *nom\> de domaine SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="12f71-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="12f71-112">Il existe des scénarios spécifiques dans lesquels vous devez disposer de l' _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="12f71-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="12f71-113"><EM> &lt;Nom&gt; de domaine SIP</EM> Enregistrement SRV, mais vous ne souhaitez pas avoir une Fédération découvrable.</span><span class="sxs-lookup"><span data-stu-id="12f71-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="12f71-114">Une telle instance est l’endroit où vous avez déployé la mobilité pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="12f71-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="12f71-115">Le centre de notifications mobiles Mobility (échanges) est un type spécial de Fédération utilisé pour les clients mobiles Microsoft Lync sur un iPhone ou un iPad Apple à l’aide du client mobile Lync 2010 ou de Windows Phone à l’aide des clients mobiles Lync 2010 mobile ou Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="12f71-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="12f71-116">Le _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="12f71-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="12f71-117"><EM> &lt;Nom&gt; de domaine SIP</EM> L’enregistrement SRV est utilisé en cas de mobilité et de notification de transmission.</span><span class="sxs-lookup"><span data-stu-id="12f71-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="12f71-118">Pour atténuer ce problème et contrôler votre détectabilité, désactivez la case à <STRONG>coactivation activer la découverte du domaine partenaire</STRONG> pour désactiver la découverte.</span><span class="sxs-lookup"><span data-stu-id="12f71-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="12f71-119">Pour configurer le protocole XMPP (extensible Messaging and Presence Protocol) pour votre déploiement, vous devez créer deux enregistrements DNS (Domain Name System) dans un serveur DNS externe qui résoudra les enregistrements vers le service Edge d’accès de votre serveur Edge ou pool de serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="12f71-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="12f71-120">Lorsque vous configurez DNS (Domain Name System) pour la connectivité de messagerie instantanée publique, vous constaterez que la configuration qui prend en charge les utilisateurs externes prend en charge la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="12f71-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="12f71-121">Si vous avez déjà configuré votre serveur Edge ou votre pool de serveurs Edge, vous devez disposer des enregistrements DNS nécessaires à la prise en charge de la connectivité PIC.</span><span class="sxs-lookup"><span data-stu-id="12f71-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="12f71-122">Résumé des enregistrements DNS-Fédération SIP, y compris la connectivité de messagerie instantanée publique</span><span class="sxs-lookup"><span data-stu-id="12f71-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12f71-123">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="12f71-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="12f71-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="12f71-124">FQDN</span></span></th>
<th><span data-ttu-id="12f71-125">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="12f71-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="12f71-126">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="12f71-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12f71-127">DNS externe/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="12f71-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="12f71-128">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="12f71-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12f71-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12f71-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12f71-130">Interface externe du service Edge d’accès requise pour la découverte automatique de DNS de votre Fédération auprès des autres partenaires de Fédération potentiels, et appelée « domaines SIP autorisés » (appelée fédération étendue dans les versions précédentes). Répétez cette opération autant que nécessaire pour tous les domaines SIP avec des utilisateurs activés pour Lync.</span><span class="sxs-lookup"><span data-stu-id="12f71-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="12f71-131">Cet enregistrement SRV est requis pour la mobilité et le centre d’échanges de notifications push.</span><span class="sxs-lookup"><span data-stu-id="12f71-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="12f71-132">Dans les cas où il existe plusieurs domaines SIP, créez et publiez un enregistrement SRV pour chaque domaine qui aura des clients mobiles Lync.</span><span class="sxs-lookup"><span data-stu-id="12f71-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="12f71-133">Le service de notifications et les services de notifications d’Apple ne fonctionnent pas comme prévu s’il n’existe pas d’enregistrement SRV explicite pour chaque domaine SIP pris en charge par le déploiement.</span><span class="sxs-lookup"><span data-stu-id="12f71-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="12f71-134">Résumé des enregistrements DNS-protocole XMPP (extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="12f71-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="12f71-135">Emplacement/TYPE/port</span><span class="sxs-lookup"><span data-stu-id="12f71-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="12f71-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="12f71-136">FQDN</span></span></th>
<th><span data-ttu-id="12f71-137">Adresse IP/Enregistrement d’hôte FQDN</span><span class="sxs-lookup"><span data-stu-id="12f71-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="12f71-138">Mappage à/Commentaires</span><span class="sxs-lookup"><span data-stu-id="12f71-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12f71-139">DNS externe/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="12f71-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="12f71-140">_xmpp-Server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="12f71-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12f71-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="12f71-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="12f71-142">Interface externe du proxy XMPP sur le service Edge d’accès ou le pool de serveurs Edge. Répétez cette opération si nécessaire pour tous les domaines SIP internes avec des utilisateurs activés de Lync où les contacts XMPP sont autorisés via la configuration de la stratégie d’accès externe par le biais d’une stratégie globale, de la stratégie de site où se trouve l’utilisateur ou de la stratégie de l’utilisateur appliquée au Utilisateur à extension Lync.</span><span class="sxs-lookup"><span data-stu-id="12f71-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="12f71-143">Un domaine XMPP autorisé doit également être configuré dans la stratégie des partenaires fédérés XMPP.</span><span class="sxs-lookup"><span data-stu-id="12f71-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="12f71-144">Voir les rubriques de la <strong>section Voir aussi</strong> pour plus de détails</span><span class="sxs-lookup"><span data-stu-id="12f71-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12f71-145">DNS externe/A</span><span class="sxs-lookup"><span data-stu-id="12f71-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="12f71-146">xmpp.contoso.com (par exemple)</span><span class="sxs-lookup"><span data-stu-id="12f71-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="12f71-147">Adresse IP du service Edge d’accès sur votre serveur Edge ou le pool de serveurs Edge qui héberge le proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="12f71-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="12f71-148">Pointe vers le service Edge d’accès ou le pool de serveurs Edge qui héberge le service proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="12f71-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="12f71-149">En général, l’enregistrement SRV que vous créez pointe vers cet enregistrement (A ou AAAA) d’hôte.</span><span class="sxs-lookup"><span data-stu-id="12f71-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="12f71-150">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="12f71-150">See Also</span></span>


[<span data-ttu-id="12f71-151">Configuration de la Fédération XMPP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="12f71-152">Configuration des notifications de type transmission dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="12f71-153">Activer ou désactiver la découverte des partenaires de Fédération dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="12f71-154">Scénarios pour l’accès des utilisateurs externes dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="12f71-155">Déterminer les exigences DNS pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="12f71-156">Gérer les domaines fédérés SIP pour votre organisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12f71-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

