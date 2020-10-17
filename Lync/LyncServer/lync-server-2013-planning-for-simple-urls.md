---
title: 'Lync Server 2013 : planification des URL simples'
description: 'Lync Server 2013 : planification des URL simples.'
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
ms.openlocfilehash: 10a7f2aaf85dafe5facba7cfd2509cfcc8812d67
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558400"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="92a1f-103">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92a1f-103">Planning for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92a1f-104">_**Dernière modification de la rubrique :** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="92a1f-104">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="92a1f-105">Les URL simples facilitent la participation aux réunions pour vos utilisateurs et facilitent l’accès aux outils d’administration de Lync Server pour vos administrateurs.</span><span class="sxs-lookup"><span data-stu-id="92a1f-105">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="92a1f-106">Lync Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="92a1f-106">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="92a1f-107">**Meet** qui est l’URL de réunion de base pour toutes les conférences dans le site ou l’organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-107">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="92a1f-108">Un exemple d’URL simple de réunion est https://meet.contoso.com .</span><span class="sxs-lookup"><span data-stu-id="92a1f-108">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="92a1f-109">Une URL pour une réunion particulière peut être https://meet.contoso.com/ *username*/7322994.</span><span class="sxs-lookup"><span data-stu-id="92a1f-109">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="92a1f-110">Avec l’URL simple de réunion, les liens pour joindre des réunions sont faciles à comprendre, à communiquer et à distribuer.</span><span class="sxs-lookup"><span data-stu-id="92a1f-110">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="92a1f-111">**Dial-in** qui permet d’accéder à la page web Paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="92a1f-111">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="92a1f-112">Cette page affiche les numéros d’accès aux conférences, les langues disponibles, les informations de conférence affectées (c’est-à-dire, les réunions qui n’ont pas besoin d’être planifiées) et les contrôles DTMF de conférence, et prend en charge la gestion des informations de conférence.</span><span class="sxs-lookup"><span data-stu-id="92a1f-112">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="92a1f-113">L’URL simple Dial-in est incluse dans toutes les invitations aux réunions pour que les utilisateurs qui souhaitent se connecter à une réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="92a1f-113">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="92a1f-114">Voici un exemple de l’URL simple Dial-in https://dialin.contoso.com .</span><span class="sxs-lookup"><span data-stu-id="92a1f-114">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="92a1f-115">L' **administrateur** permet un accès rapide au panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92a1f-115">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="92a1f-116">À partir de n’importe quel ordinateur dans les pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration Lync Server en tapant l’URL simple d’administration dans un navigateur.</span><span class="sxs-lookup"><span data-stu-id="92a1f-116">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="92a1f-117">L’URL simple d’administration est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-117">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="92a1f-118">Un exemple d’URL simple admin est https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92a1f-118">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="92a1f-119">Étendue des URL simples</span><span class="sxs-lookup"><span data-stu-id="92a1f-119">Simple URL Scope</span></span>

<span data-ttu-id="92a1f-120">Vous pouvez configurer les URL simples de sorte que leur étendue soit globale mais vous pouvez également spécifier des URL simples différentes pour chaque site central dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-120">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="92a1f-121">Si une URL simple d’étendue globale et une URL simple d’étendue de site sont spécifiées, l’URL simple de l’étendue du site a la priorité.</span><span class="sxs-lookup"><span data-stu-id="92a1f-121">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="92a1f-p105">Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, pour que l’URL simple de réunion d’un utilisateur ne change pas si celui-ci passe d’un site à un autre ; en revanche ne définissez pas d’URL globales pour les organisations qui doivent utiliser des numéros de téléphone différents pour les utilisateurs se trouvant dans différents sites. Notez que si vous définissez une URL simple (par exemple une URL simple d’accès) en tant qu’URL simple de site pour un site, vous devez également définir les autres URL simples pour ce site en tant qu’URL simples de site.</span><span class="sxs-lookup"><span data-stu-id="92a1f-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="92a1f-125">Si vous choisissez d’utiliser des URL simples d’étendue site, vos utilisateurs ne pourront pas se déplacer entre les pools de Front-End dans des sites différents sans que ces utilisateurs replanifient toutes leurs réunions planifiées, car les URL simples de réunion sont différentes entre les sites.</span><span class="sxs-lookup"><span data-stu-id="92a1f-125">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="92a1f-126">Cela inclut les scénarios de basculement lorsque les pools dans les relations de sauvegarde se trouvent dans des sites distincts.</span><span class="sxs-lookup"><span data-stu-id="92a1f-126">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="92a1f-127">Lorsque vous devez basculer entre les sites où les URL simples d’étendue de site sont déployées, les utilisateurs ne peuvent pas participer à leurs réunions en raison de l’étendue de l’URL.</span><span class="sxs-lookup"><span data-stu-id="92a1f-127">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="92a1f-128">Pour plus d’informations, consultez <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="92a1f-128">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="92a1f-129">Vous pouvez définir des URL simples globales dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="92a1f-129">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="92a1f-130">En revanche, pour définir une URL simple de site, vous devez utiliser l’applet de commande Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="92a1f-130">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="92a1f-131">Dénomination des URL simples</span><span class="sxs-lookup"><span data-stu-id="92a1f-131">Naming Your Simple URLs</span></span>

<span data-ttu-id="92a1f-p108">Il existe trois options recommandées pour nommer les URL simples. L’option que vous choisissez influe sur la configuration des enregistrements et des certificats DNS A qui prennent en charge les URL simples. Dans chaque option, vous devez configurer une URL simple de réunion pour chaque domaine SIP dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="92a1f-135">Dans votre organisation, une seule URL simple est nécessaire pour l’accès et une seule pour l’administration, quel que soit le nombre de domaines dont vous disposez.</span><span class="sxs-lookup"><span data-stu-id="92a1f-135">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="92a1f-136">Pour plus d’informations sur les enregistrements et les certificats DNS A nécessaires, consultez la rubrique [DNS Requirements for simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et [Certificate Requirements for Internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="92a1f-136">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="92a1f-137">Dans l’option 1, vous devez créer un nom de domaine SIP pour chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="92a1f-137">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="92a1f-138">Si vous utilisez cette option, vous devez prévoir un enregistrement DNS A distinct pour chaque URL simple et chaque URL simple de réunion doit être nommée dans les certificats.</span><span class="sxs-lookup"><span data-stu-id="92a1f-138">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="92a1f-139">Option 1 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="92a1f-139">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-140"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-140"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92a1f-141"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-141"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-142">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="92a1f-142">Meet</span></span></p></td>
<td><p><span data-ttu-id="92a1f-143">https://meet.contoso.com, https://meet.fabrikam.com , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="92a1f-143">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-144">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="92a1f-144">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-145">Administrateur</span><span class="sxs-lookup"><span data-stu-id="92a1f-145">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92a1f-p109">Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com. Par conséquent, vous n’avez besoin que d’un seul enregistrement DNS A pour les trois types d’URL simple. Cet enregistrement DNS A référence lync.contoso.com. Mais vous avez quand même besoin d’enregistrements DNS A distincts pour les autres domaines SIP dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="92a1f-150">Option 2 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="92a1f-150">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-151"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-151"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92a1f-152"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-152"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-153">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="92a1f-153">Meet</span></span></p></td>
<td><p><span data-ttu-id="92a1f-154">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet , et ainsi de suite (une pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="92a1f-154">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-155">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="92a1f-155">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-156">Administrateur</span><span class="sxs-lookup"><span data-stu-id="92a1f-156">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="92a1f-157">L’option 3 est particulièrement utile si vous disposez de plusieurs domaines SIP et si vous souhaitez qu’ils aient des URL simples de réunion distinctes mais souhaitez minimiser les enregistrements et les certificats DNS requis pour ces URL simples.</span><span class="sxs-lookup"><span data-stu-id="92a1f-157">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="92a1f-158">Option 3 de dénomination d’URL simple</span><span class="sxs-lookup"><span data-stu-id="92a1f-158">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-159"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-159"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="92a1f-160"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="92a1f-160"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-161">Satisfaction</span><span class="sxs-lookup"><span data-stu-id="92a1f-161">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a1f-162">Appels entrants</span><span class="sxs-lookup"><span data-stu-id="92a1f-162">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a1f-163">Administrateur</span><span class="sxs-lookup"><span data-stu-id="92a1f-163">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="92a1f-164">Dénomination d’URL simple et règles de validation</span><span class="sxs-lookup"><span data-stu-id="92a1f-164">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="92a1f-165">Le générateur de topologies et les applets de commande Lync Server Management Shell appliquent plusieurs règles de validation pour vos URL simples.</span><span class="sxs-lookup"><span data-stu-id="92a1f-165">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="92a1f-166">Vous devez définir des URL simples pour les réunions et l’accès, et éventuellement une URL pour l’administration.</span><span class="sxs-lookup"><span data-stu-id="92a1f-166">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="92a1f-167">Chaque domaine SIP doit avoir une URL simple de réunion mais une seule URL simple est nécessaire pour l’accès et une seule pour l’administration dans toute l’organisation.</span><span class="sxs-lookup"><span data-stu-id="92a1f-167">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="92a1f-168">Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous ne pouvez pas définir lync.contoso.com/Meet comme votre URL simple de réunion et lync.contoso.com/Meet/Dialin comme votre URL simple de numérotation).</span><span class="sxs-lookup"><span data-stu-id="92a1f-168">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="92a1f-169">Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos pools, ni aucune information de port (par exemple, n' https://FQDN:88/meet est pas autorisé).</span><span class="sxs-lookup"><span data-stu-id="92a1f-169">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="92a1f-170">Toutes les URL simples doivent commencer par le préfixe https://.</span><span class="sxs-lookup"><span data-stu-id="92a1f-170">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="92a1f-p112">Les URL simples peuvent uniquement contenir des caractères alphanumériques, c’est-à-dire a-z, A-Z, 0-9 et le point (.). Si vous utilisez d’autres caractères, les URL simples peuvent ne pas fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="92a1f-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="92a1f-173">Modifications des URL simples après leur déploiement</span><span class="sxs-lookup"><span data-stu-id="92a1f-173">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="92a1f-174">Si vous modifiez une URL simple après le déploiement initial, vous devez savoir comment la modification influe sur vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="92a1f-174">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="92a1f-175">Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats.</span><span class="sxs-lookup"><span data-stu-id="92a1f-175">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="92a1f-176">Par exemple, https://lync.contoso.com/Meet https://meet.contoso.com si vous modifiez l’URL de base de lync.contoso.com en Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="92a1f-176">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="92a1f-177">Si vous avez modifié l’URL simple https://lync.contoso.com/Meet vers https://lync.contoso.com/Meetings , l’URL de base de Lync.contoso.com reste la même, de sorte qu’aucune modification de certificat ou de DNS n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="92a1f-177">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="92a1f-178">Chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque directeur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="92a1f-178">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92a1f-179">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92a1f-179">See Also</span></span>


[<span data-ttu-id="92a1f-180">Configuration DNS requise pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92a1f-180">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

