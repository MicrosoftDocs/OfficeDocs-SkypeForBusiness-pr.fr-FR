---
title: 'Lync Server 2013 : configuration des plages de ports pour vos clients Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Microsoft Lync clients
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77366884d83d29c39c1f19fc710030ea8457dd7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535011"
---
# <a name="configuring-port-ranges-for-your-microsoft-lync-clients-in-lync-server-2013"></a><span data-ttu-id="30be9-102">Configuration des plages de ports pour vos clients Microsoft Lync dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30be9-102">Configuring port ranges for your Microsoft Lync clients in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30be9-103">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="30be9-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="30be9-104">Par défaut, les applications clientes Lync peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’une session de communication est impliquée ; Cela est dû au fait que les plages de ports spécifiques ne sont pas automatiquement activées pour les clients.</span><span class="sxs-lookup"><span data-stu-id="30be9-104">By default, Lync client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="30be9-105">Pour utiliser la qualité de service, toutefois, vous devrez réaffecter les différents types de trafic (audio, vidéo, multimédia, partage d’application et transfert de fichiers) à une série de plages de ports uniques.</span><span class="sxs-lookup"><span data-stu-id="30be9-105">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="30be9-106">Cette opération peut être réalisée à l’aide de la cmdlet Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="30be9-106">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30be9-107">Les utilisateurs finaux ne peuvent pas procéder à ces modifications.</span><span class="sxs-lookup"><span data-stu-id="30be9-107">End users cannot make these changes themselves.</span></span> <span data-ttu-id="30be9-108">Les modifications de port peuvent être effectuées uniquement par les administrateurs à l’aide de l’applet de commande Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="30be9-108">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>



</div>

<span data-ttu-id="30be9-109">Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Microsoft Lync Server 2013 Management Shell :</span><span class="sxs-lookup"><span data-stu-id="30be9-109">You can determine which port ranges are currently used for communication sessions by running the following command from within the Microsoft Lync Server 2013 Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="30be9-110">En supposant que vous n’avez apporté aucune modification à vos paramètres de conférence depuis que vous avez installé Lync Server 2013, vous devez obtenir des informations qui incluent les valeurs de ces propriétés :</span><span class="sxs-lookup"><span data-stu-id="30be9-110">Assuming that you have not made any changes to your conferencing settings since you installed Lync Server 2013, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="30be9-111">Si vous examinez attentivement la sortie précédente, vous verrez deux éléments d’importance.</span><span class="sxs-lookup"><span data-stu-id="30be9-111">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="30be9-112">Tout d’abord, la propriété paramètres clientmediaportrangeenabled est définie sur false :</span><span class="sxs-lookup"><span data-stu-id="30be9-112">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="30be9-113">Cela est important car, lorsque cette propriété est définie sur false, les clients Lync utiliseront n’importe quel port disponible entre les ports 1024 et 65535 lorsqu’ils sont impliqués dans une session de communication. Cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="30be9-113">That's important because, when this property is set to False, Lync clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="30be9-114">Si vous souhaitez restreindre l’utilisation à un ensemble spécifique de ports (ce que vous devez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de ports du client multimédia.</span><span class="sxs-lookup"><span data-stu-id="30be9-114">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service) then you must first enable client media port ranges.</span></span> <span data-ttu-id="30be9-115">Cela peut être réalisé à l’aide de la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="30be9-115">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="30be9-116">La commande précédente permet d’activer des plages de ports multimédias client pour la collection globale des paramètres de configuration de conférence ; Toutefois, ces paramètres peuvent également être appliqués à l’étendue du site et/ou à l’étendue du service (pour le service de serveur de conférence uniquement).</span><span class="sxs-lookup"><span data-stu-id="30be9-116">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="30be9-117">Pour activer des plages de ports multimédias client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="30be9-117">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="30be9-118">Vous pouvez également utiliser cette commande pour activer simultanément les plages de ports pour tous vos paramètres de configuration de conférence :</span><span class="sxs-lookup"><span data-stu-id="30be9-118">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="30be9-119">La deuxième chose d’importance que vous remarquerez est que le résultat de l’exemple indique que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :</span><span class="sxs-lookup"><span data-stu-id="30be9-119">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="30be9-120">Pour mettre en œuvre la qualité de service, chacune de ces plages de ports doit être unique.</span><span class="sxs-lookup"><span data-stu-id="30be9-120">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="30be9-121">Par exemple, vous pouvez configurer les plages de ports comme suit :</span><span class="sxs-lookup"><span data-stu-id="30be9-121">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30be9-122">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="30be9-122">Client Traffic Type</span></span></th>
<th><span data-ttu-id="30be9-123">Démarrage du port</span><span class="sxs-lookup"><span data-stu-id="30be9-123">Port Start</span></span></th>
<th><span data-ttu-id="30be9-124">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="30be9-124">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30be9-125">Audio</span><span class="sxs-lookup"><span data-stu-id="30be9-125">Audio</span></span></p></td>
<td><p><span data-ttu-id="30be9-126">50020</span><span class="sxs-lookup"><span data-stu-id="30be9-126">50020</span></span></p></td>
<td><p><span data-ttu-id="30be9-127">vingtaine</span><span class="sxs-lookup"><span data-stu-id="30be9-127">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30be9-128">Vidéo</span><span class="sxs-lookup"><span data-stu-id="30be9-128">Video</span></span></p></td>
<td><p><span data-ttu-id="30be9-129">58000</span><span class="sxs-lookup"><span data-stu-id="30be9-129">58000</span></span></p></td>
<td><p><span data-ttu-id="30be9-130">vingtaine</span><span class="sxs-lookup"><span data-stu-id="30be9-130">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30be9-131">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="30be9-131">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="30be9-132">42000</span><span class="sxs-lookup"><span data-stu-id="30be9-132">42000</span></span></p></td>
<td><p><span data-ttu-id="30be9-133">vingtaine</span><span class="sxs-lookup"><span data-stu-id="30be9-133">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30be9-134">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="30be9-134">File transfer</span></span></p></td>
<td><p><span data-ttu-id="30be9-135">42020</span><span class="sxs-lookup"><span data-stu-id="30be9-135">42020</span></span></p></td>
<td><p><span data-ttu-id="30be9-136">vingtaine</span><span class="sxs-lookup"><span data-stu-id="30be9-136">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="30be9-137">Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurées pour vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="30be9-137">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="30be9-138">Par exemple, sur les serveurs, le partage d’application a été configuré pour utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré pour utiliser les ports 42000 à 42019.</span><span class="sxs-lookup"><span data-stu-id="30be9-138">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="30be9-139">Cela est également essentiel pour faciliter l’administration de QoS : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="30be9-139">This, too is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="30be9-140">(Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application à utiliser, par exemple, les ports 10000 à 10019.) Toutefois, il est recommandé de faire en sorte que les plages de ports clients soient un sous-ensemble des plages de ports de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="30be9-140">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="30be9-141">De plus, vous avez peut-être remarqué que les ports 8348 ont été mis de côté pour le partage d’application sur les serveurs, mais seulement 20 ports ont été mis de côté pour le partage d’application sur les clients.</span><span class="sxs-lookup"><span data-stu-id="30be9-141">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="30be9-142">Cela est également recommandé, mais il ne s’agit pas d’une règle matérielle et rapide.</span><span class="sxs-lookup"><span data-stu-id="30be9-142">This, too is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="30be9-143">En règle générale, vous pouvez considérer chaque port disponible pour qu’il représente une seule session de communication : Si vous disposez de 100 ports disponibles dans une plage de ports, cela signifie que l’ordinateur en question peut, au plus, se voir attribuer 100 sessions de communication à tout moment.</span><span class="sxs-lookup"><span data-stu-id="30be9-143">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="30be9-144">Étant donné que les serveurs feront probablement partie d’autres conversations que les clients, il est logique d’ouvrir beaucoup plus de ports sur les serveurs que sur les clients.</span><span class="sxs-lookup"><span data-stu-id="30be9-144">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="30be9-145">Le fait de ne pas mettre en place 20 ports pour le partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, tout en même temps.</span><span class="sxs-lookup"><span data-stu-id="30be9-145">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="30be9-146">Cela doit s’avérer suffisant pour la grande majorité de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="30be9-146">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="30be9-147">Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Lync Server Management Shell suivante :</span><span class="sxs-lookup"><span data-stu-id="30be9-147">To assign the preceding port ranges to your global collection of conferencing configuration settings you can use the following Lync Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="30be9-148">Vous pouvez utiliser cette commande pour affecter ces mêmes plages de ports à tous vos paramètres de configuration de conférence :</span><span class="sxs-lookup"><span data-stu-id="30be9-148">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="30be9-149">Les utilisateurs individuels doivent se déconnecter de Lync, puis se reconnecter pour que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="30be9-149">Individual users must log off from Lync and then log back on before these changes will actually take effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30be9-150">Vous pouvez également activer les plages de ports multimédias client, puis affecter ces plages de ports à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="30be9-150">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="30be9-151">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="30be9-151">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>



</div>

</div>

<span> </span>

</div>

</div>

</div>

