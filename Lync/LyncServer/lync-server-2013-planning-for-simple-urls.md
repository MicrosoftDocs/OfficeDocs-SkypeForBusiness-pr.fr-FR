---
title: 'Lync Server 2013 : Planification des URL simples'
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
ms.openlocfilehash: 224ca0315aff2618500182398cfe792c9626b883
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="4b77e-102">Planification des URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b77e-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b77e-103">_**Dernière modification de la rubrique :** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="4b77e-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="4b77e-104">Les URL simples permettent de participer plus facilement à des réunions pour vos utilisateurs et permettent d’accéder plus facilement aux outils d’administration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b77e-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="4b77e-105">Lync Server prend en charge trois URL simples :</span><span class="sxs-lookup"><span data-stu-id="4b77e-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="4b77e-106">La **fonction réunion** est utilisée comme URL de base pour toutes les conférences du site ou de l’organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="4b77e-107">Par exemple, une URL de réunion simple https://meet.contoso.comest.</span><span class="sxs-lookup"><span data-stu-id="4b77e-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="4b77e-108">Une URL pour une réunion particulière peut être https://meet.contoso.com/ *nom d’utilisateur*/7322994.</span><span class="sxs-lookup"><span data-stu-id="4b77e-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="4b77e-109">Avec l’URL de la réunion, vous pouvez facilement comprendre les liens permettant de participer à des réunions, et facilement communiquer et diffuser.</span><span class="sxs-lookup"><span data-stu-id="4b77e-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="4b77e-110">Le rendez **-** vous permet d’accéder à la page Web des paramètres de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="4b77e-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="4b77e-111">Cette page présente les numéros de conférence rendez-vous avec les langues disponibles, les informations de conférence affectées (c’est-à-dire pour les réunions qui n’ont pas besoin d’être planifiées), les commandes DTMF en conférence et prend en charge la gestion du numéro d’identification personnel ( Code confidentiel) et informations de conférence affectées.</span><span class="sxs-lookup"><span data-stu-id="4b77e-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="4b77e-112">L’URL d’accès à un rendez-vous est incluse dans toutes les invitations à une réunion de sorte que les utilisateurs qui souhaitent se connecter à la réunion puissent accéder au numéro de téléphone et aux informations de code confidentiel nécessaires.</span><span class="sxs-lookup"><span data-stu-id="4b77e-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="4b77e-113">Par exemple, l’URL de connexion simple est https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4b77e-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="4b77e-114">L' **administrateur** vous permet d’accéder rapidement au panneau de configuration de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b77e-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="4b77e-115">À partir de n’importe quel ordinateur au sein des pare-feu de votre organisation, un administrateur peut ouvrir le panneau de configuration de Lync Server en entrant l’URL simple d’administration dans un navigateur.</span><span class="sxs-lookup"><span data-stu-id="4b77e-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="4b77e-116">L’URL simple Admin est interne à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="4b77e-117">Par exemple, l’URL d’administration simple esthttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b77e-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="4b77e-118">Étendue d’URL simple</span><span class="sxs-lookup"><span data-stu-id="4b77e-118">Simple URL Scope</span></span>

<span data-ttu-id="4b77e-119">Vous pouvez configurer vos URL simples pour qu’elles aient une étendue globale ou spécifier différentes URL simples pour chaque site central de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="4b77e-120">S’il s’agit d’une URL simple d’étendue globale et d’une URL simple d’étendue de site, l’URL d’étendue du site est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="4b77e-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="4b77e-121">Dans la plupart des cas, nous vous conseillons de définir des URL simples uniquement au niveau global, de telle sorte que l’URL de la réunion n’est pas la même que celle d’un site à l’autre.</span><span class="sxs-lookup"><span data-stu-id="4b77e-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="4b77e-122">Il peut s’agir d’organisations qui ont besoin d’utiliser différents numéros de téléphone pour les utilisateurs rendez-vous sur différents sites.</span><span class="sxs-lookup"><span data-stu-id="4b77e-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="4b77e-123">Notez que si vous définissez une URL simple (par exemple, l’URL d’accès à la Conférence rendez-vous) sur un site, vous devez également définir d’autres URL simples sur ce site comme niveau de site.</span><span class="sxs-lookup"><span data-stu-id="4b77e-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b77e-124">Si vous choisissez d’utiliser des URL simples à portée de site, vos utilisateurs ne seront pas en mesure de basculer entre les listes frontales sur les différents sites sans que les utilisateurs replanifient toutes leurs réunions planifiées, car les URL simples de la réunion sont différentes entre les sites.</span><span class="sxs-lookup"><span data-stu-id="4b77e-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="4b77e-125">Cela inclut les scénarios de basculement dans lesquels les relations de sauvegarde se trouvent dans des sites distincts.</span><span class="sxs-lookup"><span data-stu-id="4b77e-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="4b77e-126">Lorsque vous avez besoin de basculer entre les sites dans lesquels les URL simples de votre site sont déployées, les utilisateurs ne seront pas en mesure de rejoindre leurs réunions en raison de l’étendue de l’URL.</span><span class="sxs-lookup"><span data-stu-id="4b77e-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="4b77e-127">Pour plus d’informations, consultez <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="4b77e-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="4b77e-128">Vous pouvez définir des URL simples globales dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="4b77e-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="4b77e-129">Pour définir une URL simple au niveau du site, vous devez utiliser l’applet de cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="4b77e-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="4b77e-130">Attribution d’un nom à vos URL simples</span><span class="sxs-lookup"><span data-stu-id="4b77e-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="4b77e-131">Il existe trois options recommandées pour nommer vos URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="4b77e-132">L’option que vous choisissez a des implications sur la configuration de vos enregistrements DNS A et des certificats qui prennent en charge des URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="4b77e-133">Dans chaque option, vous devez configurer une seule URL de la réunion pour chaque domaine SIP de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="4b77e-134">Vous avez toujours besoin d’une seule URL dans l’ensemble de votre organisation pour le rendez-vous, et l’autre pour l’administrateur, quel que soit le nombre de domaines SIP.</span><span class="sxs-lookup"><span data-stu-id="4b77e-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="4b77e-135">Pour plus d’informations sur les enregistrements et les certificats DNS requis, voir [exigences DNS pour les URL simples dans Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) et les [certificats requis pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="4b77e-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="4b77e-136">Dans l’option 1, vous créez un nouveau nom de domaine SIP pour chaque URL simple.</span><span class="sxs-lookup"><span data-stu-id="4b77e-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="4b77e-137">Si vous utilisez cette option, vous avez besoin d’un enregistrement DNS A distinct pour chaque URL simple et chaque URL de la réunion doit être nommée dans vos certificats.</span><span class="sxs-lookup"><span data-stu-id="4b77e-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="4b77e-138">Option de nom d’URL simple 1</span><span class="sxs-lookup"><span data-stu-id="4b77e-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-139"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="4b77e-140"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-141">Correspondre</span><span class="sxs-lookup"><span data-stu-id="4b77e-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="4b77e-142">https://meet.contoso.com, https://meet.fabrikam.comet ainsi de suite (un pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="4b77e-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-143">Rendez-vous</span><span class="sxs-lookup"><span data-stu-id="4b77e-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-144">Administrateur</span><span class="sxs-lookup"><span data-stu-id="4b77e-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b77e-145">Avec l’option 2, les URL simples sont basées sur le nom de domaine lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4b77e-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="4b77e-146">Par conséquent, vous avez besoin d’un enregistrement DNS A qui active les trois types d’URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="4b77e-147">Cet enregistrement DNS A fait référence à lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4b77e-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="4b77e-148">Par ailleurs, vous avez encore besoin d’enregistrements DNS A séparés pour d’autres domaines SIP de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="4b77e-149">Option de nom d’URL simple 2</span><span class="sxs-lookup"><span data-stu-id="4b77e-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-150"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="4b77e-151"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-152">Correspondre</span><span class="sxs-lookup"><span data-stu-id="4b77e-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="4b77e-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meetet ainsi de suite (un pour chaque domaine SIP de votre organisation)</span><span class="sxs-lookup"><span data-stu-id="4b77e-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-154">Rendez-vous</span><span class="sxs-lookup"><span data-stu-id="4b77e-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-155">Administrateur</span><span class="sxs-lookup"><span data-stu-id="4b77e-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4b77e-156">L’option 3 est particulièrement utile si vous avez de nombreux domaines SIP et que vous souhaitez qu’ils soient séparés par des URL simples et qu’ils souhaitent limiter les exigences d’enregistrements DNS et de certificats pour ces URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="4b77e-157">Option de nom d’URL simple 3</span><span class="sxs-lookup"><span data-stu-id="4b77e-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-158"><strong>URL simple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="4b77e-159"><strong>Exemple</strong></span><span class="sxs-lookup"><span data-stu-id="4b77e-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-160">Correspondre</span><span class="sxs-lookup"><span data-stu-id="4b77e-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b77e-161">Rendez-vous</span><span class="sxs-lookup"><span data-stu-id="4b77e-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b77e-162">Administrateur</span><span class="sxs-lookup"><span data-stu-id="4b77e-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="4b77e-163">Règles de validation et d’attribution d’URL simples</span><span class="sxs-lookup"><span data-stu-id="4b77e-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="4b77e-164">Le générateur de topologie et les applets de contrôle Lync Server Management Shell appliquent plusieurs règles de validation pour vos URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="4b77e-165">Vous devez définir des URL simples pour la réunion et le numéro de téléphone, mais la définition d’une pour l’administrateur est facultative.</span><span class="sxs-lookup"><span data-stu-id="4b77e-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="4b77e-166">Chaque domaine SIP doit être doté d’une URL simple de connexion, mais vous n’avez besoin que d’une seule URL de composition unique et d’une URL simple d’administration pour l’ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="4b77e-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="4b77e-167">Chaque URL simple de votre organisation doit avoir un nom unique et ne peut pas être un préfixe d’une autre URL simple (par exemple, vous n’avez pas pu définir lync.contoso.com/Meet comme URL simple de la Conférence).</span><span class="sxs-lookup"><span data-stu-id="4b77e-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="4b77e-168">Les noms d’URL simples ne peuvent pas contenir le nom de domaine complet de l’un de vos groupes, https://FQDN:88/meet ni aucune information de port (par exemple, n’est pas autorisée).</span><span class="sxs-lookup"><span data-stu-id="4b77e-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="4b77e-169">Toutes les URL simples doivent commencer par le préfixe https://.</span><span class="sxs-lookup"><span data-stu-id="4b77e-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="4b77e-170">Les URL simples peuvent contenir des caractères alphanumériques (c’est-à-dire, a-z, A-Z, 0-9 et le point (.).</span><span class="sxs-lookup"><span data-stu-id="4b77e-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="4b77e-171">Si vous utilisez d’autres caractères, les URL simples risquent de ne pas fonctionner comme prévu.</span><span class="sxs-lookup"><span data-stu-id="4b77e-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="4b77e-172">Modification d’URL simples après le déploiement</span><span class="sxs-lookup"><span data-stu-id="4b77e-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="4b77e-173">Si vous modifiez une URL simple après le déploiement initial, vous devez tenir compte de la façon dont le changement a un impact sur vos enregistrements DNS et les certificats pour les URL simples.</span><span class="sxs-lookup"><span data-stu-id="4b77e-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="4b77e-174">Si la base d’une URL simple change, vous devez également modifier les enregistrements DNS et les certificats.</span><span class="sxs-lookup"><span data-stu-id="4b77e-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="4b77e-175">Par exemple, si vous https://lync.contoso.com/Meet modifiez https://meet.contoso.com l’URL de base de Lync.contoso.com à Meet.contoso.com, vous devez modifier les enregistrements DNS et les certificats pour faire référence à Meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4b77e-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="4b77e-176">Si vous avez changé l’URL simple https://lync.contoso.com/Meet de https://lync.contoso.com/Meetingsà, l’url de base de Lync.contoso.com reste inchangée et aucune modification du DNS ou du certificat n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4b77e-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="4b77e-177">Néanmoins, chaque fois que vous modifiez un nom d’URL simple, vous devez exécuter **Enable-CsComputer** sur chaque réalisateur et serveur frontal pour enregistrer la modification.</span><span class="sxs-lookup"><span data-stu-id="4b77e-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b77e-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b77e-178">See Also</span></span>


[<span data-ttu-id="4b77e-179">Enregistrements DNS requis pour les URL simples dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b77e-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

