---
title: 'Lync Server 2013 : modèles utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cec912d84859baf77363764851d7abd1592b2760
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a><span data-ttu-id="02da5-102">Modèles utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02da5-102">User models in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02da5-103">_**Dernière modification de la rubrique :** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="02da5-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="02da5-104">Les modèles utilisateur décrits ici servent de base pour les mesures de planification de capacité et les recommandations décrites dans la rubrique [Capacity Planning for Lync Server 2013 using the user Models](lync-server-2013-capacity-planning-using-the-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="02da5-104">The user models described here provide the basis for the capacity planning measurements and recommendations described in [Capacity planning for Lync Server 2013 using the user models](lync-server-2013-capacity-planning-using-the-user-models.md).</span></span>

<div>

## <a name="lync-server-2013-user-models"></a><span data-ttu-id="02da5-105">Modèles utilisateur Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02da5-105">Lync Server 2013 User Models</span></span>

<span data-ttu-id="02da5-106">Le tableau suivant décrit le modèle utilisateur pour l’enregistrement, les contacts, la messagerie instantanée et la présence pour Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="02da5-106">The following table describes the user model for registration, contacts, instant messaging (IM), and presence for Lync Server 2013.</span></span>

### <a name="environment-and-registration-user-model"></a><span data-ttu-id="02da5-107">Modèle utilisateur pour l’environnement et l’inscription</span><span class="sxs-lookup"><span data-stu-id="02da5-107">Environment and Registration User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-108">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-108">Category</span></span></th>
<th><span data-ttu-id="02da5-109">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-110">Taille et distribution de déploiement</span><span class="sxs-lookup"><span data-stu-id="02da5-110">Deployment size and distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-111">Nous modélisons un déploiement large comptant trois sites centraux, avec un pool frontal par site.</span><span class="sxs-lookup"><span data-stu-id="02da5-111">We model a large deployment with three central sites, with one Front End pool per site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-112">Pourcentage d’utilisateurs Active Directory</span><span class="sxs-lookup"><span data-stu-id="02da5-112">Percentage of Active Directory users</span></span></p></td>
<td><p><span data-ttu-id="02da5-113">Nous partons du principe que 70% de tous les utilisateurs Active Directory de l’organisation sont activés pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="02da5-113">We assume that 70% of all Active Directory users in the organization are enabled for Lync Server.</span></span> <span data-ttu-id="02da5-114">80% des utilisateurs activés sont connectés à Lync Server chaque jour (concurrence de 80%).</span><span class="sxs-lookup"><span data-stu-id="02da5-114">80% of those enabled users are logged on to Lync Server each day (80% concurrency).</span></span> <span data-ttu-id="02da5-115">Les nombres d’employés dans le reste de cette section concernent des utilisateurs connectés simultanément.</span><span class="sxs-lookup"><span data-stu-id="02da5-115">The concurrent users are the basis for the numbers in the rest of this section.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-116">Modifications d’Active Directory</span><span class="sxs-lookup"><span data-stu-id="02da5-116">Active Directory changes</span></span></p></td>
<td><p><span data-ttu-id="02da5-117">Nous partons du principe que 0,5% du total des utilisateurs sont créés et activés pour Lync dans Active Directory chaque semaine, et que 0,5% du total des utilisateurs sont désactivés d’Active Directory et de Lync chaque semaine.</span><span class="sxs-lookup"><span data-stu-id="02da5-117">We assume that 0.5% of total users are created and enabled for Lync in Active Directory each week, and that 0.5% of total users are disabled from Active Directory and from Lync each week.</span></span> <span data-ttu-id="02da5-118">5 % des utilisateurs ont au moins un attribut Active Directory modifié chaque semaine.</span><span class="sxs-lookup"><span data-stu-id="02da5-118">5% of users have at least one Active Directory attribute changed each week.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-119">Groupes de distribution Active Directory</span><span class="sxs-lookup"><span data-stu-id="02da5-119">Active Directory distribution groups</span></span></p></td>
<td><p><span data-ttu-id="02da5-p103">Nous partons du principe que le nombre de groupes de distribution Active Directory dans l’organisation est égal à trois fois le nombre total des utilisateurs Active Directory. Les groupes de distribution ont les tailles suivantes :</span><span class="sxs-lookup"><span data-stu-id="02da5-p103">We assume that the number of Active Directory distribution groups in the organization is equal to three times the number of all users in Active Directory. The distribution groups have the following sizes:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-122">64 % se composent de 2 à 30 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-122">64% have 2-30 users</span></span></p></li>
<li><p><span data-ttu-id="02da5-123">13 % se composent de 31 à 50 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-123">13% have 31-50 users</span></span></p></li>
<li><p><span data-ttu-id="02da5-124">10 % se composent de 51 à 100 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-124">10% have 51-100 users</span></span></p></li>
<li><p><span data-ttu-id="02da5-125">13 % se composent de 101 à 500 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-125">13% have 101-500 users</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-126">Utilisateurs VoIP (Voix sur IP)</span><span class="sxs-lookup"><span data-stu-id="02da5-126">Voice over IP (VoIP) users</span></span></p></td>
<td><p><span data-ttu-id="02da5-127">60% des utilisateurs de Lync Server sont activés pour les communications unifiées (en d’autres points, leurs numéros de téléphone sont détenus par Lync Server).</span><span class="sxs-lookup"><span data-stu-id="02da5-127">60% of Lync Server users are enabled for unified communications (UC) (that is, their phone numbers are owned by Lync Server).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-128">Répartition des clients inscrits</span><span class="sxs-lookup"><span data-stu-id="02da5-128">Registered client distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-129">65% de clients exécutent le logiciel Lync 2013, notamment Lync et Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="02da5-129">65% of clients run Lync 2013 software, including Lync and Lync Phone Edition.</span></span></p>
<p><span data-ttu-id="02da5-130">30% des clients exécutent un logiciel client à partir d’une version antérieure de Lync.</span><span class="sxs-lookup"><span data-stu-id="02da5-130">30% of clients running client software from a previous version of Lync.</span></span></p>
<p><span data-ttu-id="02da5-131">5% des clients utilisant Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="02da5-131">5% of clients using Lync Web App.</span></span></p>
<p><span data-ttu-id="02da5-132">Si la mobilité est activée, nous partons du principe que 40% des utilisateurs utilisent la mobilité en même temps que les autres options de client inscrit précédemment citées.</span><span class="sxs-lookup"><span data-stu-id="02da5-132">If mobility is enabled, we assume that 40% of users are using mobility concurrently with the other previously cited registered client options.</span></span> <span data-ttu-id="02da5-133">Dans ce cas, le ratio point de présence (MPOP) client est égal à 1:1,9.</span><span class="sxs-lookup"><span data-stu-id="02da5-133">In this case the client multiple point of presence (MPOP) ratio is 1:1.9.</span></span> <span data-ttu-id="02da5-134">Si la mobilité est désactivée, le rapport de MPOP est de 1/1,5.</span><span class="sxs-lookup"><span data-stu-id="02da5-134">If mobility is disabled, the MPOP ratio is 1:1.5.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-135">Répartition des utilisateurs distants</span><span class="sxs-lookup"><span data-stu-id="02da5-135">Remote user distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-136">70 % des utilisateurs se connectent en interne.</span><span class="sxs-lookup"><span data-stu-id="02da5-136">70% of users connecting internally.</span></span></p>
<p><span data-ttu-id="02da5-137">30 % des utilisateurs se connectent par l’intermédiaire d’un serveur Edge et d’un directeur.</span><span class="sxs-lookup"><span data-stu-id="02da5-137">30% of users connecting through an Edge Server and a Director.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-138">Répartition des contacts</span><span class="sxs-lookup"><span data-stu-id="02da5-138">Contact distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-p105">Un utilisateur peut avoir 1 000 contacts au maximum. Cela concerne moins de 1 % des utilisateurs. Moins de 25 % des utilisateurs ont 100 contacts ou plus.</span><span class="sxs-lookup"><span data-stu-id="02da5-p105">The maximum number of contacts a user has is 1,000. Less than 1% of users have 1,000 contacts. Less than 25% of users have 100 or more contacts.</span></span></p>
<p><span data-ttu-id="02da5-p106">La moyenne est de 80 contacts pour les utilisateurs d’un nuage public. Parmi ces utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="02da5-p106">Average of 80 contacts for users with public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-p107">50 % des contacts font partie de l’entreprise. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="02da5-p107">50% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="02da5-146">40 % des contacts sont des utilisateurs de nuage public (utilisateurs AOL, Yahoo!, MSN ou Google Talk, par exemple).</span><span class="sxs-lookup"><span data-stu-id="02da5-146">40% of the contacts are public cloud users (such as users of AOL, Yahoo!, MSN, or Google Talk).</span></span></p></li>
<li><p><span data-ttu-id="02da5-147">10 % des contacts sont des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="02da5-147">10% of the contacts are from federated partners.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="02da5-148">À partir du 2012 1er septembre, la licence d’abonnement utilisateur Microsoft Lync Public IM Connectivity (« PIC USL ») n’est plus disponible à l’achat pour les contrats de nouveau ou de renouvellement.</span><span class="sxs-lookup"><span data-stu-id="02da5-148">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="02da5-149">Les clients disposant de licences actives seront en mesure de continuer à fédérer avec Yahoo !.</span><span class="sxs-lookup"><span data-stu-id="02da5-149">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="02da5-150">Messenger jusqu’à la date d’arrêt du service.</span><span class="sxs-lookup"><span data-stu-id="02da5-150">Messenger until the service shut down date.</span></span> <span data-ttu-id="02da5-151">Date de fin du 2014 juin pour AOL et Yahoo !</span><span class="sxs-lookup"><span data-stu-id="02da5-151">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="02da5-152">a été annoncé.</span><span class="sxs-lookup"><span data-stu-id="02da5-152">has been announced.</span></span> <span data-ttu-id="02da5-153">Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">prise en charge de la connectivité PIC de messagerie instantanée dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="02da5-153">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="02da5-154">La fonction USL PIC est une licence d’abonnement par utilisateur et par mois requise pour que Lync Server ou Office Communications Server se fédérer avec Yahoo !</span><span class="sxs-lookup"><span data-stu-id="02da5-154">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="02da5-155">Messenger.</span><span class="sxs-lookup"><span data-stu-id="02da5-155">Messenger.</span></span> <span data-ttu-id="02da5-156">La capacité de Microsoft à fournir ce service est subordonnée à la prise en charge de Yahoo !, l’accord sous-jacent de qui est en panne.</span><span class="sxs-lookup"><span data-stu-id="02da5-156">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="02da5-157">Plus que jamais, Lync est un outil puissant pour la connexion entre les organisations et les utilisateurs dans le monde entier.</span><span class="sxs-lookup"><span data-stu-id="02da5-157">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="02da5-158">La Fédération avec Windows Live Messenger ne requiert aucune licence utilisateur/périphérique supplémentaire au-delà de la licence d’accès client Lync standard.</span><span class="sxs-lookup"><span data-stu-id="02da5-158">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="02da5-159">La Fédération Skype est ajoutée à cette liste, ce qui permet aux utilisateurs de Lync d’atteindre des centaines de millions de personnes avec la messagerie instantanée et la voix.</span><span class="sxs-lookup"><span data-stu-id="02da5-159">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
</ul>
<p><span data-ttu-id="02da5-p111">La moyenne est de 50 contacts pour les utilisateurs ne pouvant pas se connecter à un nuage public. Parmi ces utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="02da5-p111">Average of 50 contacts for users without public cloud connectivity. Of these users:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-p112">80% des contacts font partie de l’entreprise. 10 % de ces utilisateurs sont des utilisateurs distants qui se connectent en dehors du pare-feu.</span><span class="sxs-lookup"><span data-stu-id="02da5-p112">80% of the contacts are within the organization. 10% of those users are remote users, connecting from outside the firewall.</span></span></p></li>
<li><p><span data-ttu-id="02da5-164">20 % des contacts sont des partenaires fédérés.</span><span class="sxs-lookup"><span data-stu-id="02da5-164">20% of the contacts are from federated partners.</span></span></p>
<p><span data-ttu-id="02da5-p113">Chaque utilisateur possède 1 groupe de distribution dans leur liste de contacts. Pour les tests de performance, nous partons du principe que les groupes de distribution sont toujours développés.</span><span class="sxs-lookup"><span data-stu-id="02da5-p113">Each user has 1 distribution group in their contact list. For performance testing, we assume that distribution groups are always expanded.</span></span></p></li>
</ul>
<p><span data-ttu-id="02da5-167">25 % des contacts d’un utilisateur passent par le protocole XMPP.</span><span class="sxs-lookup"><span data-stu-id="02da5-167">25% of a user’s contacts use XMPP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-168">Durée d’une session</span><span class="sxs-lookup"><span data-stu-id="02da5-168">Session time</span></span></p></td>
<td><p><span data-ttu-id="02da5-p114">En moyenne, un utilisateur se connecte 12 heures. Tous les utilisateurs se connectent dans les 120 minutes suivant le début de la session.</span><span class="sxs-lookup"><span data-stu-id="02da5-p114">The average user logon session lasts 12 hours. All users log on within 120 minutes of the start of the session.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a><span data-ttu-id="02da5-171">Modèle utilisateur pour la messagerie instantanée et la présence</span><span class="sxs-lookup"><span data-stu-id="02da5-171">IM and Presence User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-172">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-172">Category</span></span></th>
<th><span data-ttu-id="02da5-173">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-174">Sessions de messagerie instantanée d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="02da5-174">Peer-to-peer IM sessions</span></span></p></td>
<td><p><span data-ttu-id="02da5-175">En moyenne, chaque utilisateur ouvre six sessions de messagerie instantanée d’égal à égal par jour.</span><span class="sxs-lookup"><span data-stu-id="02da5-175">Each user averages six peer-to-peer IM sessions per day.</span></span></p>
<p><span data-ttu-id="02da5-176">10 messages instantanés par session.</span><span class="sxs-lookup"><span data-stu-id="02da5-176">10 instant messages per session.</span></span></p>
<p><span data-ttu-id="02da5-177">Chaque message est mis en correspondance avec deux messages SIP INFO et 2 messages SIP 200 OK (pour les indicateurs de statut tels&lt;que&gt; « typage »)</span><span class="sxs-lookup"><span data-stu-id="02da5-177">Each message is matched by two SIP INFO messages and 2 SIP 200 OK messages (for the status indicators such as “&lt;Name&gt; is Typing”)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-178">Interrogation de présence</span><span class="sxs-lookup"><span data-stu-id="02da5-178">Presence polling</span></span></p></td>
<td><p><span data-ttu-id="02da5-p115">Globalement, nous estimons l’interrogation de présence à 60 interrogations par utilisateur et par heure. La moyenne par utilisateur est estimée à :</span><span class="sxs-lookup"><span data-stu-id="02da5-p115">Overall, we assume presence polling at an average of 60 polls per user per hour. For each user, assume an average of:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-p116">Une interrogation par jour de présence des utilisateurs sous l’onglet d’organisation de l’utilisateur (mais pas dans la liste des contacts). En moyenne, 15 utilisateurs ne sont pas des contacts sous l’onglet d’organisation de l’utilisateur. Deux opérations d’affichage de carte de visite par jour.</span><span class="sxs-lookup"><span data-stu-id="02da5-p116">One poll per day of the presence of users in the user’s organization tab (but not Contacts list). Average number of non-contacts in the user’s organization tab is 15 users. Two contact card viewing operations per day.</span></span></p></li>
<li><p><span data-ttu-id="02da5-184">Une interrogation de présence à chaque fois que l’utilisateur clique sur le nom d’un autre utilisateur pour démarrer une conversation, estimée à une par heure.</span><span class="sxs-lookup"><span data-stu-id="02da5-184">One presence poll every time the user clicks another user to start a conversation, estimated at once per hour.</span></span></p></li>
<li><p><span data-ttu-id="02da5-p117">Six recherches utilisateur sont effectuées par heure. À chaque recherche, une interrogation par lot est envoyée à tout le monde dans la liste des résultats de recherche. Nous supposons que la taille moyenne des résultats de recherche est de 20. Pour les résultats restant à l’écran, l’interrogation par lot est actualisée toutes les 5 minutes. Nous partons du principe que deux actualisations se font par heure.</span><span class="sxs-lookup"><span data-stu-id="02da5-p117">Six user searches per hour. Every time a search is performed, a batch poll is sent for everyone in the search result list. We assume the average size of search results is 20. If the search results stay on screen, the batch poll is refreshed every 5 minutes; we assume that there will be two such refreshes per hour.</span></span></p></li>
<li><p><span data-ttu-id="02da5-189">Lorsque l’utilisateur ouvre ou prévisualise un message électronique dans Outlook, une interrogation de présence des utilisateurs dans les champs À : et CC : du message, estimée à cinq messages électroniques par heure et quatre utilisateurs par message.</span><span class="sxs-lookup"><span data-stu-id="02da5-189">When the user opens or previews an email in Outlook, a poll of the presence of users in the To: and CC: fields of the email, estimated at five emails per hour and four users per email.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-190">Abonnements aux informations de présence</span><span class="sxs-lookup"><span data-stu-id="02da5-190">Presence subscriptions</span></span></p></td>
<td><p><span data-ttu-id="02da5-p118">Lorsqu’un premier utilisateur ajoute un autre contact, il s’<em>abonne</em> à cinq catégories d’informations concernant ce contact. Des mises à jour de ces catégories d’informations sont automatiquement envoyées au premier utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02da5-p118">When one user adds another as a contact, the first user is <em>subscribing</em> to five categories of information about the second user. Updates of these categories of information are automatically sent to the first user.</span></span></p>
<p><span data-ttu-id="02da5-193">Pour chaque client, une seule demande d’abonnement par lot est envoyée pour obtenir l’état de présence d’une moyenne de 40 contacts, avec 40 boîtes de dialogue supplémentaires afin d’obtenir la présence des contacts fédérés.</span><span class="sxs-lookup"><span data-stu-id="02da5-193">For each client, a single batch subscription request is sent to obtain the presence state of an average of 40 contacts, with an additional 40 dialogs to obtain presence for federated contacts.</span></span></p>
<p><span data-ttu-id="02da5-194">La présence des membres d’un groupe de distribution développé se détermine par les abonnements de présence permanents, et non par l’interrogation, et est modelée sous forme d’une expansion par utilisateur toutes les 2 heures.</span><span class="sxs-lookup"><span data-stu-id="02da5-194">Presence for members of an expanded distribution group is found through persistent presence subscriptions, not polling, and is modeled as 1 expansion per user for each 2 hours.</span></span></p>
<p><span data-ttu-id="02da5-p119">Les <em>abonnements courts</em> se produisent si un utilisateur ouvre une session, qu’il existe un abonnement par lot pour tous les contacts de l’utilisateur et que l’utilisateur ferme sa session peu de temps après. Nous partons du principe que 6 abonnements courts se font par utilisateur et par heure, où chaque abonnement dure 10 minutes.</span><span class="sxs-lookup"><span data-stu-id="02da5-p119"><em>Short subscriptions</em> happen when a user logs in, there is a batch subscription for all the user’s contacts, and then the user soon logs off. We assume 6 short subscriptions per user per hour, where each subscription lasts 10 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-197">Publication de présence</span><span class="sxs-lookup"><span data-stu-id="02da5-197">Presence Publication</span></span></p></td>
<td><p><span data-ttu-id="02da5-198">En moyenne, l’état de présence est publié 4 fois par utilisateur et par heure, avec un maximum de 6 fois.</span><span class="sxs-lookup"><span data-stu-id="02da5-198">Presence state is published at an average of 4 publications per user per hour, with a maximum 6 per user per hour.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-199">Taille du document de présence</span><span class="sxs-lookup"><span data-stu-id="02da5-199">Presence Document Size</span></span></p></td>
<td><p><span data-ttu-id="02da5-200">La taille moyenne d’un document de présence complet est estimée à 4 Ko, avec un maximum de 25 Ko.</span><span class="sxs-lookup"><span data-stu-id="02da5-200">The average size of a complete presence document is assumed to be 4K, with a maximum of 25K.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-201">Le tableau suivant décrit le modèle utilisateur pour l’utilisation d’un carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="02da5-201">The following table describes the user model for address book use.</span></span>

### <a name="address-book-usage-user-model"></a><span data-ttu-id="02da5-202">Modèle utilisateur pour l’utilisation d’un carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="02da5-202">Address Book Usage User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-203">Mode de recherche d’un carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="02da5-203">Address Book search mode</span></span></th>
<th><span data-ttu-id="02da5-204">Utilisation</span><span class="sxs-lookup"><span data-stu-id="02da5-204">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-205">Requête web du carnet d’adresses uniquement (toutes les requêtes sont effectuées par le service de requête web du carnet d’adresses)</span><span class="sxs-lookup"><span data-stu-id="02da5-205">Address Book Web Query only (all queries performed by Address Book Web Query service)</span></span></p></td>
<td><p><span data-ttu-id="02da5-206">Quatre requêtes de préfixe quotidiennes par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02da5-206">Four prefix queries per user per day.</span></span></p>
<p><span data-ttu-id="02da5-p120">60 requêtes de recherche exacte quotidiennes par utilisateur. 40 % de ces requêtes sont traitées par lot, avec une moyenne de 20 contacts par requête. Les 60 % restants concernent un seul contact.</span><span class="sxs-lookup"><span data-stu-id="02da5-p120">60 exact search queries per user per day. 40% of those are batched, with an average of 20 contacts per query. The other 60% of the queries are for a single contact.</span></span></p>
<p><span data-ttu-id="02da5-p121">25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.</span><span class="sxs-lookup"><span data-stu-id="02da5-p121">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="02da5-212">Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="02da5-212">One total organization search query per user per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-p122">Mode mixte : utilisation du fichier de carnet d’adresses et des requêtes web Il s’agit du mode par défaut.</span><span class="sxs-lookup"><span data-stu-id="02da5-p122">Mixed mode, both address book file and web queries used. This is the default mode.</span></span></p></td>
<td><p><span data-ttu-id="02da5-215">Deux types de requêtes uniquement sont transmises sur le réseau, à savoir les requêtes de photos et les requêtes de recherche dans toute l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="02da5-215">Only two types of queries go to the network, the photo and total organizational search queries.</span></span></p>
<p><span data-ttu-id="02da5-p123">25 requêtes de photos quotidiennes par utilisateur. 24 concernent une seule photo, la dernière étant une requête par lot avec une moyenne de 20 contacts.</span><span class="sxs-lookup"><span data-stu-id="02da5-p123">25 photo queries per user per day. 24 are for a single photo, the other is a batch query with an average of 20 contacts.</span></span></p>
<p><span data-ttu-id="02da5-218">Une requête quotidienne par utilisateur de recherche dans toute l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="02da5-218">One total organization search query per user per day.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-219">Le tableau suivant décrit le modèle de conférence.</span><span class="sxs-lookup"><span data-stu-id="02da5-219">The following table describes the conferencing model.</span></span>

### <a name="conferencing-model"></a><span data-ttu-id="02da5-220">Modèle de conférence</span><span class="sxs-lookup"><span data-stu-id="02da5-220">Conferencing Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-221">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-221">Category</span></span></th>
<th><span data-ttu-id="02da5-222">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-222">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-223">Réunions planifiées &quot;et réunions&quot; maintenant</span><span class="sxs-lookup"><span data-stu-id="02da5-223">Scheduled meetings versus &quot;Meet now&quot; meetings</span></span></p></td>
<td><p><span data-ttu-id="02da5-224">60 % des réunions sont planifiées, 40 % ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="02da5-224">60% scheduled, 40% unscheduled.</span></span></p>
<p><span data-ttu-id="02da5-225">De toutes les réunions planifiées, nous partons du principe que 80 % correspondent à des conférences affectées et qui sont des occurrences de conférences périodiques. 10 % sont des réunions ouvertes uniques. 8 % correspondent à des réunions anonymes uniques et 2 % sont des réunions fermées uniques.</span><span class="sxs-lookup"><span data-stu-id="02da5-225">Of the scheduled meetings, we assume that 80% are assigned conferences, which are occurences of recurring conferences; 10% are one-time open meetings; 8% are one-time anonymous meetings, and 2% are one-time closed meetings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-226">Répartition des clients de conférence</span><span class="sxs-lookup"><span data-stu-id="02da5-226">Conferencing client distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-227">Pour les réunions planifiées :</span><span class="sxs-lookup"><span data-stu-id="02da5-227">For scheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-228">65% des utilisateurs de conférence utilisent Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="02da5-228">65% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="02da5-229">5% des utilisateurs de conférence utilisent Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="02da5-229">5% of conferencing users use Microsoft Lync Web App.</span></span></p></li>
<li><p><span data-ttu-id="02da5-230">30% des utilisateurs de conférence utilisent des clients antérieurs, notamment Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 et Microsoft Office Communicator Web Access (version 2007).</span><span class="sxs-lookup"><span data-stu-id="02da5-230">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul>
<p><span data-ttu-id="02da5-231">Pour les réunions non planifiées :</span><span class="sxs-lookup"><span data-stu-id="02da5-231">For unscheduled meetings:</span></span></p>
<ul>
<li><p><span data-ttu-id="02da5-232">70% des utilisateurs de conférence utilisent Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="02da5-232">70% of conferencing users use Lync 2013.</span></span></p></li>
<li><p><span data-ttu-id="02da5-233">30% des utilisateurs de conférence utilisent des clients antérieurs, notamment Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 et Microsoft Office Communicator Web Access (version 2007).</span><span class="sxs-lookup"><span data-stu-id="02da5-233">30% of conferencing users use earlier clients, including Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007, and Microsoft Office Communicator Web Access (2007 release).</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-234">Simultanéité des réunions</span><span class="sxs-lookup"><span data-stu-id="02da5-234">Meeting concurrency</span></span></p></td>
<td><p><span data-ttu-id="02da5-p124">5 % des utilisateurs participeront à des conférences pendant les heures de travail. Ainsi, dans un pool de 80 000 utilisateurs, il peut arriver que 4 000 utilisateurs participent à tout moment à des conférences.</span><span class="sxs-lookup"><span data-stu-id="02da5-p124">5% of users will be in conferences during working hours. Thus, in an 80,000-user pool, as many as 4,000 users might be in conferences at any one time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-237">Répartition des appels audio d’une réunion</span><span class="sxs-lookup"><span data-stu-id="02da5-237">Meeting audio distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-238">40 % d’appels audio VoIP et de conférences rendez-vous combinés, avec un ratio d’utilisateurs VoIP par rapport aux utilisateurs d’appels entrants égal à 3:1.</span><span class="sxs-lookup"><span data-stu-id="02da5-238">40% mixed VoIP audio and dial-in conferencing, with a 3:1 ratio of VoIP users to dial-in users.</span></span></p>
<p><span data-ttu-id="02da5-239">35 % d’appels audio VoIP uniquement.</span><span class="sxs-lookup"><span data-stu-id="02da5-239">35% VoIP audio only.</span></span></p>
<p><span data-ttu-id="02da5-240">15 % d’audioconférences rendez-vous uniquement.</span><span class="sxs-lookup"><span data-stu-id="02da5-240">15% dial-in conferencing audio only.</span></span></p>
<p><span data-ttu-id="02da5-241">10 % sans appel audio (conférences de messagerie instantanée uniquement, avec une moyenne de cinq messages envoyés par utilisateur).</span><span class="sxs-lookup"><span data-stu-id="02da5-241">10% no audio (IM-only conferences, with an average of five messages sent per user).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-242">Utilisation de divers médias dans le cadre des conférences</span><span class="sxs-lookup"><span data-stu-id="02da5-242">Media mix for conferences</span></span></p></td>
<td><p><span data-ttu-id="02da5-243">75 % des conférences ont lieu sur Internet, notamment par des méthodes de collaboration audio ou autres.</span><span class="sxs-lookup"><span data-stu-id="02da5-243">75% of conferences are web conferences, which include audio plus some other collaboration modalities.</span></span></p>
<p><span data-ttu-id="02da5-244">Pour ces conférences, les autres méthodes de collaboration sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="02da5-244">For these conferences, the other collaboration methods are as follows:</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="02da5-245">Le total des nombres suivants dépasse 100 %, car une conférence peut faire appel à plusieurs méthodes de collaboration.</span><span class="sxs-lookup"><span data-stu-id="02da5-245">These numbers add up to more than 100% because one conference can have multiple collaboration methods.</span></span>


</div>
<ul>
<li><p><span data-ttu-id="02da5-p125">50 % utilisent le partage d’application. Nous supposons qu’un utilisateur envoie des données avec un pic de 1,1 Mo par seconde.</span><span class="sxs-lookup"><span data-stu-id="02da5-p125">50% add application sharing. We assume one users sends data at a peak of 1.1 MB per second.</span></span></p></li>
<li><p><span data-ttu-id="02da5-248">50 % font appel à la messagerie instantanée (avec en moyenne 2 messages par utilisateur).</span><span class="sxs-lookup"><span data-stu-id="02da5-248">50% add instant messaging (with an average of 2 messages per user).</span></span></p></li>
<li><p><span data-ttu-id="02da5-p126">20 % ont recours à la collaboration de données, à travers de PowerPoint ou d’un tableau blanc, par exemple. En moyenne, 2 fichiers PowerPoint d’environ 10 Mo (sans vidéo incorporée) ou 30 Mo (avec vidéo incorporée) chacun sont présentés au cours d’une conférence. On dénombre 20 annotations par tableau blanc en moyenne.</span><span class="sxs-lookup"><span data-stu-id="02da5-p126">20% add data collaboration, including PowerPoint or whiteboard In these, an average of 2 PowerPoint files presented per conference, with an average PowerPoint file size of 10 MB (without embedded video) or 30 MB (with embedded video). Average of 20 annotations per whiteboard.</span></span></p></li>
<li><p><span data-ttu-id="02da5-p127">20 % utilisent de la vidéo. De ces utilisateurs, 70 % participent à des conférences activées pour la vidéo multiview, où chaque utilisateur reçoit 2 à 3 flux vidéo.</span><span class="sxs-lookup"><span data-stu-id="02da5-p127">20% add video. Of these users, 70% are in conferences enabled for multiview video, where each user receives 2-3 video streams.</span></span></p></li>
<li><p><span data-ttu-id="02da5-253">15 % ajoutent des notes partagées.</span><span class="sxs-lookup"><span data-stu-id="02da5-253">15% add shared notes.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-254">Répartition des participants aux réunions</span><span class="sxs-lookup"><span data-stu-id="02da5-254">Meeting participant distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-255">50 % d’utilisateurs internes authentifiés.</span><span class="sxs-lookup"><span data-stu-id="02da5-255">50% internal, authenticated users.</span></span></p>
<p><span data-ttu-id="02da5-256">25 % d’utilisateurs distants authentifiés.</span><span class="sxs-lookup"><span data-stu-id="02da5-256">25% remote access, authenticated users.</span></span></p>
<p><span data-ttu-id="02da5-257">15 % d’utilisateurs anonymes.</span><span class="sxs-lookup"><span data-stu-id="02da5-257">15% anonymous users.</span></span></p>
<p><span data-ttu-id="02da5-258">10 % d’utilisateurs fédérés.</span><span class="sxs-lookup"><span data-stu-id="02da5-258">10% federated users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-259">Répartition de la participation aux réunions</span><span class="sxs-lookup"><span data-stu-id="02da5-259">Meeting join distribution</span></span></p></td>
<td><p><span data-ttu-id="02da5-260">Il est simulé que les utilisateurs se joignent à la réunion dans les 5 premières minutes.</span><span class="sxs-lookup"><span data-stu-id="02da5-260">Users are simulated as joining the meeting within the first 5 minutes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-261">Dans les pools frontaux standard, Lync Server 2013 a une taille de réunion maximale prise en charge de 250 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-261">In regular Front End pools, Lync Server 2013 has a maximum supported meeting size of 250 users.</span></span> <span data-ttu-id="02da5-262">Chaque pool peut héberger 250 utilisateurs au cours d’une même réunion.</span><span class="sxs-lookup"><span data-stu-id="02da5-262">Each pool can host one 250-user meeting at a time.</span></span> <span data-ttu-id="02da5-263">Quand une réunion regroupant autant de participants a lieu, le pool peut également héberger d’autres conférences plus petites.</span><span class="sxs-lookup"><span data-stu-id="02da5-263">While this large meeting is occurring, the pool can also host other smaller conferences.</span></span> <span data-ttu-id="02da5-264">Vous pouvez aussi prendre en charge les réunions rassemblant jusqu’à 1 000 utilisateurs en configurant un pool dédié pour les héberger.</span><span class="sxs-lookup"><span data-stu-id="02da5-264">Additionally, you can support meetings of up to 1000 users by setting up a dedicated pool to host these meetings.</span></span> <span data-ttu-id="02da5-265">Pour plus d’informations, reportez-vous à la rubrique [prise en charge des grandes réunions dans Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="02da5-265">For details, see [Support for large meetings in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).</span></span>

<span data-ttu-id="02da5-266">Les conférences sont simulées comme suit :</span><span class="sxs-lookup"><span data-stu-id="02da5-266">Conferences were simulated as follows:</span></span>

  - <span data-ttu-id="02da5-267">85 % des conférences comptent quatre participants.</span><span class="sxs-lookup"><span data-stu-id="02da5-267">85% of conferences had four participants.</span></span>

  - <span data-ttu-id="02da5-268">10 % des conférences comptent six participants.</span><span class="sxs-lookup"><span data-stu-id="02da5-268">10% of conferences had six participants.</span></span>

  - <span data-ttu-id="02da5-269">5 % des conférences comptent 11 participants.</span><span class="sxs-lookup"><span data-stu-id="02da5-269">5% of conferences had 11 participants.</span></span>

  - <span data-ttu-id="02da5-270">Une conférence importante compte 250 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="02da5-270">One large conference of 250 users.</span></span>

<span data-ttu-id="02da5-271">Le tableau suivant fournit des détails sur le modèle utilisateur pour les conférences auxquelles participent des utilisateurs d’appels entrants.</span><span class="sxs-lookup"><span data-stu-id="02da5-271">The following table provides details about the user model for conferences involving dial-in users.</span></span>

### <a name="dial-in-conferencing-user-model"></a><span data-ttu-id="02da5-272">Modèle utilisateur pour les conférences rendez-vous</span><span class="sxs-lookup"><span data-stu-id="02da5-272">Dial-In Conferencing User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-273">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-273">Category</span></span></th>
<th><span data-ttu-id="02da5-274">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-275">Authentifié/anonyme</span><span class="sxs-lookup"><span data-stu-id="02da5-275">Authenticated/anonymous</span></span></p></td>
<td><p><span data-ttu-id="02da5-p129">70 % des appelants se joignent anonymement et sont invités à entrer un nom enregistré.</span><span class="sxs-lookup"><span data-stu-id="02da5-p129">70% of callers join as anonymous and are prompted for a recorded name. 30% join as authenticated users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-278">Durée de conversation et attente musicale</span><span class="sxs-lookup"><span data-stu-id="02da5-278">Call duration and music on hold</span></span></p></td>
<td><p><span data-ttu-id="02da5-279">Durée moyenne de conversation sans attente musicale : 50 secondes.</span><span class="sxs-lookup"><span data-stu-id="02da5-279">Average call duration without music on hold: 50 seconds.</span></span></p>
<p><span data-ttu-id="02da5-280">50 % des appelants entendent une musique d’attente pendant 5 minutes en moyenne.</span><span class="sxs-lookup"><span data-stu-id="02da5-280">50% of call-in users hear music on hold, for an average of 5 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02da5-281">Numérotation en fréquences vocales ou DTMF (Dual Tone Multi-Frequency)</span><span class="sxs-lookup"><span data-stu-id="02da5-281">Dual-tone multifrequency (DTMF)</span></span></p></td>
<td><p><span data-ttu-id="02da5-p130">15 % des conférences rendez-vous ont des responsables téléphoniques. 10 % des conférences mixtes qui incluent des utilisateurs d’appels entrants ont également des responsables téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="02da5-p130">15% of conferences that are dial-in only have phone leaders. 10% of mixed conferences that include dial-in users also have phone leaders.</span></span></p>
<p><span data-ttu-id="02da5-284">20 % des responsables téléphoniques utilisent deux commandes DTMF par conférence.</span><span class="sxs-lookup"><span data-stu-id="02da5-284">20% of phone leaders use 2 DTMF commands per conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-285">Langues d’annonce</span><span class="sxs-lookup"><span data-stu-id="02da5-285">Announcement languages</span></span></p></td>
<td><p><span data-ttu-id="02da5-286">Les simulations utilisent l’anglais comme langue pour les annonces.</span><span class="sxs-lookup"><span data-stu-id="02da5-286">Simulations use English as the announcement language.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-287">Le tableau suivant fournit des détails sur le modèle utilisateur pour les salles d’attente de conférence.</span><span class="sxs-lookup"><span data-stu-id="02da5-287">The following table provides details about the user model for conference lobbies.</span></span>

### <a name="conference-lobby-user-model"></a><span data-ttu-id="02da5-288">Modèle d’utilisateur pour les salles d’attente de conférence</span><span class="sxs-lookup"><span data-stu-id="02da5-288">Conference Lobby User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-289">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-289">Category</span></span></th>
<th><span data-ttu-id="02da5-290">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-290">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-291">Nombre d’utilisateurs dans la salle d’attente</span><span class="sxs-lookup"><span data-stu-id="02da5-291">Number of users in lobby</span></span></p></td>
<td><p><span data-ttu-id="02da5-292">5 % des utilisateurs d’appels entrants et 25 % d’utilisateurs d’autres catégories passent par la salle d’attente.</span><span class="sxs-lookup"><span data-stu-id="02da5-292">5% of dial-in users go through the lobby, and 25% of other users go through the lobby</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-293">Autorisation à quitter la salle d’attente</span><span class="sxs-lookup"><span data-stu-id="02da5-293">Admitting from lobby</span></span></p></td>
<td><p><span data-ttu-id="02da5-294">Pendant les simulations, le présentateur autorise tous les utilisateurs à participer avant l’expiration du délai du client.</span><span class="sxs-lookup"><span data-stu-id="02da5-294">In simulations, all users were admitted by the presenter before client timeout.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-295">Le tableau suivant décrit le modèle utilisateur pour d’autres sessions d’égal à égal.</span><span class="sxs-lookup"><span data-stu-id="02da5-295">The following table describes the user model for other peer-to-peer sessions.</span></span>

### <a name="peer-to-peer-sessions-user-model"></a><span data-ttu-id="02da5-296">Modèle utilisateur pour les sessions d’égal à égal</span><span class="sxs-lookup"><span data-stu-id="02da5-296">Peer-to-Peer Sessions User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-297">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-297">Category</span></span></th>
<th><span data-ttu-id="02da5-298">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-298">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-299">Partage d’application</span><span class="sxs-lookup"><span data-stu-id="02da5-299">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="02da5-300">Chaque utilisateur participe à cinq sessions de partage d’application d’égal à égal par mois, avec une moyenne de 0,25 session par jour.</span><span class="sxs-lookup"><span data-stu-id="02da5-300">Each user participates in 5 peer-to-peer application sharing sessions per month, for an average of 0.25 sessions per day.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-301">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="02da5-301">File transfer</span></span></p></td>
<td><p><span data-ttu-id="02da5-p131">Chaque utilisateur participe à une session de transfert de fichiers d’égal à égal par mois (dans le cadre d’une session de messagerie instantanée), avec une moyenne de 0,05 session par jour. En moyenne, le volume transféré au cours d’une session est de 1 Mo.</span><span class="sxs-lookup"><span data-stu-id="02da5-p131">Each user participates in 1 peer-to-peer file transfer session per month (as part of an IM session), for an average of 0.05 sessions per day. The average session file size transferred is 1 MB.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="02da5-304">Le tableau suivant décrit le modèle utilisateur pour les stratégies.</span><span class="sxs-lookup"><span data-stu-id="02da5-304">The following table describes the user model for policies.</span></span>

### <a name="policies-user-model"></a><span data-ttu-id="02da5-305">Modèle utilisateur des stratégies</span><span class="sxs-lookup"><span data-stu-id="02da5-305">Policies User Model</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="02da5-306">Catégorie</span><span class="sxs-lookup"><span data-stu-id="02da5-306">Category</span></span></th>
<th><span data-ttu-id="02da5-307">Description</span><span class="sxs-lookup"><span data-stu-id="02da5-307">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02da5-308">Stratégies de conférence, de présence et d’archivage</span><span class="sxs-lookup"><span data-stu-id="02da5-308">Conferencing, Presence, and Archiving Policies</span></span></p></td>
<td><p><span data-ttu-id="02da5-309">Nous partons du principe qu’il y a une stratégie globale, 10 stratégies de conférence, 4 stratégies d’archivage et 10 stratégies de présence.</span><span class="sxs-lookup"><span data-stu-id="02da5-309">We assume that there is one global policy, 10 tag conferencing policies, 4 Archiving policies, and 10 tag presence policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02da5-310">Stratégie de la voix</span><span class="sxs-lookup"><span data-stu-id="02da5-310">Voice Policy</span></span></p></td>
<td><p><span data-ttu-id="02da5-311">Nous supposons qu’il existe une stratégie globale et 2 stratégies de mots clés par site.</span><span class="sxs-lookup"><span data-stu-id="02da5-311">We assume that there is one global policy and 2 tag policies per site.</span></span> <span data-ttu-id="02da5-312">100 % des sites ont une stratégie de site et 30 % des utilisateurs sont gérés par une stratégie par utilisateur.</span><span class="sxs-lookup"><span data-stu-id="02da5-312">100% of sites have a site policy, and 30% of users have a per-user policy assigned.</span></span> <span data-ttu-id="02da5-313">Nous prenons pour hypothèse un plan de numérotation par site et deux itinéraires par site.</span><span class="sxs-lookup"><span data-stu-id="02da5-313">We assume one dial plan per site and two routes per site.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a><span data-ttu-id="02da5-314">Heure de pointe</span><span class="sxs-lookup"><span data-stu-id="02da5-314">Busy Hour</span></span>

<span data-ttu-id="02da5-p133">Pour les sessions d’égal à égal, la charge maximale est calculée à partir des « tentatives d’appels aux heures de pointe » (BHCA, Busy Hour Call Attempt). Cette mesure utilisée dans le secteur de la téléphonie suppose que 50 % de tous les appels d’une journée seront passés en 20 % du temps. Elle se calcule à l’aide de la formule suivante :</span><span class="sxs-lookup"><span data-stu-id="02da5-p133">For peer-to-peer sessions, peak load is calculated using busy hour call attempts (BHCA). This voice industry term assumes that 50% of all calls for the day will be completed in 20% of the time. It is calculated using the following formula:</span></span>

`BHCA=(total calls * 0.5) / 1.6`

<span data-ttu-id="02da5-318">Au cours d’un test de performance, l’heure de pointe a été simulée en exécutant des sessions VoIP et d’autres sessions d’égal à égal aux heures de pointe pendant au moins 1,6 heure par jour.</span><span class="sxs-lookup"><span data-stu-id="02da5-318">Performance testing simulated busy hour by running VoIP and other peer-to-peer sessions at a busy hour load for at least 1.6 hours per day.</span></span>

<span data-ttu-id="02da5-p134">Le pic de charge des conférences suppose que 75 % de toutes les conférences d’une journée de huit heures ont lieu pendant quatre heures de pointe. Ces heures de pointe représentent 1,5 fois la charge de conférence moyenne.</span><span class="sxs-lookup"><span data-stu-id="02da5-p134">Conferencing peak load assumes that 75% of all conferences for an eight-hour day happen in 4 peak time hours. Those peak hours have 1.5 times the average conferencing load.</span></span>

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a><span data-ttu-id="02da5-321">Appels voix entreprise vers RTC</span><span class="sxs-lookup"><span data-stu-id="02da5-321">Enterprise Voice to PSTN Calls</span></span>

<span data-ttu-id="02da5-322">Les hypothèses suivantes s’appliquent aux appels vocaux d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="02da5-322">The following assumptions apply to Enterprise Voice calls:</span></span>

  - <span data-ttu-id="02da5-323">50% des utilisateurs sont activés pour voix entreprise, et 60% de ces utilisateurs sont activés pour les appels RTC.</span><span class="sxs-lookup"><span data-stu-id="02da5-323">50% of users are enabled for Enterprise Voice, and 60% of these users are enabled for PSTN calling.</span></span>

  - <span data-ttu-id="02da5-p135">Chacun de ces derniers utilisateurs passe 4 appels PSTN pendant les heures de pointe. Chaque appel dure 3 minutes.</span><span class="sxs-lookup"><span data-stu-id="02da5-p135">Each of these users enabled for PSTN calling makes 4 PSTN calls during the busy hour. Each call duration is 3 minutes.</span></span>

  - <span data-ttu-id="02da5-326">65 % des appels vocaux PSTN utilisent le contournement de média.</span><span class="sxs-lookup"><span data-stu-id="02da5-326">65% of these PSTN voice calls use media bypass.</span></span>

</div>

<div>

## <a name="mobility"></a><span data-ttu-id="02da5-327">Mobilité</span><span class="sxs-lookup"><span data-stu-id="02da5-327">Mobility</span></span>

<span data-ttu-id="02da5-p136">40 % des utilisateurs inscrits sont présumés être activés pour la mobilité. Pour chacun d’entre eux, nous partons du principe que l’activité du client mobile vient s’ajouter à celle des autres instances MPOP de l’utilisateur, à l’exception des interactions en conférence pour lesquelles le client de mobilité n’est qu’un autre type de client pouvant être utilisé pour participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="02da5-p136">40% of registered users are assumed to be enabled for Mobility. For each user that has mobility enabled, we assume that the activity of the mobile client is additive to that of the other MPOP instances for that user, with the exception of conferencing interactions, for which the mobility client is just another client type that can be used to participate in conferences.</span></span>

</div>

<div>

## <a name="persistent-chat"></a><span data-ttu-id="02da5-330">Conversation permanente</span><span class="sxs-lookup"><span data-stu-id="02da5-330">Persistent Chat</span></span>

<span data-ttu-id="02da5-331">Nous supposons que 25 % des utilisateurs inscrits participent à des sessions de chat permanentes avec les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="02da5-331">We assume that 25% of registered users will be involved in Persistent chat sessions, with the following characteristics:</span></span>

  - <span data-ttu-id="02da5-332">1,5 salles de conversation par utilisateur sont prévues en moyenne.</span><span class="sxs-lookup"><span data-stu-id="02da5-332">An average of 1.5 chat rooms per user</span></span>

  - <span data-ttu-id="02da5-333">Chaque salle de conversation engendre 12 demandes d’interrogation par heure, en ciblant une moyenne de 10 utilisateurs chacune.</span><span class="sxs-lookup"><span data-stu-id="02da5-333">Each chat room results in 12 polling requests per hour, targeting an average of 10 users each</span></span>

</div>

<div>

## <a name="response-group-and-call-park"></a><span data-ttu-id="02da5-334">Response Group et parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="02da5-334">Response Group and Call Park</span></span>

<span data-ttu-id="02da5-p137">Nous supposons que 0,15 % des utilisateurs inscrits appartiennent à des groupes Response group. Nous partons du principe que 0,02 % des utilisateurs inscrits ont des appels parqués à tout moment donné.</span><span class="sxs-lookup"><span data-stu-id="02da5-p137">We assume that 0.15% of registered users belong to response groups. We assume that 0.02% of registered users have parked calls at any given point of time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

