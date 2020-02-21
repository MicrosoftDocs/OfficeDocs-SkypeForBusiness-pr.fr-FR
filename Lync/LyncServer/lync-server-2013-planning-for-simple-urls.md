---
title: 'Lync Server 2013 : planification des URL simples'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6bbbe8650ae1d7746c9b87ecf4518236f8b1575
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="b7acd-102">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7acd-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7acd-103">_**Dernière modification de la rubrique :** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="b7acd-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="b7acd-104">Les URL simples facilitent la participation aux réunions pour vos utilisateurs et facilitent l’accès aux outils d’administration de Lync Server pour vos administrateurs.</span><span class="sxs-lookup"><span data-stu-id="b7acd-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="b7acd-105">Lync Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="b7acd-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="b7acd-106">**Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="b7acd-107">Un exemple d’URL simple de réunion est https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b7acd-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="b7acd-108">Une URL pour une réunion particulière peut être https://meet.contoso.com/ *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="b7acd-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="b7acd-109">Avec l’URL simple de réunion, les liens pour joindre des réunions sont faciles à comprendre, à communiquer et à distribuer.</span><span class="sxs-lookup"><span data-stu-id="b7acd-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="b7acd-110">**Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b7acd-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="b7acd-111">Cette page affiche les numéros d’accès de conférence avec leurs langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion du numéro d’identification personnel ( PIN) et les informations de conférence affectées.</span><span class="sxs-lookup"><span data-stu-id="b7acd-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="b7acd-112">L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="b7acd-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="b7acd-113">Voici https://dialin.contoso.comun exemple de l’URL simple Dial-in.</span><span class="sxs-lookup"><span data-stu-id="b7acd-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="b7acd-114">L' **administrateur** permet un accès rapide au panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7acd-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="b7acd-115">À partir de n’importe quel ordinateur dans les pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration Lync Server en tapant l’URL simple d’administration dans un navigateur.</span><span class="sxs-lookup"><span data-stu-id="b7acd-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="b7acd-116">L’URL simple d’administration est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="b7acd-117">Un exemple d’URL simple admin esthttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="b7acd-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="b7acd-118">Étendue des URL simples</span><span class="sxs-lookup"><span data-stu-id="b7acd-118">Simple URL Scope</span></span>

<span data-ttu-id="b7acd-119">Vous pouvez configurer les URL simples de sorte que leur étendue soit globale mais vous pouvez également spécifier des URL simples différentes pour chaque site central dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="b7acd-120">Si une URL simple d’étendue globale et une URL simple d’étendue de site sont spécifiées, l’URL simple de l’étendue du site a la priorité.</span><span class="sxs-lookup"><span data-stu-id="b7acd-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="b7acd-p105">Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, pour que l’URL simple de réunion d’un utilisateur ne change pas si celui-ci passe d’un site à un autre ; en revanche ne définissez pas d’URL globales pour les organisations qui doivent utiliser des numéros de téléphone différents pour les utilisateurs se trouvant dans différents sites. Notez que si vous définissez une URL simple (par exemple une URL simple d’accès) en tant qu’URL simple de site pour un site, vous devez également définir les autres URL simples pour ce site en tant qu’URL simples de site.</span><span class="sxs-lookup"><span data-stu-id="b7acd-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7acd-124">Si vous choisissez d’utiliser des URL simples d’étendue site, vos utilisateurs ne peuvent pas passer d’un pool frontal à un autre dans différents sites sans que ces utilisateurs replanifient toutes leurs réunions planifiées, car les URL simples de la réunion sont différentes d’un site à un autre.</span><span class="sxs-lookup"><span data-stu-id="b7acd-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="b7acd-125">Cela inclut les scénarios de basculement lorsque les pools dans les relations de sauvegarde se trouvent dans des sites distincts.</span><span class="sxs-lookup"><span data-stu-id="b7acd-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="b7acd-126">Lorsque vous devez basculer entre les sites où les URL simples d’étendue de site sont déployées, les utilisateurs ne peuvent pas participer à leurs réunions en raison de l’étendue de l’URL.</span><span class="sxs-lookup"><span data-stu-id="b7acd-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="b7acd-127">Pour plus d’informations, consultez <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="b7acd-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="b7acd-128">Vous pouvez définir des URL simples globales dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="b7acd-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="b7acd-129">En revanche, pour définir une URL simple de site, vous devez utiliser l’applet de commande Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b7acd-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="b7acd-130">Dénomination des URL simples</span><span class="sxs-lookup"><span data-stu-id="b7acd-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="b7acd-p108">Il existe trois options recommandées pour nommer les URL simples. L’option que vous choisissez influe sur la configuration des enregistrements et des certificats DNS A qui prennent en charge les URL simples. Dans chaque option, vous devez configurer une URL simple de réunion pour chaque domaine SIP dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="b7acd-134">Dans votre organisation, une seule URL simple est nécessaire pour l’accès et une seule pour l’administration, quel que soit le nombre de domaines dont vous disposez.</span><span class="sxs-lookup"><span data-stu-id="b7acd-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="b7acd-135">Pour plus d’informations sur les enregistrements et les certificats DNS A nécessaires, consultez la rubrique [DNS Requirements for simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="b7acd-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="b7acd-136">Dans l’option 1, vous devez créer un nom de domaine SIP pour chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="b7acd-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="b7acd-137">Si vous utilisez cette option, vous devez prévoir un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doit être nommée dans les certificats.</span><span class="sxs-lookup"><span data-stu-id="b7acd-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="b7acd-138">Option 1 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="b7acd-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-139"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b7acd-140"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-141">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="b7acd-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="b7acd-142">https://meet.contoso.com, https://meet.fabrikam.com, et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="b7acd-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-143">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="b7acd-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-144">Administrateur</span><span class="sxs-lookup"><span data-stu-id="b7acd-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b7acd-p109">Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS A pour les trois types d’URL simple. Cet enregistrement DNS A référence lync.contoso.com. Mais vous avez quand même besoin d’enregistrements DNS A distincts pour les autres domaines SIP dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="b7acd-149">Option 2 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="b7acd-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-150"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b7acd-151"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-152">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="b7acd-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="b7acd-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="b7acd-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-154">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="b7acd-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-155">Administrateur</span><span class="sxs-lookup"><span data-stu-id="b7acd-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b7acd-156">L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples de réunion distinctes mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples.</span><span class="sxs-lookup"><span data-stu-id="b7acd-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="b7acd-157">Option 3 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="b7acd-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-158"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="b7acd-159"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="b7acd-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-160">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="b7acd-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7acd-161">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="b7acd-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7acd-162">Administrateur</span><span class="sxs-lookup"><span data-stu-id="b7acd-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="b7acd-163">Dénomination d’URL simple et règles de validation</span><span class="sxs-lookup"><span data-stu-id="b7acd-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="b7acd-164">Le générateur de topologies et les applets de commande Lync Server Management Shell appliquent plusieurs règles de validation pour vos URL simples.</span><span class="sxs-lookup"><span data-stu-id="b7acd-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="b7acd-165">Vous devez définir des URL simples pour les réunions et l’accès, et éventuellement une URL pour l’administration.</span><span class="sxs-lookup"><span data-stu-id="b7acd-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="b7acd-166">Chaque domaine SIP doit avoir une URL simple de réunion mais une seule URL simple est nécessaire pour l’accès et une seule pour l’administration dans toute l’organisation.</span><span class="sxs-lookup"><span data-stu-id="b7acd-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="b7acd-167">Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous ne pouvez pas définir lync.contoso.com/Meet comme votre URL simple de réunion et lync.contoso.com/Meet/Dialin comme votre URL simple de numérotation).</span><span class="sxs-lookup"><span data-stu-id="b7acd-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="b7acd-168">Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos pools https://FQDN:88/meet , ni aucune information de port (par exemple, n’est pas autorisé).</span><span class="sxs-lookup"><span data-stu-id="b7acd-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="b7acd-169">Toutes les URL simples doivent commencer par le préfixe https://.</span><span class="sxs-lookup"><span data-stu-id="b7acd-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="b7acd-p112">Les URL simples peuvent uniquement contenir des caractères alphanumériques, c’est-à-dire a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples peuvent ne pas fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="b7acd-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="b7acd-172">Modifications des URL simples après leur déploiement</span><span class="sxs-lookup"><span data-stu-id="b7acd-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="b7acd-173">Si vous modifiez une URL simple après le déploiement initial, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="b7acd-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="b7acd-174">Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats.</span><span class="sxs-lookup"><span data-stu-id="b7acd-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="b7acd-175">Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com en Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b7acd-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="b7acd-176">Si vous avez modifié l’URL simple https://lync.contoso.com/Meet vers https://lync.contoso.com/Meetings, l’url de base de Lync.contoso.com reste la même, de sorte qu’aucune modification de certificat ou de DNS n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="b7acd-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="b7acd-177">Chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="b7acd-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7acd-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7acd-178">See Also</span></span>


[<span data-ttu-id="b7acd-179">Configuration DNS requise pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7acd-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

