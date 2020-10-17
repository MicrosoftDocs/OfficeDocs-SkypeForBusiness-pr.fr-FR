---
title: 'Lync Server 2013 : liste de vérification du déploiement pour E9-1-1'
description: 'Lync Server 2013 : liste de vérification du déploiement pour E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568351"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="74a9e-103">Liste de vérification du déploiement pour E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74a9e-103">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74a9e-104">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="74a9e-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="74a9e-105">Pour effectuer une planification efficace du système Enhanced 9-1-1 (E9-1-1), vous devez tenir compte des exigences de déploiement suivantes :</span><span class="sxs-lookup"><span data-stu-id="74a9e-105">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="74a9e-106">Conditions préalables au déploiement E9-1-1</span><span class="sxs-lookup"><span data-stu-id="74a9e-106">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="74a9e-107">Étapes nécessaires au déploiement E9-1-1</span><span class="sxs-lookup"><span data-stu-id="74a9e-107">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="74a9e-108">Conditions préalables au déploiement E9-1-1</span><span class="sxs-lookup"><span data-stu-id="74a9e-108">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="74a9e-109">Avant de déployer E9-1-1, vous devez déjà avoir déployé vos serveurs internes Lync Server, notamment un magasin central de gestion, un pool frontal ou un serveur Standard Edition, un ou plusieurs serveurs de médiation ou pools de serveurs de médiation, ainsi que des clients Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74a9e-109">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="74a9e-110">Le déploiement E9-1-1 requiert également une jonction SIP vers un fournisseur de services E9-1-1 certifié ou une passerelle ELIN vers votre réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="74a9e-110">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="74a9e-111">Lync Server prend en charge l’utilisation des fournisseurs de services E9-1-1 uniquement aux États-Unis.</span><span class="sxs-lookup"><span data-stu-id="74a9e-111">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="74a9e-112">Processus de déploiement</span><span class="sxs-lookup"><span data-stu-id="74a9e-112">Deployment Process</span></span>

<span data-ttu-id="74a9e-113">Le tableau suivant présente une vue d’ensemble du processus de déploiement E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="74a9e-113">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="74a9e-114">Pour plus d’informations sur les étapes de déploiement, voir [configure enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="74a9e-114">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74a9e-115">Phase</span><span class="sxs-lookup"><span data-stu-id="74a9e-115">Phase</span></span></th>
<th><span data-ttu-id="74a9e-116">Étapes</span><span class="sxs-lookup"><span data-stu-id="74a9e-116">Steps</span></span></th>
<th><span data-ttu-id="74a9e-117">Rôles</span><span class="sxs-lookup"><span data-stu-id="74a9e-117">Roles</span></span></th>
<th><span data-ttu-id="74a9e-118">Documentation de déploiement</span><span class="sxs-lookup"><span data-stu-id="74a9e-118">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74a9e-119">Configurer les utilisations de voix, itinéraires et configurations de jonction</span><span class="sxs-lookup"><span data-stu-id="74a9e-119">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="74a9e-p103">Créez un nouvel enregistrement d’utilisation PSTN. Son nom doit être identique à celui du paramètre <strong>Utilisation PSTN</strong> utilisé dans la stratégie d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="74a9e-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-122">Créez ou affectez un itinéraire de communications vocales à l’enregistrement d’utilisation PSTN créé dans l’étape précédente, puis pointez l’attribut de passerelle vers la jonction SIP E9-1-1 ou la passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="74a9e-122">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-123">Pour un fournisseur de services E9-1-1 de jonction SIP, définissez la jonction qui traitera les appels E9-1-1 via le protocole SIP pour transmettre les données PIDF-LO à l’aide de l’applet de commande <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</span><span class="sxs-lookup"><span data-stu-id="74a9e-123">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-p104">Pour un fournisseur de services E9-1-1 de jonction SIP, vous pouvez éventuellement créer ou affecter un itinéraire PSTN local pour les appels qui ne sont pas traités par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire sera utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible. Si cette option est prise en charge par votre fournisseur de services E9-1-1, affectez une règle de configuration de jonction à la passerelle qui traduit la chaîne de numérotation 911 en numéro SDA (sélection directe à l’arrivée) du centre d’intervention en cas d’appels d’urgence (ECRC) national/régional.</span><span class="sxs-lookup"><span data-stu-id="74a9e-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="74a9e-127">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="74a9e-127">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="74a9e-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configuration d’un itinéraire des communications vocales E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a9e-129">Créer des stratégies d’emplacement et les attribuer aux utilisateurs et aux sous-réseaux</span><span class="sxs-lookup"><span data-stu-id="74a9e-129">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="74a9e-130">Vérifiez la stratégie d’emplacement globale.</span><span class="sxs-lookup"><span data-stu-id="74a9e-130">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-131">Créez une stratégie d’emplacement avec une étendue de niveau utilisateur ; ou, si l’organisation a plusieurs sites avec différentes utilisations d’urgence, créez une stratégie d’emplacement avec une étendue de niveau réseau.</span><span class="sxs-lookup"><span data-stu-id="74a9e-131">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-132">Attribuez la stratégie d’emplacement aux sites réseau.</span><span class="sxs-lookup"><span data-stu-id="74a9e-132">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-133">Ajoutez les sous-réseaux appropriés au site réseau.</span><span class="sxs-lookup"><span data-stu-id="74a9e-133">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-134">(Facultatif) Attribuez la stratégie d’emplacement aux stratégies d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="74a9e-134">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="74a9e-135">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="74a9e-135">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="74a9e-136">CSLocationAdmin (sauf pour la création de stratégies d’emplacement)</span><span class="sxs-lookup"><span data-stu-id="74a9e-136">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="74a9e-137"><a href="lync-server-2013-create-location-policies.md">Créer des stratégies d’emplacement dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-137"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="74a9e-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Ajouter une stratégie d’emplacement à un site réseau dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="74a9e-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associer des sous-réseaux à des sites réseau pour E9-1-1 dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74a9e-140">Configurer la base de données d’emplacements</span><span class="sxs-lookup"><span data-stu-id="74a9e-140">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="74a9e-141">Remplir la base de données avec une correspondance des éléments réseau avec les emplacements.</span><span class="sxs-lookup"><span data-stu-id="74a9e-141">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-142">Pour les passerelles ELIN, ajoutez numéros à la &lt; &gt; colonne CompanyName.</span><span class="sxs-lookup"><span data-stu-id="74a9e-142">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-143">Configurez la connexion au fournisseur de services E9-1-1 pour valider les adresses.</span><span class="sxs-lookup"><span data-stu-id="74a9e-143">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-144">Validez les adresses avec le fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="74a9e-144">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-145">Publier la base de données mise à jour.</span><span class="sxs-lookup"><span data-stu-id="74a9e-145">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-146">Pour les passerelles ELIN, téléchargez les numéros d’identification de l’emplacement en cas d’urgence vers la base de données ALI (Automatic Location Identification) de votre opérateur RTC.</span><span class="sxs-lookup"><span data-stu-id="74a9e-146">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="74a9e-147">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="74a9e-147">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="74a9e-148">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="74a9e-148">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="74a9e-149"><a href="lync-server-2013-configure-the-location-database.md">Configuration de la base de données d’emplacements dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-149"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74a9e-150">Configurer les fonctionnalités avancées (facultatif)</span><span class="sxs-lookup"><span data-stu-id="74a9e-150">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="74a9e-151">Configurez l’URL pour l’application SNMP.</span><span class="sxs-lookup"><span data-stu-id="74a9e-151">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="74a9e-152">Configurez l’URL pour l’emplacement du service d’informations d’emplacement secondaire.</span><span class="sxs-lookup"><span data-stu-id="74a9e-152">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="74a9e-153">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="74a9e-153">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="74a9e-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configurer une application SNMP dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="74a9e-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurer un service d’informations d’emplacement secondaire dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="74a9e-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

