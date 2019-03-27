---
title: Configuration des plages de ports et une stratégie de qualité de Service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cet article explique comment configurer les plages de ports pour vos clients et la configuration des stratégies de qualité de Service dans Skype pour Business Server pour les clients s’exécutant sur Windows 10.
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881520"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="cd42d-103">Configuration des plages de ports et d’une stratégie de qualité de Service pour vos clients dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="cd42d-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="cd42d-104">Cet article explique comment configurer les plages de ports pour vos clients et la configuration des stratégies de qualité de Service dans Skype pour Business Server pour les clients s’exécutant sur Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cd42d-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="cd42d-105">Configurer les plages de ports</span><span class="sxs-lookup"><span data-stu-id="cd42d-105">Configure port ranges</span></span>

<span data-ttu-id="cd42d-106">Par défaut, le Skype pour les applications client d’entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsque impliquées dans une session de communication ; Il s’agit, car les plages de ports ne sont pas automatiquement activés pour les clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="cd42d-107">Pour pouvoir utiliser la qualité de Service, toutefois, vous devrez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et le transfert de fichiers) à une série de plages de ports uniques.</span><span class="sxs-lookup"><span data-stu-id="cd42d-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="cd42d-108">Cette opération peut être effectuée à l’aide de l’applet de commande Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cd42d-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="cd42d-109">Les utilisateurs finaux ne peuvent pas apporter ces modifications eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="cd42d-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="cd42d-110">Modifications de port ne peuvent être effectuées par les administrateurs à l’aide de l’applet de commande Set-CsConferencingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="cd42d-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="cd42d-111">Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de la Skype pour Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="cd42d-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="cd42d-112">En supposant que vous n’avez apporté des modifications à vos paramètres de conférence dans la mesure où vous avez installé Skype pour Business Server, vous devriez obtenir des informations comprenant ces valeurs de propriété :</span><span class="sxs-lookup"><span data-stu-id="cd42d-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="cd42d-113">Si vous examinez attentivement la sortie précédente, vous verrez deux choses d’importance.</span><span class="sxs-lookup"><span data-stu-id="cd42d-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="cd42d-114">Tout d’abord, la propriété de paramètres ClientMediaPortRangeEnabled est définie sur False :</span><span class="sxs-lookup"><span data-stu-id="cd42d-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="cd42d-115">Ceci est important car, lorsque cette propriété est définie sur False, Skype pour les clients professionnels utilisent n’importe quel port disponible entre les ports 1024 et 65535 lorsque impliquées dans une session de communication ; Cela est vrai indépendamment des autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="cd42d-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="cd42d-116">Si vous souhaitez limiter l’utilisation à un ensemble de ports spécifié (et il s’agit d’un élément que vous ne souhaitez pas faire si vous envisagez l’implémentation de qualité de Service), vous devez tout d’abord activer plages de ports multimédia client.</span><span class="sxs-lookup"><span data-stu-id="cd42d-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="cd42d-117">Qui peut être effectuée à l’aide de la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="cd42d-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="cd42d-118">La commande précédente Active les plages de ports multimédia client pour la collection globale des paramètres de configuration de conférence ; Toutefois, ces paramètres peuvent également s’appliquer à l’étendue site et/ou l’étendue service (pour le service de serveur de conférence).</span><span class="sxs-lookup"><span data-stu-id="cd42d-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="cd42d-119">Pour activer le média client port plages pour un site spécifique ou un serveur, spécifiez l’identité du site ou du serveur lors de l’appel de Set-CsConferencingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="cd42d-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="cd42d-120">Vous pouvez également utiliser cette commande pour activer simultanément des plages de ports pour tous vos paramètres de configuration de conférence :</span><span class="sxs-lookup"><span data-stu-id="cd42d-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="cd42d-121">La deuxième chose importante à remarquer est que la sortie d’exemple montre que, par défaut, les ports multimédias plages définies pour chaque type de trafic réseau est identiques :</span><span class="sxs-lookup"><span data-stu-id="cd42d-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="cd42d-122">Pour mettre en œuvre QoS, chacune de ces plages de ports vous devrez être uniques.</span><span class="sxs-lookup"><span data-stu-id="cd42d-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="cd42d-123">Par exemple, vous pouvez configurer les plages de ports comme suit :</span><span class="sxs-lookup"><span data-stu-id="cd42d-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd42d-124">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="cd42d-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="cd42d-125">Port de début</span><span class="sxs-lookup"><span data-stu-id="cd42d-125">Port Start</span></span></th>
<th><span data-ttu-id="cd42d-126">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="cd42d-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd42d-127">Audio</span><span class="sxs-lookup"><span data-stu-id="cd42d-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="cd42d-128">50020</span><span class="sxs-lookup"><span data-stu-id="cd42d-128">50020</span></span></p></td>
<td><p><span data-ttu-id="cd42d-129">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd42d-130">Vidéo</span><span class="sxs-lookup"><span data-stu-id="cd42d-130">Video</span></span></p></td>
<td><p><span data-ttu-id="cd42d-131">58000</span><span class="sxs-lookup"><span data-stu-id="cd42d-131">58000</span></span></p></td>
<td><p><span data-ttu-id="cd42d-132">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd42d-133">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="cd42d-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="cd42d-134">42000</span><span class="sxs-lookup"><span data-stu-id="cd42d-134">42000</span></span></p></td>
<td><p><span data-ttu-id="cd42d-135">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd42d-136">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="cd42d-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="cd42d-137">42020</span><span class="sxs-lookup"><span data-stu-id="cd42d-137">42020</span></span></p></td>
<td><p><span data-ttu-id="cd42d-138">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="cd42d-139">Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurée pour vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="cd42d-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="cd42d-140">Par exemple, sur les serveurs, partage d’application a été configuré pour utiliser des ports 40803 via et 49 151 ; sur les ordinateurs clients, partage d’application est configuré pour utiliser des ports 42000 via 42019.</span><span class="sxs-lookup"><span data-stu-id="cd42d-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="cd42d-141">Trop, cela principalement pour faciliter l’administration de QoS : ports client n’ont pas représenter un sous-ensemble des ports utilisés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="cd42d-142">(Par exemple, sur les ordinateurs clients vous pouvez configurer partage d’application pour utiliser, par exemple, ports 10000 par le biais de 10019.) Toutefois, il est recommandé que vous apportez à votre client de plages de ports un sous-ensemble des plages de ports votre serveur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="cd42d-143">En outre, vous avez sans doute remarqué que 8348 ports ont été attribuées au partage d’application sur les serveurs, mais que 20 ports ont été attribuées au partage d’application sur les clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="cd42d-144">Cela trop, est recommandé, mais n’est pas une règle absolue.</span><span class="sxs-lookup"><span data-stu-id="cd42d-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="cd42d-145">En règle générale, vous pouvez considérer chaque port disponible pour représenter une session de communication unique : Si vous avez 100 ports disponibles dans une plage de ports, ce qui signifie que l’ordinateur en question peut participer, au maximum 100 sessions de communication à tout moment donné.</span><span class="sxs-lookup"><span data-stu-id="cd42d-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="cd42d-146">Étant donné que les serveurs seront probablement prendre part à des conversations plus nombreux que les clients, c’est significatif pour ouvrir des ports plus nombreux sur les serveurs que sur les clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="cd42d-147">Paramètre côté 20 ports partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur le périphérique spécifié et tous en même temps.</span><span class="sxs-lookup"><span data-stu-id="cd42d-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="cd42d-148">Qui doit s’avérer suffisant pour la plupart de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="cd42d-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="cd42d-149">Pour affecter les plages de ports précédentes à votre collection globale des paramètres de configuration de conférence, vous pouvez utiliser le suivant Skype de commande Business Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="cd42d-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="cd42d-150">Ou bien, utilisez cette commande pour affecter ces mêmes plages de ports pour toutes les conférences de vos paramètres de configuration :</span><span class="sxs-lookup"><span data-stu-id="cd42d-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="cd42d-151">Des utilisateurs individuels doivent se déconnecter de Skype pour les entreprises et se reconnecter avant que ces modifications puissent prendre effet.</span><span class="sxs-lookup"><span data-stu-id="cd42d-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="cd42d-152">Vous pouvez également activer les plages de ports multimédia client et ensuite affecter ces plages de ports, à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="cd42d-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="cd42d-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="cd42d-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="cd42d-154">Configuration des stratégies de qualité de Service de clients s’exécutant sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="cd42d-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="cd42d-155">Outre la spécification des plages de ports pour une utilisation par votre Skype pour les clients d’entreprise, vous devez également créer des stratégies de qualité de Service distincts qui seront appliqués aux ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="cd42d-156">(Les stratégies de qualité de Service créées pour les serveurs de conférence, d’Application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’applique uniquement aux ordinateurs qui exécutent le Skype pour client d’entreprise et 10 Windows.</span><span class="sxs-lookup"><span data-stu-id="cd42d-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="cd42d-157">L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :</span><span class="sxs-lookup"><span data-stu-id="cd42d-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd42d-158">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="cd42d-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="cd42d-159">Port de début</span><span class="sxs-lookup"><span data-stu-id="cd42d-159">Port Start</span></span></th>
<th><span data-ttu-id="cd42d-160">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="cd42d-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd42d-161">Audio</span><span class="sxs-lookup"><span data-stu-id="cd42d-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="cd42d-162">50020</span><span class="sxs-lookup"><span data-stu-id="cd42d-162">50020</span></span></p></td>
<td><p><span data-ttu-id="cd42d-163">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd42d-164">Vidéo</span><span class="sxs-lookup"><span data-stu-id="cd42d-164">Video</span></span></p></td>
<td><p><span data-ttu-id="cd42d-165">58000</span><span class="sxs-lookup"><span data-stu-id="cd42d-165">58000</span></span></p></td>
<td><p><span data-ttu-id="cd42d-166">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd42d-167">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="cd42d-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="cd42d-168">42000</span><span class="sxs-lookup"><span data-stu-id="cd42d-168">42000</span></span></p></td>
<td><p><span data-ttu-id="cd42d-169">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd42d-170">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="cd42d-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="cd42d-171">42020</span><span class="sxs-lookup"><span data-stu-id="cd42d-171">42020</span></span></p></td>
<td><p><span data-ttu-id="cd42d-172">20</span><span class="sxs-lookup"><span data-stu-id="cd42d-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="cd42d-173">Pour créer une stratégie audio de qualité de Service pour les ordinateurs Windows 10, ouvrez une session un ordinateur où la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="cd42d-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="cd42d-174">Ouvrez Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**), puis effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="cd42d-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="cd42d-175">Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="cd42d-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="cd42d-176">Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée Clients, la nouvelle stratégie doit être créée en l’unité d’organisation du Client.</span><span class="sxs-lookup"><span data-stu-id="cd42d-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="cd42d-177">Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="cd42d-178">Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="cd42d-179">Avec le bouton droit de la stratégie créée, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="cd42d-180">Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="cd42d-181">Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie dans la zone **nom** .</span><span class="sxs-lookup"><span data-stu-id="cd42d-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="cd42d-182">Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="cd42d-183">Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="cd42d-184">Dans la page suivante, vérifiez que **toutes les applications** est sélectionné, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-184">On the next page, make sure that **All applications** is selected, and then click **Next**.</span></span> <span data-ttu-id="cd42d-185">Ce paramètre indique le réseau pour rechercher tous les paquets avec un marquage DSCP des paquets pas seulement 46, créé par une application spécifique.</span><span class="sxs-lookup"><span data-stu-id="cd42d-185">This setting instructs the network to look for all packets with a DSCP marking of 46, not just packets created by a specific application.</span></span>

8.  <span data-ttu-id="cd42d-186">Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="cd42d-187">Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.</span><span class="sxs-lookup"><span data-stu-id="cd42d-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="cd42d-188">Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** .</span><span class="sxs-lookup"><span data-stu-id="cd42d-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="cd42d-189">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau plus couramment utilisés par Skype pour Business Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="cd42d-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="cd42d-190">Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="cd42d-191">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="cd42d-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="cd42d-192">Par exemple, si vous réservé ports 50020 par le biais des ports 50039 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="cd42d-193">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-193">Click **Finish**.</span></span>

<span data-ttu-id="cd42d-194">Après avoir créé la stratégie QoS pour l’audio, vous devez ensuite créer une deuxième stratégie pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="cd42d-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="cd42d-195">Pour créer une stratégie pour la vidéo, suivez la même procédure de base que vous avez suivi lors de la création de la stratégie audio, effectuant les substitutions :</span><span class="sxs-lookup"><span data-stu-id="cd42d-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="cd42d-196">Utilisez un nom de stratégie différent (et unique).</span><span class="sxs-lookup"><span data-stu-id="cd42d-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="cd42d-197">Définissez la valeur DSCP **34** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="cd42d-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="cd42d-198">(Comme mentionné précédemment, il est inutile d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP autre que celui utilisé pour l’audio).</span><span class="sxs-lookup"><span data-stu-id="cd42d-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="cd42d-199">Utiliser la plage de ports précédemment configuré pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="cd42d-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="cd42d-200">Par exemple, si vous avez réservé ports 58000 via 58019 pour la vidéo, définissez la plage de ports à ceci : **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="cd42d-201">Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, effectuez les remplacements suivants :</span><span class="sxs-lookup"><span data-stu-id="cd42d-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="cd42d-202">Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour le partage d’Application Business Server**).</span><span class="sxs-lookup"><span data-stu-id="cd42d-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="cd42d-203">Définissez la valeur DSCP à **24** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="cd42d-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="cd42d-204">(Là encore, cette valeur ne doit pas être 24 ; il doit simplement être différent dans les valeurs DSCP utilisés pour l’audio et vidéo).</span><span class="sxs-lookup"><span data-stu-id="cd42d-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="cd42d-205">Utiliser la plage de ports précédemment configuré pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="cd42d-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="cd42d-206">Par exemple, si vous avez réservé ports 42000 par le biais de 42019 pour le partage d’application, définissez la plage de ports à ceci : **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="cd42d-207">Pour une stratégie de transfert de fichier :</span><span class="sxs-lookup"><span data-stu-id="cd42d-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="cd42d-208">Utilisez un nom différent (et unique) de la stratégie (par exemple, **Skype pour les transferts de fichiers Business Server**).</span><span class="sxs-lookup"><span data-stu-id="cd42d-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="cd42d-209">Définissez la valeur DSCP **14**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="cd42d-210">(Là encore, cette valeur ne doit pas être 14 ; il doit simplement être un code DSCP unique).</span><span class="sxs-lookup"><span data-stu-id="cd42d-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="cd42d-211">Utiliser la plage de ports précédemment configuré pour l’application.</span><span class="sxs-lookup"><span data-stu-id="cd42d-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="cd42d-212">Par exemple, si vous avez réservé ports 42020 par le biais de 42039 pour le partage d’application, définissez la plage de ports à ceci : **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="cd42d-213">Les nouvelles stratégies que vous avez créé ne prendra pas effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="cd42d-214">Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doivent être actualisées :</span><span class="sxs-lookup"><span data-stu-id="cd42d-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpudate.exe /force

<span data-ttu-id="cd42d-215">Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande s’exécutant sous les informations d’identification d’administrateur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="cd42d-216">Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez sur **invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="cd42d-217">N’oubliez pas que ces stratégies doivent être ciblés vers vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="cd42d-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="cd42d-218">Ils ne doivent pas être appliquées à des serveurs exécutant Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="cd42d-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="cd42d-219">Pour garantir que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="cd42d-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="cd42d-220">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="cd42d-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="cd42d-221">Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="cd42d-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="cd42d-222">Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="cd42d-223">Cliquez sur **TCP/IP**, pointez sur **Nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="cd42d-224">Une fois la nouvelle clé de Registre est créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="cd42d-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="cd42d-225">Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="cd42d-226">Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="cd42d-227">Double-cliquez sur **ne pas utiliser l’authentification réseau**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="cd42d-228">Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="cd42d-229">Fermez l’Éditeur du Registre et eboot votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="cd42d-230">Configurer la qualité de Service sur des ordinateurs ayant plusieurs cartes réseau</span><span class="sxs-lookup"><span data-stu-id="cd42d-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="cd42d-231">Si vous disposez d’un ordinateur qui possède plusieurs cartes réseau, vous pouvez exécuter occasionnellement problèmes où les valeurs DSCP sont affichés sous forme de 0 x 00 plutôt que la valeur configurée.</span><span class="sxs-lookup"><span data-stu-id="cd42d-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="cd42d-232">Cela se produit généralement sur les ordinateurs où un ou plusieurs des cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé).</span><span class="sxs-lookup"><span data-stu-id="cd42d-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="cd42d-233">Dans ce cas qui, valeurs DSCP seront balisés pour les cartes réseau qui peuvent accéder au domaine, mais ne seront pas balisés pour les cartes qui ne peuvent pas accéder au domaine.</span><span class="sxs-lookup"><span data-stu-id="cd42d-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="cd42d-234">Si vous souhaitez les valeurs DSCP balise pour toutes les cartes réseau sur un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="cd42d-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="cd42d-235">Qui peuvent être effectuées en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="cd42d-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="cd42d-236">Cliquez sur \*\*Démarrer \*\*, puis sur \*\*Exécuter \*\*.</span><span class="sxs-lookup"><span data-stu-id="cd42d-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="cd42d-237">Dans la boîte de dialogue **exécuter** , tapez **regedit**, puis appuyez sur ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="cd42d-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="cd42d-238">Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_ordinateur**, développez **système**, développez **CurrentControlSet**, développez **services**et **puis TCPIP**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="cd42d-239">Si vous ne voyez pas d’une clé de Registre intitulée **QoS** puis **Tcpip**d’avec le bouton droit, pointez sur **Nouveau**, puis cliquez sur **clé**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="cd42d-240">Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur ENTRÉE pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="cd42d-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="cd42d-241">Avec le bouton droit **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="cd42d-242">Une fois la nouvelle valeur de Registre est créée, tapez **n’utilisez pas l’authentification réseau**, puis appuyez sur ENTRÉE pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="cd42d-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="cd42d-243">Double-cliquez sur **ne pas utiliser l’authentification réseau**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="cd42d-244">Dans la boîte de dialogue **Modification de la chaîne** , tapez **1** dans la zone **valeur** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="cd42d-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="cd42d-245">Après la création et la configuration de la nouvelle valeur de Registre, vous devrez redémarrer votre ordinateur pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="cd42d-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd42d-246">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cd42d-246">See also</span></span>

[<span data-ttu-id="cd42d-247">Créer un objet de stratégie de groupe dans Windows 10</span><span class="sxs-lookup"><span data-stu-id="cd42d-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
