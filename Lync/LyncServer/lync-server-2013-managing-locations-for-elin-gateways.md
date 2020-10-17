---
title: 'Lync Server 2013 : gestion des emplacements pour les passerelles ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e33f05f0a05b1225f1687faa00cf48af02fa1410
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498161"
---
# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="32659-102">Gestion des emplacements pour les passerelles ELIN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32659-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32659-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="32659-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="32659-104">Pour que Lync Server fournisse automatiquement des emplacements pour les clients au sein d’un réseau, vous devez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="32659-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="32659-105">Remplissez la base de données du service informations d’emplacement avec un câblage réseau, et incluez les numéros d’identification des emplacements de secours (numéros) dans le champ CompanyName.</span><span class="sxs-lookup"><span data-stu-id="32659-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="32659-106">Publiez les emplacements afin qu’ils soient disponibles pour les clients dans votre réseau.</span><span class="sxs-lookup"><span data-stu-id="32659-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="32659-107">Téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.</span><span class="sxs-lookup"><span data-stu-id="32659-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="32659-108">Pour plus d’informations sur la façon d’effectuer ces tâches, voir [configure the location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="32659-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="32659-109">Les emplacements ajoutés à la base de données de l’emplacement central ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Lync Server Management Shell et sont répliqués dans les magasins locaux du pool.</span><span class="sxs-lookup"><span data-stu-id="32659-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="32659-110">Pour plus d’informations, voir <A href="lync-server-2013-publish-the-location-database.md">publish the location Database from Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="32659-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="32659-111">Cette section décrit les éléments à prendre en compte lorsque vous prévoyez de mettre à jour ou maintenir la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="32659-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="32659-112">Planification des emplacements d’urgence</span><span class="sxs-lookup"><span data-stu-id="32659-112">Planning Emergency Locations</span></span>

<span data-ttu-id="32659-113">Lorsque vous utilisez des passerelles ELIN, vous remplissez la base de données du service informations d’emplacement avec l’adresse postale, un emplacement spécifique au sein d’un bâtiment et au moins un ELIN pour chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="32659-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="32659-114">Durant la phase de planification, il est recommandé de décider du nom des emplacements et de l’affectation des numéros d’identification de l’emplacement en cas d’urgence.</span><span class="sxs-lookup"><span data-stu-id="32659-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="32659-115">Planification des noms d’emplacement</span><span class="sxs-lookup"><span data-stu-id="32659-115">Planning Location Names</span></span>

<span data-ttu-id="32659-116">Le champ **emplacement** du service informations d’emplacement, qui contient l’emplacement spécifique au sein d’un bâtiment, a une longueur maximale de 20 caractères (espaces compris).</span><span class="sxs-lookup"><span data-stu-id="32659-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="32659-117">En respectant cette limite, essayez d’inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="32659-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="32659-p104">Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.</span><span class="sxs-lookup"><span data-stu-id="32659-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="32659-121">Identificateur d’emplacement qui aide les utilisateurs à vérifier que leur client Lync a sélectionné l’emplacement correct.</span><span class="sxs-lookup"><span data-stu-id="32659-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="32659-122">Le client Lync concatène et affiche automatiquement les champs **Location** et **City** découverts dans son en-tête.</span><span class="sxs-lookup"><span data-stu-id="32659-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="32659-123">Il est recommandé d’ajouter l’adresse postale de l’immeuble à chaque identificateur d’emplacement (par exemple, « 1st Floor \<street number\> »).</span><span class="sxs-lookup"><span data-stu-id="32659-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="32659-124">Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.</span><span class="sxs-lookup"><span data-stu-id="32659-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="32659-125">Si l’emplacement est approximatif car il est déterminé par un point d’accès sans fil, vous pouvez ajouter le mot Near (par exemple, « À proximité du 1er étage 1234 »).</span><span class="sxs-lookup"><span data-stu-id="32659-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="32659-126">Planification des numéros d’identification de l’emplacement en cas d’urgence (ELIN)</span><span class="sxs-lookup"><span data-stu-id="32659-126">Planning ELINs</span></span>

<span data-ttu-id="32659-p106">Après avoir déterminé comment diviser l’espace de votre bâtiment en emplacements, vous devez décider du nombre de numéros ELIN à affecter à chaque emplacement. Par exemple, dans un immeuble à plusieurs étages ou multilocatif, différentes zones ERL peuvent être affectées à différentes zones d’urgence. En général, chaque étage d’un immeuble est désigné comme un emplacement. Chaque emplacement se voit alors affecté un ou plusieurs numéros ELIN, qui sont utilisés comme numéros d’appel durant un appel d’urgence. Contactez votre opérateur RTC pour connaître les numéros de téléphone que vous pouvez utiliser pour les numéros ELIN. Le tableau suivant fournit des exemples d’emplacements pour une adresse postale spécifique.</span><span class="sxs-lookup"><span data-stu-id="32659-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="32659-133">Exemples d’affectations d’emplacements et de numéros ELIN</span><span class="sxs-lookup"><span data-stu-id="32659-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32659-134">Zone de l’immeuble</span><span class="sxs-lookup"><span data-stu-id="32659-134">Building Area</span></span></th>
<th><span data-ttu-id="32659-135">Emplacement</span><span class="sxs-lookup"><span data-stu-id="32659-135">Location</span></span></th>
<th><span data-ttu-id="32659-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="32659-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="32659-137">Premier étage</span><span class="sxs-lookup"><span data-stu-id="32659-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="32659-138">0,1</span><span class="sxs-lookup"><span data-stu-id="32659-138">1</span></span></p></td>
<td><p><span data-ttu-id="32659-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="32659-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="32659-140">Deuxième étage</span><span class="sxs-lookup"><span data-stu-id="32659-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="32659-141">n°2</span><span class="sxs-lookup"><span data-stu-id="32659-141">2</span></span></p></td>
<td><p><span data-ttu-id="32659-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="32659-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="32659-143">Troisième étage</span><span class="sxs-lookup"><span data-stu-id="32659-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="32659-144">3</span><span class="sxs-lookup"><span data-stu-id="32659-144">3</span></span></p></td>
<td><p><span data-ttu-id="32659-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="32659-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="32659-146">Les emplacements définis doivent satisfaire les exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="32659-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="32659-147">être conformes aux réglementations locales et nationales/régionales en termes de surface maximale par emplacement et nombre d’emplacements par adresse postale ;</span><span class="sxs-lookup"><span data-stu-id="32659-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="32659-148">être assez spécifiques pour faciliter la localisation de l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="32659-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="32659-149">Remplissage de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="32659-149">Populating the Location Database</span></span>

<span data-ttu-id="32659-150">Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="32659-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="32659-151">**Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="32659-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="32659-p107">Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?</span><span class="sxs-lookup"><span data-stu-id="32659-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="32659-154">**Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="32659-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="32659-155">En utilisant l’option service d’informations d’emplacement secondaire de Lync Server pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors connexion.</span><span class="sxs-lookup"><span data-stu-id="32659-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="32659-156">Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="32659-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="32659-157">Cela signifie que le service d’informations d’emplacement peut retourner plusieurs adresses provenant du service d’informations d’emplacement secondaire à un client Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32659-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="32659-158">L’utilisateur peut alors choisir l’emplacement le plus approprié.</span><span class="sxs-lookup"><span data-stu-id="32659-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="32659-159">Pour s’intégrer au service d’informations d’emplacement, la base de données tierce doit suivre le schéma de demande/réponse d’emplacement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="32659-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="32659-160">Pour plus d’informations, reportez-vous à <https://go.microsoft.com/fwlink/p/?linkid=213819> .</span><span class="sxs-lookup"><span data-stu-id="32659-160">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="32659-161">Pour plus d’informations sur le déploiement d’un service d’informations d’emplacement secondaire, reportez-vous à la rubrique [Configure a Secondary location information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="32659-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="32659-162">Pour plus d’informations sur le remplissage de la base de données d’emplacements, voir [configure the location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="32659-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="32659-163">Mise à jour de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="32659-163">Maintaining the Location Database</span></span>

<span data-ttu-id="32659-p110">Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="32659-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="32659-166">**Comment allez-vous mettre à jour la base de données d’emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="32659-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="32659-p111">L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?</span><span class="sxs-lookup"><span data-stu-id="32659-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="32659-169">**Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**</span><span class="sxs-lookup"><span data-stu-id="32659-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="32659-170">Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="32659-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="32659-171">Si l’application SNMP renvoie une adresse IP ou un ID de port qui n’est pas inclus dans la base de données, le service informations d’emplacement ne pourra pas renvoyer un emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="32659-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

