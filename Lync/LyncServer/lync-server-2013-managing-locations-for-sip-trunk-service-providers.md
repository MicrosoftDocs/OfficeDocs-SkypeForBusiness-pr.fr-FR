---
title: 'Lync Server 2013: gestion des emplacements pour les fournisseurs de service SIP Trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eba237ae4e984169a354339ce0222dfd58f324c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="4795c-102">Gestion des emplacements pour les fournisseurs de services SIP Trunk dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4795c-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4795c-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4795c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4795c-104">Pour configurer Lync Server de façon à ce qu’il détecte automatiquement les clients au sein d’un réseau, vous devez renseigner la base de données de service informations d’emplacement auprès d’un Wiremap réseau et publier les emplacements, ou lier une base de données externe contenant déjà le bon mappages.</span><span class="sxs-lookup"><span data-stu-id="4795c-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="4795c-105">Dans le cadre de ce processus, vous devez valider les adresses géographiques des emplacements avec votre fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="4795c-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="4795c-106">Pour plus d’informations, reportez-vous à [la rubrique Configurer la base de données de localisation dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4795c-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4795c-107">Renseignez la base de données du service Informations d’emplacement avec un emplacement d’intervention d’urgence (ERL), composé d’une adresse géographique et de l’adresse spécifique au sein d’un bâtiment.</span><span class="sxs-lookup"><span data-stu-id="4795c-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="4795c-108">Le champ d' **emplacement** du service des informations d’emplacement, qui correspond à un emplacement spécifique au sein d’un immeuble, a une longueur maximale de 20 caractères (espaces compris).</span><span class="sxs-lookup"><span data-stu-id="4795c-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="4795c-109">En respectant cette limite, essayez d’inclure les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="4795c-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="4795c-p103">Nom facile à comprendre qui identifie l’emplacement de l’appelant 911 pour s’assurer que les agents des services d’urgence trouvent l’emplacement spécifique rapidement lorsqu’ils arrivent à l’adresse géographique. Ce nom d’emplacement peut inclure un numéro d’immeuble, un numéro d’étage, un indicateur d’aile, un numéro de chambre, etc. Évitez les surnoms connus des seuls employés, qui peuvent induire les agents des services d’urgence en erreur.</span><span class="sxs-lookup"><span data-stu-id="4795c-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="4795c-113">Un identificateur d’emplacement qui permet à l’utilisateur de voir facilement le bon emplacement du client Lync.</span><span class="sxs-lookup"><span data-stu-id="4795c-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="4795c-114">Le client Lync concatène et affiche automatiquement les champs **emplacement** et **ville** détectés dans son en-tête.</span><span class="sxs-lookup"><span data-stu-id="4795c-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="4795c-115">Il est recommandé d’ajouter l’adresse postale du bâtiment à chaque identificateur d’emplacement (par exemple, «numéro \<\>de rue du 1er étage»).</span><span class="sxs-lookup"><span data-stu-id="4795c-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="4795c-116">Sans l’adresse postale, un identificateur d’emplacement générique tel que « 1er étage » peut s’appliquer à n’importe quel immeuble de la ville.</span><span class="sxs-lookup"><span data-stu-id="4795c-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="4795c-117">Si l’emplacement est approximatif (car déterminé par un point d’accès sans fil), vous pouvez ajouter le mot Near (par exemple, « À proximité du 1er étage 1234 »).</span><span class="sxs-lookup"><span data-stu-id="4795c-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4795c-118">Les emplacements ajoutés à la base de données d’emplacement central ne sont pas disponibles pour le client tant qu’ils n’ont pas été publiés à l’aide d’une commande Lync Server Management Shell et répliqués dans les boutiques locales du pool.</span><span class="sxs-lookup"><span data-stu-id="4795c-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="4795c-119">Pour plus d’informations, voir <A href="lync-server-2013-publish-the-location-database.md">publier la base de données de localisation à partir de Lync Server 2013</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4795c-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="4795c-120">Les sections suivantes abordent les points à prendre en considération lorsque vous remplissez et mettez à jour la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="4795c-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="4795c-121">Remplissage de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="4795c-121">Populating the Location Database</span></span>

<span data-ttu-id="4795c-122">Les questions suivantes vous permettront de déterminer comment remplir la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="4795c-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="4795c-123">**Quel processus allez-vous adopter pour remplir la base de données d’emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="4795c-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="4795c-p106">Où sont stockées les données et quelles étapes devez-vous suivre pour les convertir au format requis par la base de données d’emplacements ? Allez-vous ajouter des emplacements individuellement ou en bloc en utilisant un fichier CSV ?</span><span class="sxs-lookup"><span data-stu-id="4795c-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="4795c-126">**Disposez-vous d’une base de données tierce qui contient déjà un mappage des emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="4795c-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="4795c-127">À l’aide de l’option de service d’information d’emplacement secondaire du serveur Lync Server pour vous connecter à une base de données tierce, vous pouvez regrouper et gérer les emplacements à l’aide d’une plateforme hors connexion.</span><span class="sxs-lookup"><span data-stu-id="4795c-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="4795c-128">Outre la possibilité d’associer des emplacements à des identificateurs réseau, cette approche vous offre l’avantage d’associer des emplacements à un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="4795c-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="4795c-129">Cela signifie que le service d’information d’emplacement peut retourner plusieurs adresses à partir du service d’information d’emplacement secondaire, vers un client serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="4795c-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="4795c-130">L’utilisateur peut alors choisir l’emplacement le plus approprié.</span><span class="sxs-lookup"><span data-stu-id="4795c-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="4795c-131">Pour être intégré au service d’information d’emplacement, la base de données tierce doit suivre le schéma de requête/réponse d’emplacement du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="4795c-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="4795c-132">Pour en savoir plus,\[voir «MS\]-E911WS: Web service for E911 support Protocol Specification <http://go.microsoft.com/fwlink/p/?linkid=213819>» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="4795c-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="4795c-133">Pour plus d’informations sur le déploiement d’un service d’information d’emplacement secondaire, voir [configurer un service d’information d’emplacement secondaire dans Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4795c-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="4795c-134">Pour plus d’informations sur le remplissage de la base de données de localisation, voir [configurer la base de données de localisation dans Lync Server 2013](lync-server-2013-configure-the-location-database.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4795c-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="4795c-135">Mise à jour de la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="4795c-135">Maintaining the Location Database</span></span>

<span data-ttu-id="4795c-p109">Une fois que vous avez renseigné la base de données des emplacements, vous devez développer une stratégie pour la mettre à jour au fur et à mesure que la configuration réseau change. Les questions suivantes vous permettront de déterminer comment maintenir la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="4795c-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="4795c-138">**Comment allez-vous mettre à jour la base de données d’emplacements ?**</span><span class="sxs-lookup"><span data-stu-id="4795c-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="4795c-p110">L’ajout de points d’accès sans fil, le recâblage du bureau (qui implique des affectations de commutateur différentes) et l’extension des sous-réseaux font partie des nombreux scénarios qui requièrent la mise à jour de la base de données des emplacements. Mettrez-vous directement à jour chaque emplacement individuel ou effectuerez-vous une mise à jour en bloc de tous les emplacements en utilisant un fichier CSV ?</span><span class="sxs-lookup"><span data-stu-id="4795c-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="4795c-141">**Ferez-vous appel à une application SNMP pour associer des adresses MAC de client Lync aux identificateurs de port et de commutateur ?**</span><span class="sxs-lookup"><span data-stu-id="4795c-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="4795c-142">Si vous utilisez une application SNMP, vous devez développer un processus manuel permettant de garder les informations de châssis de commutateur et de port cohérentes entre l’application SNMP et la base de données des emplacements.</span><span class="sxs-lookup"><span data-stu-id="4795c-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="4795c-143">Si l’application SNMP renvoie une adresse IP du châssis ou un ID de port qui n’est pas inclus dans la base de données, le service d’information d’emplacement n’est pas en mesure de renvoyer un emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="4795c-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

