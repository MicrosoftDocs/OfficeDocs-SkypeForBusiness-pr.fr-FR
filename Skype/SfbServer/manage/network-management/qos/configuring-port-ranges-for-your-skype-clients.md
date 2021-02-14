---
title: Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Cet article explique comment configurer des plages de ports pour vos clients et des stratégies de qualité de service dans Skype Entreprise Server pour les clients exécutant Windows 10.
ms.openlocfilehash: b2961193bef799742ac3b79a4f421a7aa50c5a03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814200"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a><span data-ttu-id="a9519-103">Configuration des plages de ports et d’une stratégie de qualité de service pour vos clients dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a9519-103">Configuring port ranges and a Quality of Service policy for your clients in Skype for Business Server</span></span>

<span data-ttu-id="a9519-104">Cet article explique comment configurer des plages de ports pour vos clients et des stratégies de qualité de service dans Skype Entreprise Server pour les clients exécutant Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a9519-104">This article describes how to configure port ranges for your clients and configuring Quality of Service policies in Skype for Business Server for clients running on Windows 10.</span></span>

## <a name="configure-port-ranges"></a><span data-ttu-id="a9519-105">Configurer des plages de ports</span><span class="sxs-lookup"><span data-stu-id="a9519-105">Configure port ranges</span></span>

<span data-ttu-id="a9519-106">Par défaut, les applications clientes Skype Entreprise peuvent utiliser n’importe quel port entre les ports 1024 et 65535 lorsqu’elles sont impliquées dans une session de communication . Cela est dû au fait que des plages de ports spécifiques ne sont pas automatiquement activées pour les clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-106">By default, Skype for Business client applications can use any port between ports 1024 and 65535 when involved in a communication session; this is because specific port ranges are not automatically enabled for clients.</span></span> <span data-ttu-id="a9519-107">Toutefois, pour utiliser la qualité de service, vous devez réaffecter les différents types de trafic (audio, vidéo, média, partage d’application et transfert de fichiers) à une série de plages de ports uniques.</span><span class="sxs-lookup"><span data-stu-id="a9519-107">In order to use Quality of Service, however, you will need to reassign the various traffic types (audio, video, media, application sharing, and file transfer) to a series of unique port ranges.</span></span> <span data-ttu-id="a9519-108">Pour ce faire, vous pouvez utiliser l'Set-CsConferencingConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9519-108">This can be done by using the Set-CsConferencingConfiguration cmdlet.</span></span>

> [!NOTE]  
> <span data-ttu-id="a9519-109">Les utilisateurs finaux ne peuvent pas effectuer ces modifications eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="a9519-109">End users cannot make these changes themselves.</span></span> <span data-ttu-id="a9519-110">Les modifications de port peuvent uniquement être apportées par les administrateurs à l’aide Set-CsConferencingConfiguration cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9519-110">Port changes can only be made by administrators using the Set-CsConferencingConfiguration cmdlet.</span></span>


<span data-ttu-id="a9519-111">Vous pouvez déterminer les plages de ports actuellement utilisées pour les sessions de communication en exécutant la commande suivante à partir de Skype Entreprise Server Management Shell :</span><span class="sxs-lookup"><span data-stu-id="a9519-111">You can determine which port ranges are currently used for communication sessions by running the following command from within the Skype for Business Server Management Shell:</span></span>

    Get-CsConferencingConfiguration

<span data-ttu-id="a9519-112">En supposant que vous n’avez pas apporté de modifications à vos paramètres de conférence depuis l’installation de Skype Entreprise Server, vous devez obtenir des informations qui incluent ces valeurs de propriété :</span><span class="sxs-lookup"><span data-stu-id="a9519-112">Assuming that you have not made any changes to your conferencing settings since you installed Skype for Business Server, you should get back information that includes these property values:</span></span>

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

<span data-ttu-id="a9519-113">Si vous regardez attentivement la sortie précédente, vous verrez deux choses d’importance.</span><span class="sxs-lookup"><span data-stu-id="a9519-113">If you look closely at the preceding output, you'll see two things of importance.</span></span> <span data-ttu-id="a9519-114">Tout d’abord, la propriété ClientMediaPortRangeEnabled est définie sur False :</span><span class="sxs-lookup"><span data-stu-id="a9519-114">First, the ClientMediaPortRangeEnabled property is set to False:</span></span>

    ClientMediaPortRangeEnabled : False

<span data-ttu-id="a9519-115">Ceci est important car, lorsque cette propriété est définie sur False, les clients Skype Entreprise utilisent n’importe quel port disponible entre les ports 1024 et 65535 lorsqu’ils sont impliqués dans une session de communication . cela s’applique quels que soient les autres paramètres de port (par exemple, ClientMediaPort ou ClientVideoPort).</span><span class="sxs-lookup"><span data-stu-id="a9519-115">That's important because, when this property is set to False, Skype for Business clients will use any available port between ports 1024 and 65535 when involved in a communication session; this is true regardless of any other port settings (for example, ClientMediaPort or ClientVideoPort).</span></span> <span data-ttu-id="a9519-116">Si vous souhaitez limiter l’utilisation à un ensemble spécifique de ports (et c’est ce que vous souhaitez faire si vous envisagez d’implémenter la qualité de service), vous devez d’abord activer les plages de ports de média client.</span><span class="sxs-lookup"><span data-stu-id="a9519-116">If you want to restrict usage to a specified set of ports (and this is something you do want to do if you plan on implementing Quality of Service), then you must first enable client media port ranges.</span></span> <span data-ttu-id="a9519-117">Pour ce faire, utilisez la commande Windows PowerShell suivante :</span><span class="sxs-lookup"><span data-stu-id="a9519-117">That can be done using the following Windows PowerShell command:</span></span>

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a9519-118">La commande précédente active les plages de ports de média client pour la collection globale de paramètres de configuration de conférence ; toutefois, ces paramètres peuvent également être appliqués à l’étendue Site et/ou Service (pour le service Serveur de conférence uniquement).</span><span class="sxs-lookup"><span data-stu-id="a9519-118">The preceding command enables client media port ranges for the global collection of conferencing configuration settings; however, these settings can also be applied to the site scope and/or the service scope (for the Conferencing Server service only).</span></span> <span data-ttu-id="a9519-119">Pour activer les plages de ports multimédias client pour un site ou un serveur spécifique, spécifiez l’identité de ce site ou serveur lors de l’appel de Set-CsConferencingConfiguration :</span><span class="sxs-lookup"><span data-stu-id="a9519-119">To enable client media port ranges for a specific site or server, specify the Identity of that site or server when calling Set-CsConferencingConfiguration:</span></span>

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a9519-120">Vous pouvez également utiliser cette commande pour activer simultanément des plages de ports pour tous vos paramètres de configuration de conférence :</span><span class="sxs-lookup"><span data-stu-id="a9519-120">Alternatively, you can use this command to simultaneously enable port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

<span data-ttu-id="a9519-121">La deuxième chose importante que vous remarquerez est que l’exemple de sortie montre que, par défaut, les plages de ports multimédias définies pour chaque type de trafic réseau sont identiques :</span><span class="sxs-lookup"><span data-stu-id="a9519-121">The second thing of importance you will notice is that the sample output shows that, by default, the media port ranges set for each type of network traffic are identical:</span></span>

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

<span data-ttu-id="a9519-122">Pour implémenter QoS, chacune de ces plages de ports doit être unique.</span><span class="sxs-lookup"><span data-stu-id="a9519-122">In order to implement QoS, each of these port ranges will need to be unique.</span></span> <span data-ttu-id="a9519-123">Par exemple, vous pouvez configurer les plages de ports comme ceci :</span><span class="sxs-lookup"><span data-stu-id="a9519-123">For example, you might configure the port ranges like this:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9519-124">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="a9519-124">Client Traffic Type</span></span></th>
<th><span data-ttu-id="a9519-125">Début du port</span><span class="sxs-lookup"><span data-stu-id="a9519-125">Port Start</span></span></th>
<th><span data-ttu-id="a9519-126">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="a9519-126">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9519-127">Audio</span><span class="sxs-lookup"><span data-stu-id="a9519-127">Audio</span></span></p></td>
<td><p><span data-ttu-id="a9519-128">50020</span><span class="sxs-lookup"><span data-stu-id="a9519-128">50020</span></span></p></td>
<td><p><span data-ttu-id="a9519-129">20</span><span class="sxs-lookup"><span data-stu-id="a9519-129">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9519-130">Vidéo</span><span class="sxs-lookup"><span data-stu-id="a9519-130">Video</span></span></p></td>
<td><p><span data-ttu-id="a9519-131">58000</span><span class="sxs-lookup"><span data-stu-id="a9519-131">58000</span></span></p></td>
<td><p><span data-ttu-id="a9519-132">20</span><span class="sxs-lookup"><span data-stu-id="a9519-132">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9519-133">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="a9519-133">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a9519-134">42000</span><span class="sxs-lookup"><span data-stu-id="a9519-134">42000</span></span></p></td>
<td><p><span data-ttu-id="a9519-135">20</span><span class="sxs-lookup"><span data-stu-id="a9519-135">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9519-136">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="a9519-136">File transfer</span></span></p></td>
<td><p><span data-ttu-id="a9519-137">42020</span><span class="sxs-lookup"><span data-stu-id="a9519-137">42020</span></span></p></td>
<td><p><span data-ttu-id="a9519-138">20</span><span class="sxs-lookup"><span data-stu-id="a9519-138">20</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a9519-139">Dans le tableau précédent, les plages de ports client représentent un sous-ensemble des plages de ports configurées pour vos serveurs.</span><span class="sxs-lookup"><span data-stu-id="a9519-139">In the preceding table, client port ranges represent a subset of the port ranges configured for your servers.</span></span> <span data-ttu-id="a9519-140">Par exemple, sur les serveurs, le partage d’application a été configuré pour utiliser les ports 40803 à 49151 ; sur les ordinateurs clients, le partage d’application est configuré pour utiliser les ports 42000 à 42019.</span><span class="sxs-lookup"><span data-stu-id="a9519-140">For example, on the servers, application sharing was configured to use ports 40803 through 49151; on the client computers, application sharing is configured to use ports 42000 through 42019.</span></span> <span data-ttu-id="a9519-141">Cette tâche est également effectuée principalement pour faciliter l’administration de la qualité de service : les ports clients n’ont pas besoin de représenter un sous-ensemble des ports utilisés sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="a9519-141">This, too, is done primarily to make administration of QoS easier: client ports do not have to represent a subset of the ports used on the server.</span></span> <span data-ttu-id="a9519-142">(Par exemple, sur les ordinateurs clients, vous pouvez configurer le partage d’application pour utiliser, par exemple, les ports 10000 à 10019.) Toutefois, il est recommandé de faire de vos plages de ports client un sous-ensemble de vos plages de ports de serveur.</span><span class="sxs-lookup"><span data-stu-id="a9519-142">(For example, on the client computers you could configure application sharing to use, say, ports 10000 through 10019.) However, it is recommended that you make your client port ranges a subset of your server port ranges.</span></span>

<span data-ttu-id="a9519-143">En outre, vous avez peut-être remarqué que 8 348 ports ont été mis de côté pour le partage d’applications sur les serveurs, mais que seuls 20 ports ont été mis de côté pour le partage d’application sur les clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-143">In addition, you might have noticed that 8348 ports were set aside for application sharing on the servers, but only 20 ports were set aside for application sharing on the clients.</span></span> <span data-ttu-id="a9519-144">Cela est également recommandé, mais il ne s’agit pas d’une règle difficile et rapide.</span><span class="sxs-lookup"><span data-stu-id="a9519-144">This, too, is recommended, but is not a hard-and-fast rule.</span></span> <span data-ttu-id="a9519-145">En règle générale, vous pouvez considérer chaque port disponible pour représenter une seule session de communication : si vous avez 100 ports disponibles dans une plage de ports, cela signifie que l’ordinateur en question peut participer, au maximum, à 100 sessions de communication à un moment donné.</span><span class="sxs-lookup"><span data-stu-id="a9519-145">In general, you can consider each available port to represent a single communication session: if you have 100 ports available in a port range, that means that the computer in question could participate in, at most, 100 communication sessions at any given time.</span></span> <span data-ttu-id="a9519-146">Étant donné que les serveurs participeront probablement à beaucoup plus de conversations que de clients, il est logique d’ouvrir beaucoup plus de ports sur les serveurs que sur les clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-146">Because servers will likely take part in many more conversations than clients, it makes sense to open many more ports on servers than on clients.</span></span> <span data-ttu-id="a9519-147">La définition de 20 ports pour le partage d’application sur un client signifie qu’un utilisateur peut participer à 20 sessions de partage d’application sur l’appareil spécifié, et le tout en même temps.</span><span class="sxs-lookup"><span data-stu-id="a9519-147">Setting aside 20 ports for application sharing on a client means that a user could participate in 20 application sharing sessions on the specified device, and all at the same time.</span></span> <span data-ttu-id="a9519-148">Cela devrait s’avérer suffisant pour la grande majorité de vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="a9519-148">That should prove sufficient for the vast majority of your users.</span></span>

<span data-ttu-id="a9519-149">Pour affecter les plages de ports précédentes à votre collection globale de paramètres de configuration de conférence, vous pouvez utiliser la commande Skype Entreprise Server Management Shell suivante :</span><span class="sxs-lookup"><span data-stu-id="a9519-149">To assign the preceding port ranges to your global collection of conferencing configuration settings, you can use the following Skype for Business Server Management Shell command:</span></span>

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="a9519-150">Vous pouvez également utiliser cette commande pour affecter ces mêmes plages de ports pour tous vos paramètres de configuration de conférence :</span><span class="sxs-lookup"><span data-stu-id="a9519-150">Or, use this command to assign these same port ranges for all your conferencing configuration settings:</span></span>

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

<span data-ttu-id="a9519-151">Les utilisateurs individuels doivent se déconnecter de Skype Entreprise, puis se déconnecter pour que ces modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="a9519-151">Individual users must log off from Skype for Business and then log back on before these changes will actually take effect.</span></span>

> [!NOTE]  
> <span data-ttu-id="a9519-152">Vous pouvez également activer les plages de ports multimédias client, puis les affecter à l’aide d’une seule commande.</span><span class="sxs-lookup"><span data-stu-id="a9519-152">You can also enable client media port ranges, and then assign those port ranges, using a single command.</span></span> <span data-ttu-id="a9519-153">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a9519-153">For example:</span></span><BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a><span data-ttu-id="a9519-154">Configurer des stratégies de qualité de service pour les clients qui s’exécutent sur Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9519-154">Configure Quality of Service policies for clients running on Windows 10</span></span>

<span data-ttu-id="a9519-155">En plus de spécifier des plages de ports à utiliser par vos clients Skype Entreprise, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-155">In addition to specifying port ranges for use by your Skype for Business clients, you must also create separate Quality of Service policies that will be applied to client computers.</span></span> <span data-ttu-id="a9519-156">(Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Skype Entreprise et Windows 10.</span><span class="sxs-lookup"><span data-stu-id="a9519-156">(The Quality of Service policies created for Conferencing, Application, and Mediation servers should not be applied to client computers.) This information applies only to computers running the Skype for Business client and Windows 10.</span></span>

<span data-ttu-id="a9519-157">L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :</span><span class="sxs-lookup"><span data-stu-id="a9519-157">The following example uses this set of port ranges to create an audio policy and a video policy:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a9519-158">Type de trafic client</span><span class="sxs-lookup"><span data-stu-id="a9519-158">Client Traffic Type</span></span></th>
<th><span data-ttu-id="a9519-159">Début du port</span><span class="sxs-lookup"><span data-stu-id="a9519-159">Port Start</span></span></th>
<th><span data-ttu-id="a9519-160">Plage de ports</span><span class="sxs-lookup"><span data-stu-id="a9519-160">Port Range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a9519-161">Audio</span><span class="sxs-lookup"><span data-stu-id="a9519-161">Audio</span></span></p></td>
<td><p><span data-ttu-id="a9519-162">50020</span><span class="sxs-lookup"><span data-stu-id="a9519-162">50020</span></span></p></td>
<td><p><span data-ttu-id="a9519-163">20</span><span class="sxs-lookup"><span data-stu-id="a9519-163">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9519-164">Vidéo</span><span class="sxs-lookup"><span data-stu-id="a9519-164">Video</span></span></p></td>
<td><p><span data-ttu-id="a9519-165">58000</span><span class="sxs-lookup"><span data-stu-id="a9519-165">58000</span></span></p></td>
<td><p><span data-ttu-id="a9519-166">20</span><span class="sxs-lookup"><span data-stu-id="a9519-166">20</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a9519-167">Partage d'application</span><span class="sxs-lookup"><span data-stu-id="a9519-167">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a9519-168">42000</span><span class="sxs-lookup"><span data-stu-id="a9519-168">42000</span></span></p></td>
<td><p><span data-ttu-id="a9519-169">20</span><span class="sxs-lookup"><span data-stu-id="a9519-169">20</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a9519-170">Transfert de fichiers</span><span class="sxs-lookup"><span data-stu-id="a9519-170">File transfer</span></span></p></td>
<td><p><span data-ttu-id="a9519-171">42020</span><span class="sxs-lookup"><span data-stu-id="a9519-171">42020</span></span></p></td>
<td><p><span data-ttu-id="a9519-172">20</span><span class="sxs-lookup"><span data-stu-id="a9519-172">20</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="a9519-173">Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 10, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée.</span><span class="sxs-lookup"><span data-stu-id="a9519-173">To create a Quality of Service audio policy for Windows 10 computers, first log on to a computer where Group Policy Management has been installed.</span></span> <span data-ttu-id="a9519-174">Ouvrez la gestion des stratégies de groupe (cliquez sur **Démarrer,** pointez sur Outils d’administration, puis cliquez sur **Gestion** des stratégies de groupe), puis complétez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="a9519-174">Open Group Policy Management (click **Start**, point to **Administrative Tools**, and then click **Group Policy Management**), and then complete the following procedure:</span></span>

1.  <span data-ttu-id="a9519-175">Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="a9519-175">In Group Policy Management, locate the container where the new policy should be created.</span></span> <span data-ttu-id="a9519-176">Par exemple, si tous vos ordinateurs clients sont situés dans une ou plusieurs des deux, la nouvelle stratégie doit être créée dans l’ou client.</span><span class="sxs-lookup"><span data-stu-id="a9519-176">For example, if all your client computers are located in an OU named Clients, the new policy should be created in the Client OU.</span></span>

2.  <span data-ttu-id="a9519-177">Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce domaine, puis le **lier ici.**</span><span class="sxs-lookup"><span data-stu-id="a9519-177">Right-click the appropriate container, and then click **Create a GPO in this domain, and Link it here**.</span></span>

3.  <span data-ttu-id="a9519-178">Dans la **boîte de dialogue Nouvel objet** de stratégie de  groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9519-178">In the **New GPO** dialog box, type a name for the new Group Policy object in the **Name** box, and then click **OK**.</span></span>

4.  <span data-ttu-id="a9519-179">Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**</span><span class="sxs-lookup"><span data-stu-id="a9519-179">Right-click the newly-created policy, and then click **Edit**.</span></span>

5.  <span data-ttu-id="a9519-180">Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration** ordinateur, Développez **Paramètres Windows,** cliquez avec le bouton droit sur **QoS** basé sur la stratégie, puis cliquez sur Créer **une stratégie.**</span><span class="sxs-lookup"><span data-stu-id="a9519-180">In the Group Policy Management Editor, expand **Computer Configuration**, expand **Windows Settings**, right-click **Policy-based QoS**, and then click **Create new policy**.</span></span>

6.  <span data-ttu-id="a9519-181">Dans la **boîte de dialogue QoS** basée sur la stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la **zone** Nom.</span><span class="sxs-lookup"><span data-stu-id="a9519-181">In the **Policy-based QoS** dialog box, on the opening page, type a name for the new policy in the **Name** box.</span></span> <span data-ttu-id="a9519-182">Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**.</span><span class="sxs-lookup"><span data-stu-id="a9519-182">Select **Specify DSCP Value** and set the value to **46**.</span></span> <span data-ttu-id="a9519-183">Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a9519-183">Leave **Specify Outbound Throttle Rate** unselected, and then click **Next**.</span></span>

7.  <span data-ttu-id="a9519-184">Sur la page suivante, sélectionnez Uniquement les applications avec ce nom **exécutable,** entrez **Lync.exe** comme nom, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a9519-184">On the next page, select **Only applications with this executable name**, enter **Lync.exe** as the name, and then click **Next**.</span></span> <span data-ttu-id="a9519-185">Ce paramètre indique à la stratégie de hiérarchiser uniquement le trafic correspondant à partir du client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="a9519-185">This setting instructs the policy to only prioritize matching traffic from the Skype for Business client.</span></span>

8.  <span data-ttu-id="a9519-186">Sur la troisième page, assurez-vous que les adresses **IP source Et** Toute adresse IP de **destination** sont sélectionnées, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="a9519-186">On the third page, make sure that both **Any source IP address** and **Any destination IP address** are selected, and then click **Next**.</span></span> <span data-ttu-id="a9519-187">Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.</span><span class="sxs-lookup"><span data-stu-id="a9519-187">These two settings ensure that packets will be managed regardless of which computer (IP address) sent those packets and which computer (IP address) will receive those packets.</span></span>

9.  <span data-ttu-id="a9519-188">Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**.</span><span class="sxs-lookup"><span data-stu-id="a9519-188">On page four, select **TCP and UDP** from the **Select the protocol this QoS policy applies to** dropdown list.</span></span> <span data-ttu-id="a9519-189">TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Skype Entreprise Server et ses applications clientes.</span><span class="sxs-lookup"><span data-stu-id="a9519-189">TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are the two networking protocols most-commonly used by Skype for Business Server and its client applications.</span></span>

10. <span data-ttu-id="a9519-190">Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**.</span><span class="sxs-lookup"><span data-stu-id="a9519-190">Under the heading **Specify the source port number**, select **From this source port or range**.</span></span> <span data-ttu-id="a9519-191">Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio.</span><span class="sxs-lookup"><span data-stu-id="a9519-191">In the accompanying text box, type the port range reserved for audio transmissions.</span></span> <span data-ttu-id="a9519-192">Par exemple, si vous avez réservé les ports 50020 à 50039 pour le trafic audio, entrez la plage de ports en utilisant ce format : **50020:50039**.</span><span class="sxs-lookup"><span data-stu-id="a9519-192">For example, if you reserved ports 50020 through ports 50039 for audio traffic enter the port range using this format: **50020:50039**.</span></span> <span data-ttu-id="a9519-193">Cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="a9519-193">Click **Finish**.</span></span>

<span data-ttu-id="a9519-194">Après avoir créé la stratégie QoS pour l’audio, vous devez créer une deuxième stratégie pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="a9519-194">After you have created the QoS policy for audio you should then create a second policy for video.</span></span> <span data-ttu-id="a9519-195">Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="a9519-195">To create a policy for video, follow the same basic procedure you followed when creating the audio policy, making these substitutions:</span></span>

  - <span data-ttu-id="a9519-196">Utilisez un nom de stratégie différent (et unique).</span><span class="sxs-lookup"><span data-stu-id="a9519-196">Use a different (and unique) policy name.</span></span>

  - <span data-ttu-id="a9519-197">Attribuez à la valeur DSCP la valeur **34** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="a9519-197">Set the DSCP value to **34** instead of 46.</span></span> <span data-ttu-id="a9519-198">(Comme indiqué précédemment, vous n’avez pas besoin d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP différente de celle utilisée pour l’audio.)</span><span class="sxs-lookup"><span data-stu-id="a9519-198">(As noted previously, you do not have to use the DSCP value 34; you simply must assign a different DSCP value than the one used for audio.)</span></span>

  - <span data-ttu-id="a9519-199">Utilisez la plage de ports précédemment configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="a9519-199">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a9519-200">Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports sur celle-ci : **58000:58019**.</span><span class="sxs-lookup"><span data-stu-id="a9519-200">For example, if you have reserved ports 58000 through 58019 for video, set the port range to this: **58000:58019**.</span></span>

<span data-ttu-id="a9519-201">Si vous décidez de créer une stratégie pour la gestion du trafic de partage d’application, faites les substitutions ci-après :</span><span class="sxs-lookup"><span data-stu-id="a9519-201">If you decide to create a policy for managing application sharing traffic, make these substitutions:</span></span>

  - <span data-ttu-id="a9519-202">Utilisez un nom de stratégie différent (et unique) (par exemple, partage d’application Skype Entreprise **Server).**</span><span class="sxs-lookup"><span data-stu-id="a9519-202">Use a different (and unique) policy name (for example, **Skype for Business Server Application Sharing**).</span></span>

  - <span data-ttu-id="a9519-203">Attribuez à la valeur DSCP la valeur **24** au lieu de 46.</span><span class="sxs-lookup"><span data-stu-id="a9519-203">Set the DSCP value to **24** instead of 46.</span></span> <span data-ttu-id="a9519-204">(Là encore, cette valeur ne doit pas être 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.)</span><span class="sxs-lookup"><span data-stu-id="a9519-204">(Again, this value does not have to be 24; it simply must be different than the DSCP values used for audio and for video.)</span></span>

  - <span data-ttu-id="a9519-205">Utilisez la plage de ports précédemment configurée pour le trafic vidéo.</span><span class="sxs-lookup"><span data-stu-id="a9519-205">Use the previously configured port range for video traffic.</span></span> <span data-ttu-id="a9519-206">Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports comme ceci : **42000:42019**.</span><span class="sxs-lookup"><span data-stu-id="a9519-206">For example, if you have reserved ports 42000 through 42019 for application sharing, set the port range to this: **42000:42019**.</span></span>

<span data-ttu-id="a9519-207">Pour une stratégie de transfert de fichiers :</span><span class="sxs-lookup"><span data-stu-id="a9519-207">For a file transfer policy:</span></span>

  - <span data-ttu-id="a9519-208">Utilisez un nom de stratégie différent (et unique) (par exemple, transferts de fichiers **Skype Entreprise Server).**</span><span class="sxs-lookup"><span data-stu-id="a9519-208">Use a different (and unique) policy name (for example, **Skype for Business Server File Transfers**).</span></span>

  - <span data-ttu-id="a9519-209">Définissez la valeur DSCP sur **14**.</span><span class="sxs-lookup"><span data-stu-id="a9519-209">Set the DSCP value to **14**.</span></span> <span data-ttu-id="a9519-210">(Là encore, cette valeur ne doit pas être 14 ; il doit simplement s’agit d’un code DSCP unique.)</span><span class="sxs-lookup"><span data-stu-id="a9519-210">(Again, this value does not have to be 14; it simply must be a unique DSCP code.)</span></span>

  - <span data-ttu-id="a9519-211">Utilisez la plage de ports précédemment configurée pour l’application.</span><span class="sxs-lookup"><span data-stu-id="a9519-211">Use the previously configured port range for application.</span></span> <span data-ttu-id="a9519-212">Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports comme ceci : **42020:42039**.</span><span class="sxs-lookup"><span data-stu-id="a9519-212">For example, if you have reserved ports 42020 through 42039 for application sharing, set the port range to this: **42020:42039**.</span></span>

<span data-ttu-id="a9519-213">Les nouvelles stratégies que vous avez créées ne prennent effet qu’une fois la stratégie de groupe actualisée sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-213">The new policies you have created will not take effect until Group Policy has been refreshed on your client computers.</span></span> <span data-ttu-id="a9519-214">Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :</span><span class="sxs-lookup"><span data-stu-id="a9519-214">Although Group Policy periodically refreshes on its own, you can force an immediate refresh by running the following command on each computer where Group Policy needs to be refreshed:</span></span>

    Gpupdate.exe /force

<span data-ttu-id="a9519-215">Cette commande peut être exécuté à partir de n’importe quelle fenêtre de commande qui s’exécute sous les informations d’identification de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="a9519-215">This command can be run from any command window that is running under administrator credentials.</span></span> <span data-ttu-id="a9519-216">Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="a9519-216">To run a command window under administrator credentials, click **Start**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

<span data-ttu-id="a9519-217">Gardez à l’esprit que ces stratégies doivent être ciblées sur vos ordinateurs clients.</span><span class="sxs-lookup"><span data-stu-id="a9519-217">Keep in mind that these policies should be targeted towards your client computers.</span></span> <span data-ttu-id="a9519-218">Elles ne doivent pas être appliquées aux serveurs exécutant Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="a9519-218">They should not be applied to servers running Skype for Business Server.</span></span>

<span data-ttu-id="a9519-219">Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="a9519-219">To help ensure that network packets are marked with the appropriate DSCP value, you should also create a new registry entry on each computer by completing the following procedure:</span></span>

1.  <span data-ttu-id="a9519-220">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a9519-220">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a9519-221">Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="a9519-221">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="a9519-222">Dans l’Éditeur du Registre, développez **HKEY \_ LOCAL \_ MACHINE,** développez **SYSTEM,** **CurrentControlSet,** développez **les services,** puis **développez Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="a9519-222">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a9519-223">Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**.</span><span class="sxs-lookup"><span data-stu-id="a9519-223">Right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a9519-224">Une fois la nouvelle clé de Registre créée, tapez **QoS,** puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="a9519-224">After the new registry key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a9519-225">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**.</span><span class="sxs-lookup"><span data-stu-id="a9519-225">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a9519-226">Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA,** puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="a9519-226">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a9519-227">Double-cliquez **sur Ne pas utiliser le NLA**.</span><span class="sxs-lookup"><span data-stu-id="a9519-227">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a9519-228">Dans la boîte **de dialogue Modifier**  la chaîne, tapez **1** dans la zone de données Valeur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9519-228">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

7.  <span data-ttu-id="a9519-229">Fermez l’Éditeur du Registre et redémarrez votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a9519-229">Close the Registry Editor and eboot your computer.</span></span>

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a><span data-ttu-id="a9519-230">Configurer la qualité de service sur des ordinateurs avec plusieurs cartes réseau</span><span class="sxs-lookup"><span data-stu-id="a9519-230">Configure Quality of Service on computers with multiple network adapters</span></span>

<span data-ttu-id="a9519-231">Si vous disposez d’un ordinateur qui possède plusieurs cartes réseau, vous pouvez parfois vous exécuter dans des problèmes où les valeurs DSCP sont affichées en tant que 0x00 plutôt que la valeur configurée.</span><span class="sxs-lookup"><span data-stu-id="a9519-231">If you have a computer that has multiple network adapters, you might occasionally run in to issues where DSCP values are shown as 0x00 rather than the configured value.</span></span> <span data-ttu-id="a9519-232">Cela se produit généralement sur les ordinateurs sur lequel une ou plusieurs cartes réseau ne sont pas en mesure d’accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé).</span><span class="sxs-lookup"><span data-stu-id="a9519-232">This will typically occur on computers where one or more of the network adapters are not able to access your Active Directory domain (for example, if these adapters are used for a private network).</span></span> <span data-ttu-id="a9519-233">Dans ce cas, les valeurs DSCP sont marquées pour les cartes qui peuvent accéder au domaine, mais pas pour les adaptateurs qui ne peuvent pas accéder au domaine.</span><span class="sxs-lookup"><span data-stu-id="a9519-233">In cases like that, DSCP values will be tagged for the adapters that can access the domain, but will not be tagged for adapters that cannot access the domain.</span></span>

<span data-ttu-id="a9519-234">Si vous souhaitez baliser des valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le Registre.</span><span class="sxs-lookup"><span data-stu-id="a9519-234">If you would like to tag DSCP values for all the network adapters in a computer, including adapters that do not have access to your domain, you will need to add and configure a value to the registry.</span></span> <span data-ttu-id="a9519-235">Pour cela, effectuez la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="a9519-235">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="a9519-236">Cliquez sur **Démarrer**, puis sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="a9519-236">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="a9519-237">Dans la **boîte de** dialogue Exécuter, tapez **regedit,** puis appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="a9519-237">In the **Run** dialog box, type **regedit**, and then press ENTER.</span></span>

3.  <span data-ttu-id="a9519-238">Dans l’Éditeur du Registre, développez **HKEY \_ LOCAL \_ MACHINE,** développez **SYSTEM,** **CurrentControlSet,** développez **les services,** puis **développez Tcpip**.</span><span class="sxs-lookup"><span data-stu-id="a9519-238">In the Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SYSTEM**, expand **CurrentControlSet**, expand **services**, and then expand **Tcpip**.</span></span>

4.  <span data-ttu-id="a9519-239">Si vous ne voyez pas de clé de Registre étiquetée **QoS,** cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau,** puis cliquez sur **Clé**.</span><span class="sxs-lookup"><span data-stu-id="a9519-239">If you do not see a registry key labeled **QoS** then right-click **Tcpip**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="a9519-240">Une fois la nouvelle clé créée, tapez **QoS,** puis appuyez sur Entrée pour renommer la clé.</span><span class="sxs-lookup"><span data-stu-id="a9519-240">After the new key is created, type **QoS**, and then press ENTER to rename the key.</span></span>

5.  <span data-ttu-id="a9519-241">Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**.</span><span class="sxs-lookup"><span data-stu-id="a9519-241">Right-click **QoS**, point to **New**, and then click **String Value**.</span></span> <span data-ttu-id="a9519-242">Une fois la nouvelle valeur de Registre créée, tapez Ne pas utiliser **le NLA,** puis appuyez sur Entrée pour renommer la valeur.</span><span class="sxs-lookup"><span data-stu-id="a9519-242">After the new registry value is created, type **Do not use NLA**, and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="a9519-243">Double-cliquez **sur Ne pas utiliser le NLA**.</span><span class="sxs-lookup"><span data-stu-id="a9519-243">Double-click **Do not use NLA**.</span></span> <span data-ttu-id="a9519-244">Dans la boîte **de dialogue Modifier**  la chaîne, tapez **1** dans la zone de données Valeur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9519-244">In the **Edit String** dialog box, type **1** in the **Value data** box, and then click **OK**.</span></span>

<span data-ttu-id="a9519-245">Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur pour que les modifications prennent effet.</span><span class="sxs-lookup"><span data-stu-id="a9519-245">After creating and configuring the new registry value, you will need to reboot your computer for the changes to take effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9519-246">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9519-246">See also</span></span>

[<span data-ttu-id="a9519-247">Créer un objet de stratégie de groupe dans Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9519-247">Create a Group Policy Object in Windows 10</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
